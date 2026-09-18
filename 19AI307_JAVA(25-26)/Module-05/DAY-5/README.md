


# Ex.No:5(E) MULTITHREADING -SYNCHRONIZATION

## QUESTION:

Read N numbers from the user, use a fixed thread pool (size 3) to compute the sum of each number multiplied by 2. Return results in the same order.

## AIM:
To write a Java program that uses a Fixed Thread Pool to process a set of numbers concurrently and demonstrates synchronization by maintaining the order of results.

## ALGORITHM :

1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read total number of tasks (T) from the user.
4. Read T numbers and store them in a list.
5. Create a FixedThreadPool of size 3 using Executors.newFixedThreadPool(3).
6. Submit tasks to multiply each number by 2 using Callable.
7. Keep the Future objects returned from each task to retain order.
8. Retrieve results using future.get() in the same order they were submitted.
9. Display final results.
10. Shutdown executor service.
11. End the program.





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
import java.util.concurrent.*;

public class FixedThreadPoolExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        int T = sc.nextInt();
        List<Integer> numbers = new ArrayList<>();
        
        for (int i = 0; i < T; i++) {
            numbers.add(sc.nextInt());
        }
        ExecutorService executor = Executors.newFixedThreadPool(3);
        List<Future<Integer>> results = new ArrayList<>();
        for (int num : numbers) {
            Future<Integer> result = executor.submit(() -> num * 2);
            results.add(result);
        }
        for (Future<Integer> res : results) {
            try {
                System.out.println("Result: " + res.get());
            } catch (Exception e) {
                e.printStackTrace();
            }
        }

        executor.shutdown();
        sc.close();
    }
}
```







## OUTPUT:
![java55](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/c2055b9ef022dad36843a4845adf77e1cc993e4d/19AI307_JAVA(25-26)/Module-05/DAY-5/java55.png)


## RESULT:
Thus, the Java program using multithreading with synchronization and a fixed thread pool to compute values and preserve output order was successfully implemented and executed.





