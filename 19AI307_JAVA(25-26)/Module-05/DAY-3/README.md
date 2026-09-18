
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
Developed by: Niranjan V
RegisterNumber: 21222224110042
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
