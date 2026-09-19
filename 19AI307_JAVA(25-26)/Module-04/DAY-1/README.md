# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:
If an Integer object is set to null, and you attempt to call .toString() on it, what happens? How can you prevent your code from throwing an exception in such cases?


## AIM:

To write a Java program to demonstrate NullPointerException when calling .toString() on a null Integer object and to handle the exception using try-catch.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read an integer value from the user.
4. Assign null if the user enters 0 (or a specific case).
5. Try to call .toString() method on the Integer object.
6. Catch the NullPointerException and display a meaningful message.
7. Display output and end the program.

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
import java.util.Scanner;

public class NullCheck
{
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        Integer num = sc.nextInt(); 
        try 
        {
            if (num == 0) 
            {
                num = null;
            }
            System.out.println(num.toString());

        } 
        catch (NullPointerException e) 
        {
            System.out.println("Null Integer");
        }
    }
}
```






## OUTPUT:
![java41](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/9322907efbe6666ef88acb6049076b422ed172f1/19AI307_JAVA(25-26)/Module-04/DAY-1/java41.png)


## RESULT:
Thus, the program demonstrates that calling .toString() on a null object causes a NullPointerException, and the exception can be prevented using a try-catch block.

# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM 

## QUESTION:
In a large office, multiple departments send print jobs to a shared central printer. To manage load and prevent collision, a Print Spooler Manager handles all job submissions.

The IT team insists that there should be only one spooler manager instance in the entire system. Regardless of how many jobs or departments exist, all jobs must pass through this one manager.

Your task is to simulate a singleton print job queue. Each print job submitted increases the queue count.

## AIM:
To write a Java program that demonstrates the Singleton Design Pattern, ensuring only one instance of a Print Spooler Manager exists to handle job queue management.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a PrintSpooler class with:

    A private static instance.

    A private constructor.

    A public static getInstance() method to return the single instance.

4. Maintain a counter that represents the number of print jobs.
5. In the main() method, simulate two departments submitting print jobs.
6. Access the same instance of the Print Spooler and increment the job count.
7. Display the print job queue.
8. Stop the program.



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

class PrintSpoolerManager {
    private static PrintSpoolerManager instance;
    private int jobCount = 0;

    private PrintSpoolerManager() {}

    public static PrintSpoolerManager getInstance() {
        if (instance == null) {
            instance = new PrintSpoolerManager();
        }
        return instance;
    }

    public int submitJob(String department) {
        jobCount++;
        return jobCount;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            String dept = sc.nextLine();
            PrintSpoolerManager spooler = PrintSpoolerManager.getInstance();
            int total = spooler.submitJob(dept);
            System.out.println(dept + " submitted a print job. Total Jobs in Queue: " + total);
        }
    }
}
```


## OUTPUT:

![java42](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/307e4889adff0712306078adcc9b86614a3f814f/19AI307_JAVA(25-26)/Module-04/DAY-2/java42.png)

## RESULT:
Thus, the program to simulate a Singleton Print Spooler Manager using SOLID principles was successfully implemented and executed.

# Ex.No:4(C)  COMPOSITION IN JAVA

## QUESTION:
Create animals from two regions: "Africa" and "Asia". Use Abstract Factory to create families of animals (Herbivore, Carnivore). Print the interaction result.



## AIM:
To write a Java program demonstrating Composition and Abstract Factory Pattern by creating animal families of different regions and displaying interactions between herbivores and carnivores.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create interfaces Herbivore and Carnivore.
4. Create concrete animal classes (e.g., Wildebeest, Lion, Deer, Tiger) implementing those interfaces.
5. Create an abstract factory class for producing families of animals.
6. Implement region-based factories (AfricaFactory, AsiaFactory).
7. In the main program, instantiate factories and show interactions.
8. Print the result.
9. Stop the program.

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
import java.util.Scanner;

interface Herbivore {}
interface Carnivore {
    void eat(Herbivore h);
}

class Wildebeest implements Herbivore {}
class Lion implements Carnivore {
    public void eat(Herbivore h) {
        System.out.println("Lion eats Wildebeest");
    }
}

class Buffalo implements Herbivore {}
class Tiger implements Carnivore {
    public void eat(Herbivore h) {
        System.out.println("Tiger eats Buffalo");
    }
}

interface AnimalFactory {
    Herbivore createHerbivore();
    Carnivore createCarnivore();
}

class AfricaFactory implements AnimalFactory {
    public Herbivore createHerbivore() { return new Wildebeest(); }
    public Carnivore createCarnivore() { return new Lion(); }
}

class AsiaFactory implements AnimalFactory {
    public Herbivore createHerbivore() { return new Buffalo(); }
    public Carnivore createCarnivore() { return new Tiger(); }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String region = sc.nextLine().toLowerCase();
        AnimalFactory factory;

        if (region.equals("africa")) factory = new AfricaFactory();
        else if (region.equals("asia")) factory = new AsiaFactory();
        else {
            System.out.println("Invalid region");
            return;
        }

        Carnivore carn = factory.createCarnivore();
        Herbivore herb = factory.createHerbivore();
        carn.eat(herb);
    }
}
```





## OUTPUT:

![java43](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/8b4be1e27b6fb5da0aa68915801ab1e6c9c7174e/19AI307_JAVA(25-26)/Module-04/DAY-3/java43.png)

## RESULT:
Thus, the program using Composition and Abstract Factory Pattern was successfully implemented and executed to create animal interactions for African and Asian regions.

# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
You are asked to simulate a simple Shape Drawing Tool using the Factory Design Pattern in Java.

You will implement a Shape interface with concrete classes for different shapes (Circle, Square, Rectangle). Using a ShapeFactory, your program will take shape names from user input and draw them accordingly. If the shape is unknown, print an error message.



## AIM:
To write a Java program that implements the Factory Design Pattern to create and draw shapes dynamically based on user input.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Shape interface containing a draw() method.
4. Create concrete classes Circle, Square, and Rectangle implementing Shape.
5. Create a ShapeFactory class with a method getShape(String shapeType).
6. In the main() method, accept user input for shape type.
7. Call factory method to get the appropriate object.
8. Draw the shape or print error if unknown.
9. Stop the program.


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
import java.util.Scanner;

interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing Square");
    }
}

class Rectangle implements Shape {
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

class ShapeFactory {
    public Shape getShape(String shapeType) {
        if (shapeType == null) {
            return null;
        }
        switch (shapeType.toLowerCase()) {
            case "circle":
                return new Circle();
            case "square":
                return new Square();
            case "rectangle":
                return new Rectangle();
            default:
                return null;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        ShapeFactory factory = new ShapeFactory();
        
        while (true) {
            String input = sc.nextLine().trim();
            if (input.equalsIgnoreCase("exit")) {
                break;
            }
            
            Shape shape = factory.getShape(input);
            if (shape != null) {
                shape.draw();
            } else {
                System.out.println("Invalid shape: " + input);
            }
        }
        sc.close();
    }
}
```






## OUTPUT:

![java44](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/b628a27d8352a971924fad5b0adffc7f5f8644ba/19AI307_JAVA(25-26)/Module-04/DAY-4/java44.png)

## RESULT:
Thus, the Java program to simulate Shape Drawing using the Factory Design Pattern was successfully implemented and executed.

# Ex.No:4(D) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:
Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.



## AIM:
To write a Java program that demonstrates a Behavioral Pattern using the Factory Method, allowing different notification types to send messages through a common interface.

## ALGORITHM :
1.Start the program.
2.Create the NotificationContext object.
3.Read the notification type from the user.
4.If the input is "exit", terminate the program.
5.Otherwise, check the notification type:
6.If it is email, create EmailNotification.
If it is sms, create SMSNotification.
If it is push, create PushNotification.
7.Set the selected notification as the strategy using setStrategy().
Call sendNotification() from the NotificationContext.
8.The selected strategy executes its notifyUser() method.
9.If the input is invalid, display "Invalid notification type".
10.Repeat steps 3–9 until the user enters "exit".
11.Stop the program.





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

import java.util.Scanner;

// ===== Strategy Interface =====
interface NotificationStrategy {
    void notifyUser();
}

// ===== Concrete Strategies =====
class EmailNotification implements NotificationStrategy {
    public void notifyUser() {
        System.out.println("Sending Email Notification");
    }
}

class SMSNotification implements NotificationStrategy {
    public void notifyUser() {
        System.out.println("Sending SMS Notification");
    }
}

class PushNotification implements NotificationStrategy {
    public void notifyUser() {
        System.out.println("Sending Push Notification");
    }
}

// ===== Context =====
class NotificationContext {
    private NotificationStrategy strategy;

    public void setStrategy(NotificationStrategy strategy) {
        this.strategy = strategy;
    }

    public void sendNotification() {
        if (strategy != null) {
            strategy.notifyUser();
        } else {
            System.out.println("No notification strategy selected");
        }
    }
}

// ===== Main =====
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        NotificationContext context = new NotificationContext();

        while (true) {
            String input = sc.nextLine().trim();

            if (input.equalsIgnoreCase("exit")) {
                break;
            }

            switch (input.toLowerCase()) {
                case "email":
                    context.setStrategy(new EmailNotification());
                    break;

                case "sms":
                    context.setStrategy(new SMSNotification());
                    break;

                case "push":
                    context.setStrategy(new PushNotification());
                    break;

                default:
                    System.out.println("Invalid notification type: " + input);
                    continue;
            }

            context.sendNotification();
        }

        sc.close();
    }
}


```






## OUTPUT:

![java45](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/c6316a5904f4a174dd995f6b7d7c47b65f677921/19AI307_JAVA(25-26)/Module-04/DAY-5/java45.png)

## RESULT:
Thus, the program demonstrating the Behavioral Pattern using Factory Method to generate different notification types was successfully implemented and executed.



