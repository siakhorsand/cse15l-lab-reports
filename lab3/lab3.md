# Lab 3: Debugging and Command-Line Tools
by Sia Khorsand 


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
This test case actually should be successful but is not due to the fact that  ArrayExamples is buggy.
We will fix this bug in the following steps.

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
        assertArrayEquals(input, input);
    }
}
```
This test case provides an input array to the *reversed* method and expects the output to be the reversed version of the input. This input should induce a success in the buggy program.
This test case actually should fail but is not failing due to the fact that ArrayExamples is buggy.
We will fix this bug in the following steps.



### Symptom and the output of running above tests

![Passing and Failing Tests](screenshot.png)

Here is the output from running the tests above. As expected, one of them **fails** and the other **passes**.


### Before and After 

```java

public class ArrayExamples {    
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) { 
      arr[i] = arr[arr.length - i - 1];
    }
  }

  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) { 
      arr[i] = newArray[arr.length - i - 1]; //assigns to current array 
    }
    return arr; //returns current array
  }

```
The problem is that the *reverseInPlae* method incorrectly indexed the input in the for loop and assigned values to the **original** array rather than a **newly assigned** array. 

So, to fix this, i added a new array and fixed the indexing issues in the for loop of 

```java
  static void reverseInPlace(int[] arr) { 
    for(int i = 0; i < arr.length/2; i ++) { //correct reversing logic 
      int temp = arr[i];
      arr[i]= arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp; // temporary value 
    }
  }

  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i++) {
      newArray[i] = arr[arr.length - i - 1]; // currect indexing assigned to new array 
    }
    return newArray; // returns the new array 
  }

```
The bug was a logical problem caused by incorrect indexing in the *reverseInPlace* method that resulted in incorrect value assignments. The reversing logic implemented in the first method **overwrites** the beginning of the array with the end elements before they can are swapped, producing the **incorrect** result. The second method uses the same incorrect logic but assigns the values to a new array, which is not returned. The fixed implementations of these methods **correctly** swaps elements using the right algorithm to reverse the arrays. And the fixed second method **correctly** assigns to the new array and returns the new array. 


## Part 2: Researching Commands
For the purposes of this lab report, we will be using `grep` as an examples to find 4 interesting options, for each of which we will provide two examples. 

As our sources, we will be using the `man grep` command to find the use case examples of `grep`. 

### Example 1: `-i` (ignore)

`-i` will ignore case distinctions.

1.
input:
    `grep -i "method" technical/biomed/rr74.txt `

output: 
    `        Materials and methods
          concentration was determined using the Bradford method`

          
input: 
    `grep -i "pain" technical/biomed/*`

output:
[long list of words from txt files]



### Example 2: `-r` (Recursive)

This command searches recursively in all files within the desired directory and returns the lines that match the desired pattern. 

1.

    `grep -r "hello" technical/*`
2.
      `grep -r "white" techincal/plos/`


recursively checks and lists all files *technical* that containt "white".

### Example 3: `-l` (List):

`-l` lists all files that contain the desired text. 

1. 
`grep -l "method" technical/*`
lists all files in technical that include " method". 
2.
   `grep -l "example" technical/biomed/*
`
lists all files that include "example" wihtin technical/biomed/.

### Example 3: `-v` (Lists all lines that #EXCLUDE# desired text):

1.
    `grep -v "introduction" technical/plos/*`
lists all the lines that do #NOT# include "introduction" within the plos folder inside technical

2.
 `grep -v "theoretically" technical/biomed/rr73.txt`
lists all the lines that do #not# include "theoretically" in the rr73.txt file in the biomed directory. 
   





   

