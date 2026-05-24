# Java 中的猜数字游戏

> 原文：[https://www.geeksforgeeks.org/number-guessing-game-in-java/](https://www.geeksforgeeks.org/number-guessing-game-in-java/)

任务是编写一个 [Java 程序](https://www.geeksforgeeks.org/java/)，其中用户将得到 `K` 的试验来猜测一个随机生成的数字。下面是游戏规则：

*   如果猜测的数字大于实际数字，程序将响应一条消息，说明猜测的数字高于实际数字。
*   如果猜测的数字小于实际数字，程序将响应一条消息，说明猜测的数字低于实际数字。
*   如果猜测的数字等于实际数字，或者 `k` 次测试已用完，程序将结束并显示相应的消息。

**方法：** 下面是步骤：

*   方法是使用 Java 中的 [`Math.random()`](https://www.geeksforgeeks.org/java-math-random-method-examples/) 方法来生成一个随机数。
*   现在使用一个循环来获取用户的 `k` 次输入，并为每次输入打印该数字是小于还是大于实际数字。
*   如果用户在 `k` 次尝试中猜对了数字，则打印用户获胜。
*   否则，打印他无法猜到，并打印实际数字。

下面是上述方法的实现：

## Java 代码

```java
// Java program for the above approach
import java.util.Scanner;

public class GFG {

    // Function that implements the
    // number guessing game
    public static void guessingNumberGame()
    {
        // Scanner Class
        Scanner sc = new Scanner(System.in);

        // Generate the numbers
        int number = 1 + (int)(100 * Math.random());

        // Given K trials
        int K = 5;

        int i, guess;

        System.out.println(
            "A number is chosen"
            + " between 1 to 100."
            + "Guess the number"
            + " within 5 trials.");

        // Iterate over K Trials
        for (i = 0; i < K; i++) {

            System.out.println(
                "Guess the number:");

            // Take input for guessing
            guess = sc.nextInt();

            // If the number is guessed
            if (number == guess) {
                System.out.println(
                    "Congratulations!"
                    + " You guessed the number.");
                break;
            }
            else if (number > guess
                     && i != K - 1) {
                System.out.println(
                    "The number is "
                    + "greater than " + guess);
            }
            else if (number < guess
                     && i != K - 1) {
                System.out.println(
                    "The number is"
                    + " less than " + guess);
            }
        }

        if (i == K) {
            System.out.println(
                "You have exhausted"
                + " K trials.");

            System.out.println(
                "The number was " + number);
        }
    }

    // Driver Code
    public static void main(String arg[])
    {
        // Function Call
        guessingNumberGame();
    }
}
```