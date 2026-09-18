
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
Developed by: Niranjan V
RegisterNumber: 21222224110042
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
