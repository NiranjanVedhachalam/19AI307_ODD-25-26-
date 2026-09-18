

# Ex.No:5(D) THREAD PRIORITY

## QUESTION:
Write a java program for set the priority and name of the current thread.Consider two threads t1 and t2

## AIM:
To write a Java program that demonstrates thread priority by creating two threads, assigning names and priorities to them, and displaying thread execution.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a class that extends Thread.
4. Override the run() method to print the current thread name and priority.
5. Create two thread objects t1 and t2.
6. Set names and priorities for each thread using setName() and setPriority().
7. Start both threads.
8. Display messages showing thread execution order.
9. End the program.


## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: Niranjan V
RegisterNumber: 21222224110042
*/
```

## SOURCE CODE:
```
import java.util.*;

public class ThreadPriorityExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String name1 = sc.nextLine();
        String name2 = sc.nextLine();
        Thread t1 = new Thread();
        Thread t2 = new Thread();
        t1.setName(name1);
        t2.setName(name2);
        t1.setPriority(4);
        t2.setPriority(2);
        System.out.println(t1);
        System.out.println(t2);

        sc.close();
    }
}
```

## OUTPUT:

![java54](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/7d952630fc35928069eb8db8971d42aa9400df96/19AI307_JAVA(25-26)/Module-05/DAY-4/java54.png)


## RESULT:
Thus, the Java program that demonstrates thread naming and thread priority was successfully executed.
