
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
Developed by: Niranjan V
RegisterNumber: 21222224110042
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
