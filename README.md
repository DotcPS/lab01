# lab01
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.Random;

public class ListComparison {
    public static void main(String[] args) {
        int listSize = 100000;
        int insertSize = 1000;
        
        ArrayList<Integer> arrayList = new ArrayList<>();
        LinkedList<Integer> linkedList = new LinkedList<>();
        
     
        fillList(arrayList, listSize);
        fillList(linkedList, listSize);
        
      
        measureFillOperation("ArrayList", arrayList, listSize);
        measureFillOperation("LinkedList", linkedList, listSize);
        
      
        measureInsertOperation("ArrayList", arrayList, insertSize, listSize / 2);
        measureInsertOperation("LinkedList", linkedList, insertSize, listSize / 2);
        
      
    }
    
    public static void fillList(java.util.List<Integer> list, int size) {
        Random random = new Random();
        for (int i = 0; i < size; i++) {
            list.add(random.nextInt(size));
        }
    }
    
    public static void measureFillOperation(String listType, java.util.List<Integer> list, int size) {
        long startTime = System.nanoTime();
        
        long endTime = System.nanoTime();
        long duration = endTime - startTime;
        System.out.println("Fill " + listType + ": " + duration + " ns");
    }
    
    public static void measureInsertOperation(String listType, java.util.List<Integer> list, int insertSize, int index) {
        long startTime = System.nanoTime();
       
        long endTime = System.nanoTime();
        long duration = endTime - startTime;
        System.out.println("Insert in the middle of " + listType + ": " + duration + " ns");
    }
    

}
