package dequequeuestack;

import java.util.Deque;
import java.util.LinkedList;

public class FIFOQueue<T> {
   //creation of fifo queue using deque
    private Deque<T> deque;
    //constructor
    public FIFOQueue()
    {
        deque=new LinkedList<>();//using LinkedList as the underlying implementation
    }
    //Add an element to the queue(enqueue)
    public void enqueue(T element)
    {
        deque.addLast(element);//Add to the end of the deque
    }
    
    //Remove and return the front element from the queue(dequeue)
    public  T  dequeue()
    {
        if(deque.isEmpty()){
            throw new IllegalStateException("Queue is empty");
        }
        return deque.removeFirst();//Remove from the front of the deque
    }
    
    public T peek()
    {
        if (deque.isEmpty())
        {
            throw new IllegalStateException("Queue is empty");
        }
        return deque.getFirst();//Get the front element
    }
    
    //check if the queue is empty
    public boolean isEmpty()
    {
        return deque.isEmpty();
    }
    //override toSring() to display the element in the queue
    @Override
    public String toString()
    {
        return deque.toString();
    }
}
