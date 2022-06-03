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

Java comes with utility classes that implement common functionality. For
example, the `Math` class has methods for standard math operations, such as the
`abs()` method that returns the absolute value of a number.

The class that has the functionality we are interested in to get input from the
user is the `Scanner` class. It's in a `package` called `java.util`. We will
explain Java packages in more detail in another unit, but for now you can think
of Java packages as folders that help us organize our Java classes, so that they
don't all end up in the same single place.

To use another class inside your own class, you have to "import" it, using the
`import` keyword. So we need to import the `Scanner` class, which is in the
`java.util` package as follows:

```java
import java.util.Scanner;
```

Once we've imported the class we need, we can use it anywhere in our class by
declaring a variable of that type:

```java
Scanner myScanner;
```

The functionality of the Scanner class is to allow it to read input from a
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
the terminal using the `nextInt()` method, if the input we are wanting from the
user will be a number:

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

Run this program, and you will get output similar to this:

```plaintext
Please enter a number:
12
The user entered 12
```
