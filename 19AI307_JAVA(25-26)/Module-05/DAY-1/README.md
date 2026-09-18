# Ex.No:5(A) INPUTSTREAMREADER 

## QUESTION:
Write a Java program to write characters to a file using FileWriter.



## AIM:
To write a Java program that writes character data into a text file using the FileWriter class.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a FileWriter object and specify the filename.
4. Write characters to the file using the write() method.
5. Close the FileWriter to save the data.
6. End the program.




## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by:  SHREYESHKAR SEKAR
RegisterNumber: 212224220099
*/
```

## SOURCE CODE:
```
import java.io.*;
import java.util.Scanner;

public class FileWriterExampleUserInput {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            String fileName = sc.nextLine();
            String content = sc.nextLine();
            FileWriter fw = new FileWriter(fileName);
            fw.write(content);
            fw.close();

            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.out.println("Error writing to file: " + e.getMessage());
        } finally {
            sc.close();
        }
    }
}
```






## OUTPUT:

![java51](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/a9261fe7fb8a08b278b91f6a1a979055f59755dc/19AI307_JAVA(25-26)/Module-05/DAY-1/java51.png)

## RESULT:
Thus, the Java program to write characters to a file using FileWriter was successfully executed and verified.

# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION 

## QUESTION:
Write a Java program to read a string from the user, compress it in memory using ByteArrayOutputStream + GZIPOutputStream, and then decompress it back using ByteArrayInputStream + GZIPInputStream.


## AIM:

To write a Java program that reads a string from the user, compresses it using GZIP compression, and then decompresses it back to its original form.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read a string from the user using Scanner.
4. Create a ByteArrayOutputStream object to hold compressed data.
5. Wrap it with GZIPOutputStream and write the user string into it to perform compression.
6. Convert compressed data into a byte array.
7. Create a ByteArrayInputStream object using the compressed byte array.
8. Wrap it with GZIPInputStream to decompress the content.
9. Read decompressed bytes and convert them back into the original string.
10. Display original, compressed size, and decompressed results.
11. End the program.





## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by:  SHREYESHKAR SEKAR
RegisterNumber: 212224220099
*/
```

## SOURCE CODE:
```
import java.io.*;
import java.util.Scanner;
import java.util.zip.GZIPOutputStream;
import java.util.zip.GZIPInputStream;

public class GZIPMemoryExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            String input = scanner.nextLine();

            ByteArrayOutputStream baos = new ByteArrayOutputStream();
            GZIPOutputStream gzipOut = new GZIPOutputStream(baos);
            gzipOut.write(input.getBytes("UTF-8"));
            gzipOut.close(); 

            byte[] compressedData = baos.toByteArray();
            System.out.println("Compressed data (bytes):");
            for (byte b : compressedData) {
                System.out.print(b + " ");
            }
            System.out.println("\nTotal bytes: " + compressedData.length);

            ByteArrayInputStream bais = new ByteArrayInputStream(compressedData);
            GZIPInputStream gzipIn = new GZIPInputStream(bais);
            InputStreamReader reader = new InputStreamReader(gzipIn, "UTF-8");
            BufferedReader br = new BufferedReader(reader);

            StringBuilder decompressed = new StringBuilder();
            String line;
            while ((line = br.readLine()) != null) {
                decompressed.append(line);
            }

            System.out.println("\nDecompressed string:");
            System.out.println(decompressed.toString());

            br.close();
            gzipIn.close();
            bais.close();

        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        } finally {
            scanner.close();
        }
    }
}
```






## OUTPUT:
![java52](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/4629176025934c52170b68fd2b511f5724754685/19AI307_JAVA(25-26)/Module-05/DAY-2/java52.png)


## RESULT:
Thus, the Java program to compress and decompress a string using ByteArrayOutputStream, GZIPOutputStream, ByteArrayInputStream, and GZIPInputStream was successfully implemented and executed.

# Ex.No:5(C)  FILE HANDLING USING JAVA
## QUESTION:
Write a program to count the number of words in a file.



## AIM:
To write a Java program that reads a text file and counts the number of words present in the file using file handling mechanisms.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a File object to reference the input text file.
4. Use Scanner or FileReader to read the contents of the file.
5. Split the file content into words using space or delimiter.
6. Count the total number of words.
7. Display the word count.
8. End the program.





## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by:  SHREYESHKAR SEKAR
RegisterNumber: 212224220099
*/
```

## SOURCE CODE:
```
import java.io.*;
import java.util.*;

public class WordCountInFile {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            String content = sc.nextLine();
            FileWriter fw = new FileWriter("input.txt");
            fw.write(content);
            fw.close();
            BufferedReader br = new BufferedReader(new FileReader("input.txt"));
            String line;
            int wordCount = 0;
            while ((line = br.readLine()) != null) {
                String[] words = line.trim().split("\\s+");
                if (!line.trim().isEmpty()) {
                    wordCount += words.length;
                }
            }

            br.close();
            System.out.println("Number of words in the file: " + wordCount);

        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        } finally {
            sc.close();
        }
    }
}
```






## OUTPUT:
![java53](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/6117fd83efb67a2066ea2c15c1ee8c4e274b4538/19AI307_JAVA(25-26)/Module-05/DAY-3/java53.png)


## RESULT:
Thus, the Java program that counts the number of words in a file using file handling was successfully executed.

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
Developed by:  SHREYESHKAR SEKAR
RegisterNumber: 212224220099
*/
```

## SOURCE CODE:
```
import java.util.*;

class MyThread extends Thread {
    public void run() {
        System.out.println("Thread Name: " + getName());
        System.out.println("Thread Priority: " + getPriority());
    }
}

public class ThreadPriorityExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String name1 = sc.nextLine();
        String name2 = sc.nextLine();

        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();

        t1.setName(name1);
        t2.setName(name2);

        t1.setPriority(4);
        t2.setPriority(2);

        t1.start();
        t2.start();

        sc.close();
    }
}
```

## OUTPUT:

![java54](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/7d952630fc35928069eb8db8971d42aa9400df96/19AI307_JAVA(25-26)/Module-05/DAY-4/java54.png)


## RESULT:
Thus, the Java program that demonstrates thread naming and thread priority was successfully executed.

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





