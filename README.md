# Unit Testing Lab

## Learning Goals

- Write tests to check program logic.

## Introduction

In this lab, practice writing unit tests to check program logic.

Fork and clone this repository. When you do, you will see a file called
`BuggyLab.java` in the `java-unit-testing-lab/src/main/java` directory. You will
also see the `BuggyLabTest.java` in the `java-unit-testing-lba/src/test/java`
directory. All the unit testing will be written in the `BuggyLabTest` and all
the code that should be tested will be in `BuggyLab`.

## Instructions

There are two parts to this lab:

1. Writing the unit tests for the method `greaterThan()`.
2. Writing the unit tests and debugging a faulty method, `fizzBuzz()`.

Consider the starter code below in the `BuggyLab`:

```java
public class BuggyLab {

  public static boolean greaterThan(int leftOperand, int rightOperand) {
    return leftOperand > rightOperand;
  }

  public static String fizzBuzz(int number) {
    if (number % 3 == 0) {
      // if divisible by 3
      return "Fizz";
    } else if (number % 5 == 0) {
      // if divisible by 5
      return "Buzz";
    } else if ((number % 3 == 0) && (number % 5 == 0)) {
      // if divisible by both 3 and 5
      return "FizzBuzz";
    }
    else {
      // Will return a String object with the number as its value
      return Integer.toString(number);
    }
  }
}
```

### GreaterThan Unit Testing

Let's first practice writing unit tests!

Look at the `greaterThan()` method in the `BuggyLab`. This method takes two
`int` parameters and returns a `boolean`. It will compare the two integers to
see if the first parameter, `leftOperand`, is greater than the second parameter,
`rightOperand`.

We have already generated the test class, `BuggyLabTest`, for us to create our
unit tests.

- Write a unit test to test when the `greaterThan()` method should return a
  `false` value.
  - Remember, to call the methods in the `BuggyLab`, we have to use a syntax
    called dot-notation that looks like:
    `BuggyLab.greaterThan(leftOperand, rightOperand)`.
  - Use the `assertFalse()` method that you saw in the previous lesson.
- Write another unit test to test when the `greaterThan()` method should return
  a `true` value.
  - Use the `assertTrue()` method that you saw in the previous lesson.

Run each unit test case once you finish completing the above instructions. You
may also run the unit tests using the IntelliJ debugger, or you can use the Java
Visualizer tool to step through.

To run the debugger with unit tests, click on the play button next to the test
method you want to debug and choose "Debug":

![debug-single-test](https://curriculum-content.s3.amazonaws.com/java-mod-1/unit-tests/intellij-debug-unit-tests.png)

We could also debug all the tests in a specific test class by clicking the play
button next to `BuggyLabTest` and choosing "Debug":

![debug-all-tests](https://curriculum-content.s3.amazonaws.com/java-mod-1/unit-tests/intellij-debug-all-unit-tests.png)

The goal is for both test cases to pass:

![greater-than-tests-passing](https://curriculum-content.s3.amazonaws.com/java-mod-1/unit-tests/greater-than-tests-pass.png)

### FizzBuzz Unit Testing and Debugging

The `fizzBuzz()` method is a simplified version of the classic "FizzBuzz" logic
problem:

- Given an integer as a parameter:
  - If the integer is divisible by 3, return "Fizz".
  - If the integer is divisible by 5, return "Buzz".
  - If the integer is divisible by 3 and 5, return "FizzBuzz".
  - Else, return and print the integer.

This code has 1 bug! Write some unit tests to test the logic and find the bug
given the following steps:

1. Write a unit test to test the "_not_ divisible by 3 or 5" case.
   1. Remember, to call the methods in the `BuggyLab`, we have to use a syntax
      called dot-notation that looks like:
      `BuggyLab.fizzBuzz(number)`.
   2. Use the `assertEquals()` method that you saw in the previous lesson.
   3. A number that is not divisible by 3 or 5 could be 7.
   4. Remember, since the number is not divisible by 3 or 5, it will return
      the number as a `String`.
   5. This test should pass.
2. Write a unit test to test the "divisible by 3 only" case.
   1. A number that is divisible by only 3 could be 3.
   2. Remember, since the number is _only_ divisible by 3, it will return a
      `String` with a value of "Fizz".
   3. This test should pass.
3. Write a unit test to test the "divisible by 5 only" case.
   1. A number that is divisible by only 5 could be 5.
   2. Remember, since the number is _only_ divisible by 5, it will return a
      `String` with a value of "Buzz".
   3. This test should pass.
4. Write a unit test to test the "divisible by 3 and 5" case.
   1. A number that is divisible by 3 and 5 could be 15.
   2. Remember, since the number is divisible by _both_ 3 and 5, it will return
      a `String` with a value of "FizzBuzz".
   3. **This test will not pass**.

   ![unit-testing-lab-bug](https://curriculum-content.s3.amazonaws.com/java-mod-3/unit-testing-lab/unit-test-bug.png)

5. Fix the logic in the solution so that all 4 test cases pass.
   1. Use the Java Visualizer and/or the IntelliJ debugger to help isolate the
      bug.
   2. See the steps above in the "GreaterThan Unit Testing" section on how to
      run the debugger with unit tests.
   3. Once you have isolated the bug, make the appropriate fix and step through
      the code again to ensure it has been fixed.
   4. Run all 4 unit tests again and make sure each pass.

The goal is for all test cases to pass:

![fizzbuzz-tests-passing](https://curriculum-content.s3.amazonaws.com/java-mod-1/unit-tests/fizzbuzz-tests-passing.png)

## Expected Output

Make sure that all 6 tests are passing:

![tests-passing](https://curriculum-content.s3.amazonaws.com/java-mod-1/unit-tests/unit-test-lab-tests-passing.png)
