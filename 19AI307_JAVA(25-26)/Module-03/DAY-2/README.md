# Ex.No:3(b) POLYMORPHISM


## QUESTION:
Write a Java program using method overriding. Create a superclass Bank with a method getInterestRate() returning 0. Create subclasses SBI, ICICI, and HDFC that override the method.

## AIM:
To write a Java program demonstrating runtime polymorphism using method overriding, where subclasses override a method of the superclass to provide specific implementation.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a superclass Bank with a method getInterestRate() returning 0.
4. Create subclasses SBI, ICICI, and HDFC that override the method to return different interest rates.
5. In the main() method, accept bank name at runtime.
6. Create an object of the appropriate subclass based on the input.
7. Call the overridden method using a reference of type Bank.
8. Display the interest rate.
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
class Bank {
    double getInterestRate() {
        return 0;
    }
}

class SBI extends Bank {
    @Override
    double getInterestRate() {
        return 6.5;
    }
}

class ICICI extends Bank {
    @Override
    double getInterestRate() {
        return 7.0;
    }
}

class HDFC extends Bank {
    @Override
    double getInterestRate() {
        return 7.5;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String bankName = sc.nextLine().trim();
        Bank bank;
        if (bankName.equalsIgnoreCase("SBI")) {
            bank = new SBI();
            System.out.println("SBI Rate: " + bank.getInterestRate() + "%");
        } else if (bankName.equalsIgnoreCase("ICICI")) {
            bank = new ICICI();
            System.out.println("ICICI Rate: " + bank.getInterestRate() + "%");
        } else if (bankName.equalsIgnoreCase("HDFC")) {
            bank = new HDFC();
            System.out.println("HDFC Rate: " + bank.getInterestRate() + "%");
        } else {
            System.out.println("Invalid bank name.");
        }
    }
}
```





## OUTPUT:

![java32](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/508d76d2dc9f661dc9ddb5bb22d00b081114519e/19AI307_JAVA(25-26)/Module-03/DAY-2/java32.png)


## RESULT:

Thus, the Java program demonstrating Polymorphism using Method Overriding was successfully executed.
