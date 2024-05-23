# Lab 3: Debugging and Command-Line Tools

## Part 1: Debugging
For the purposes of this lab report, we will be using ArrayExamples.java as an example. 


### Failure-Inducing Input

**JUnit Test Case:**

```java
import static org.junit.Assert.*;
import org.junit.Test;

public class ArrayTests {
    @Test
    public void FailureInducingInput() {
        int[] newArr = {6,12,14,5,9,2};
        int[] input = {2,9,5,14,12,6};
        int[] expectedOutput = newArr;
        assertArrayEquals(expectedOutput, ArrayExamples.reversed(input));
    }
}

```
This test case provides an input array to the *reversed* method and expects the output to be the reversed version of the input. This input should induce a failure in the buggy program.
This is because 

### Non-Failure-Inducing Input

**JUnit Test Case:**

```java
import static org.junit.Assert.*;
import org.junit.Test;

public class ArrayTests {
    @Test
    public void testNonFailureInducingInput() {
        int[] input = {3, 7, 8};
        int[] expectedOutput = {8, 7, 3};
        ArrayExamples.reversed(input);
        assertArrayEquals(expectedOutput, input);
    }
}
```



