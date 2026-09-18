# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:
A jewelry store tracks gold rates for different types of customers. The base class is Customer with attributes like customerId, name, and purchaseWeight (in grams). There are two types of customers: RegularCustomer and PremiumCustomer. RegularCustomer gets a fixed discount of 2% on the gold rate per gram. PremiumCustomer gets a 5% discount plus a special cashback. The base gold rate per gram is input at runtime. For each customer, calculate the final price they pay:

## AIM:
To write a Java program demonstrating Inheritance and Aggregation by creating subclasses for different customer types and applying different pricing policies using inheritance.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a base class Customer with attributes customerId, name, and purchaseWeight.
4. Create two derived classes: RegularCustomer and PremiumCustomer extending Customer.
5. Implement a method in both subclasses to calculate the final price after discounts.
6. Input base gold rate per gram using Scanner in the main method.
7. Create customer objects and calculate final price.
8. Display results.
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
import java.util.*;
import java.text.DecimalFormat;

class Customer {
    String customerId, name;
    double purchaseWeight, goldRatePerGram;

    Customer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        this.customerId = customerId;
        this.name = name;
        this.purchaseWeight = purchaseWeight;
        this.goldRatePerGram = goldRatePerGram;
    }

    double getDiscountRate() {
        return 0;
    }

    double calculateFinalPrice() {
        double discountAmount = goldRatePerGram * getDiscountRate() / 100;
        double effectiveRate = goldRatePerGram - discountAmount;
        return purchaseWeight * effectiveRate;
    }

    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: General");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
    }
}

class RegularCustomer extends Customer {
    RegularCustomer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        super(customerId, name, purchaseWeight, goldRatePerGram);
    }

    @Override
    double getDiscountRate() {
        return 2;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Regular");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
    }
}

class PremiumCustomer extends Customer {
    PremiumCustomer(String customerId, String name, double purchaseWeight, double goldRatePerGram) {
        super(customerId, name, purchaseWeight, goldRatePerGram);
    }

    @Override
    double getDiscountRate() {
        return 5;
    }

    double calculateCashback() {
        return calculateFinalPrice() * 0.01;
    }

    @Override
    void display() {
        DecimalFormat df = new DecimalFormat("0.00");
        System.out.println("Customer ID: " + customerId);
        System.out.println("Name: " + name);
        System.out.println("Customer Type: Premium");
        System.out.println("Purchase Weight: " + purchaseWeight + " grams");
        System.out.println("Gold Rate per Gram: " + goldRatePerGram);
        System.out.println("Discount: " + (int)getDiscountRate() + "%");
        System.out.println("Final Price: " + df.format(calculateFinalPrice()));
        System.out.println("Cashback: " + df.format(calculateCashback()));
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String type = sc.nextLine().trim();
        String id = sc.nextLine().trim();
        String name = sc.nextLine().trim();
        double weight = sc.nextDouble();
        double goldRate = sc.nextDouble();

        Customer c;
        if (type.equalsIgnoreCase("Regular"))
            c = new RegularCustomer(id, name, weight, goldRate);
        else
            c = new PremiumCustomer(id, name, weight, goldRate);

        c.display();
    }
}
```
## OUTPUT:
![java31](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/14dc8b0a86e753d5e3ad7f7ea47059065871c1c7/19AI307_JAVA(25-26)/Module-03/DAY-1/java31.png)


## RESULT:
Thus, the Java program demonstrating Inheritance and Aggregation using customer types with different discount calculations was successfully executed.

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
Developed by:  SHREYESHKAR SEKAR
RegisterNumber: 212224220099
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


# Ex.No:3(C) ABSTRACTION

## QUESTION:
A group of researchers receives mysterious numerical sequences believed to be sent by intelligent alien life. To decode them, scientists have built intelligent SignalAgents that follow abstract processing rules. Each agent listens to the numbers differently.

Your task is to create a system where a base abstract class SignalAgent declares:

## AIM:
To implement Abstraction in Java by defining an abstract class with abstract methods and providing different implementations in derived subclasses.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an abstract class SignalAgent with an abstract method processNumbers(int[]).
4. Create subclasses SumAgent and AverageAgent that extend the base class and provide method implementations.
5. Accept a numerical sequence from the user and store it in an array.
6. Allow the user to select which type of agent to use for processing.
7. Display the processed result.
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
import java.util.*;

abstract class SignalAgent {
    abstract int decodeSignal(int[] signal);
}

class PrimeAgent extends SignalAgent {
    boolean isPrime(int n) {
        if (n <= 1) return false;
        for (int i = 2; i * i <= n; i++) {
            if (n % i == 0)
                return false;
        }
        return true;
    }

    @Override
    int decodeSignal(int[] signal) {
        int sum = 0;
        for (int num : signal) {
            if (isPrime(num))
                sum += num;
        }
        return sum;
    }
}

class MirrorAgent extends SignalAgent {
    @Override
    int decodeSignal(int[] signal) {
        int n = signal.length;
        for (int i = 0; i < n / 2; i++) {
            if (signal[i] != signal[n - 1 - i]) {
             
                return -1;
            }
        }
        return 1;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] signal = new int[n];
        for (int i = 0; i < n; i++)
            signal[i] = sc.nextInt();
        int type = sc.nextInt();
        
        SignalAgent agent;
        
        if (type == 1) {
            agent = new PrimeAgent();
            System.out.println(agent.decodeSignal(signal));
        } else if (type == 2) {
            agent = new MirrorAgent();
            int result = agent.decodeSignal(signal);
            if (result == 1)
                System.out.println("BALANCED");
            else
                System.out.println("BROKEN");
        }
    }
}
```





## OUTPUT:

![java33](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/838b2936e04f552789e71372bc8cc875126469d1/19AI307_JAVA(25-26)/Module-03/DAY-3/java33.png)

## RESULT:
Thus, the Java program demonstrating Abstraction using an abstract class and derived classes was executed successfully.


# Ex.No:3(D)    INTERFACE 

## QUESTION:
Each judge uses different criteria to score fighters. Based on points, the judge will declare “WIN”, “LOSE” or “DRAW”.

LenientJudge: WIN if diff ≥ 5, DRAW if < 5

StrictJudge: WIN if diff ≥ 10, DRAW if < 10
## AIM:


## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an interface Judge with an abstract method getResult(int fighter1, int fighter2).
4. Create two classes LenientJudge and StrictJudge implementing the interface and applying different scoring criteria.
5. Accept points scored by two fighters from the user.
6. Accept judge type from the user and invoke the respective implementation.
7. Display the result as WIN, LOSE, or DRAW.
8.Stop the program.

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

interface Judge {
    String decide(int p1, int p2);
}

class LenientJudge implements Judge {
    public String decide(int p1, int p2) {
        int diff = Math.abs(p1 - p2);
        if (p1 > p2 && diff >= 5)
            return "WIN";
        else if (p2 > p1 && diff >= 5)
            return "LOSE";
        else
            return "DRAW";
    }
}

class StrictJudge implements Judge {
    public String decide(int p1, int p2) {
        int diff = Math.abs(p1 - p2);
        if (p1 > p2 && diff >= 10)
            return "WIN";
        else if (p2 > p1 && diff >= 10)
            return "LOSE";
        else
            return "DRAW";
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int p1 = sc.nextInt();
        int p2 = sc.nextInt();
        int judgeType = sc.nextInt();

        Judge judge;
        if (judgeType == 1)
            judge = new LenientJudge();
        else if (judgeType == 2)
            judge = new StrictJudge();
        else {
            System.out.println("Invalid judge type");
            return;
        }

        System.out.println(judge.decide(p1, p2));
    }
}
```







## OUTPUT:
![java34](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/564ba08ef73efc7e73a0883948f623cfa5b0ee65/19AI307_JAVA(25-26)/Module-03/DAY-4/java34.png)


## RESULT:
Thus, the Java program demonstrating Interface implementation using different judging criteria was executed successfully.


# Ex.No:3(E) INNER CLASS

## QUESTION:
Write a Java program to create an inner class and access it from the outer class.


## AIM:
To write a Java program that demonstrates the use of an Inner Class and how it can be accessed from the Outer Class

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an outer class.
4. Inside the outer class, declare and define an inner class.
5. Create an object of the outer class.
6. Using the outer class object, create an object of the inner class.
7. Call a method of the inner class through its object.
8. Display the output.
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

public class OuterClass 
{
    class InnerClass
    {
        void displayMessage(String name)
        {
            System.out.println("Hello, " + name + "! This message is from the Inner Class.");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String name = sc.nextLine();
        OuterClass outer = new OuterClass();          
        OuterClass.InnerClass inner = outer.new InnerClass(); 
        inner.displayMessage(name); 
    }
}
```
## OUTPUT:

![java35](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/056a3e4c1367cee76213b9fd31b087383b53c8b0/19AI307_JAVA(25-26)/Module-03/DAY-5(A)/java35.png)

## RESULT:
Thus, the Java program to implement an Inner Class and access it from the Outer Class was successfully executed.

# Ex.No:3(F) WRAPPER CLASS

## QUESTION:
Find the largest digit in a number using wrapper class methods.

## AIM:
To write a Java program to find the largest digit in a given number using Wrapper Class methods.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the number from the user.
4. Convert the number to a string using wrapper class Integer.toString().
5. Traverse each character, convert it back to an integer using Character.getNumericValue().
6. Compare digits and store the largest digit.
7. Display the largest digit.
8. Stop the program.

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

public class LargestDigit {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

       
        int number = sc.nextInt();

        String input = Integer.toString(number);

        int largest = 0;

       
        for (int i = 0; i < input.length(); i++) {
            int digit = Character.getNumericValue(input.charAt(i));

           
            if (digit > largest) {
                largest = digit;
            }
        }

       
        System.out.println("The largest digit is: " + largest);

        sc.close();
    }
}
```



## OUTPUT:

![java36](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/81caee57fce6fff987403423e665ea8f13ba347d/19AI307_JAVA(25-26)/Module-03/DAY-5(B)/java36.png)

## RESULT:
Thus, the program to find the largest digit in a number using Wrapper Class methods was successfully executed.

