
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
Developed by: Niranjan V
RegisterNumber: 21222224110042
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

