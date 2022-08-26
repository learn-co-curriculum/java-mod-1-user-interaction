# User Interaction

## Learning Goals

- How to take user input
- Take inputs from user

## Introduction

The conditional statements we used as examples in the previous units were not
very useful because they will always evaluate to the same value. That's because
all our values in our examples so far have been hard-coded. In other words,
we've only had statements like this:

```java
String variableName = "some value";
```

Even when we've applied some calculation, it's been calculations based on
hard-coded values:

```java
int userYear = 2000;
int currentYear = 2022;
int age = currentYear - userYear;
```

Let's explore how we can get the user to give us their own values.

## Taking User Input in Java

Java comes with utility classes that implement common functionality, like we saw
with the `Random` class. Another utility is a class that handles taking in user
input!

The class that has the functionality we are interested in is the `Scanner`
class. The **Scanner class** is in the package `java.util` and contains the
necessary methods for us to use in order to get the accurate input from the
user. To use the `Scanner` class, we must import it using the `import` statement
like we saw in the Random Class lesson:

```java
import java.util.Scanner;
```

Once we've imported the `Scanner` class, we can use it anywhere in our class by
declaring a variable of that type:

```java
Scanner myScanner;
```

The functionality of the `Scanner` class is to allow it to read input from a
variety of input sources. In our case, we want to read input from the terminal
where our program will be running. This is represented by a variable in another
Java class named `System`. This is the same class we've been using to display
text in the terminal with the `out` variable:

```java
System.out.println("message here");
```

Now we're going to use the `in` variable to get input from the same terminal.
The `System.in` variable is passed into the `Scanner` object when we create it:

```java
Scanner inputScanner = new Scanner(System.in);
```

Once the `inputScanner` has been initialized, we can use it to get input from
the terminal. The `Scanner` class has quite a few methods that can help us!
Consider the following methods that may be of use to us:

| Method          | Description                                     |
|-----------------|-------------------------------------------------|
| `nextDouble()`  | Scans the next token of the input as a `double` |
| `nextFloat()`   | Scans the next token of the input as a `float`  |
| `nextInt`       | Scans the next token of the input as an `int`   |
| `nextLong()`    | Scans the next token of the input as a `long`   |
| `nextLine()`    | Scans the next token until it sees a newline    |
| `next()`        | Scans the next token until it sees a space      |

Depending on what it is we are expecting the user to input, we can use any of
the above methods. For example, if we are expecting an `int` data type, then we
can use the `nextInt()` method. If we are expecting a sentence or string of
words, we can use the `nextLine()` method to store the input in a `String`.

Let's say we want to get an integer from the user. We could write something
like this then:

```java
int userInput = inputScanner.nextInt();
```

Let's put all this together in a simple class:

```java
import java.util.Scanner;

public class StudentGame {
    public static void main(String[] args) {
        System.out.println("Please enter a number:");
        Scanner inputScanner = new Scanner(System.in);
        int userNumber = inputScanner.nextInt();
        System.out.println("The user entered " + userNumber);
    }
}
```

If we run this program, we will get an output similar to this:

```plaintext
Please enter a number:
12
The user entered 12
```

If we wanted the user to enter in a `String`, then we could modify the program
to something like this:

```java
import java.util.Scanner;

public class StudentGame {
    public static void main(String[] args) {
        System.out.println("Please enter a phrase:");
        Scanner inputScanner = new Scanner(System.in);
        String userPhrase = inputScanner.nextLine();
        System.out.println("The user entered " + userPhrase);
    }
}
```

Now if we run it again with this adjustment, the output may look like this:

```plaintext
Please enter a phrase:
It's a great big beautiful tomorrow
The user entered It's a great big beautiful tomorrow
```
