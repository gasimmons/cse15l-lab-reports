**Lab Report 3**

Part 1 Bugs: 

Original Code:
```java
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

Failure Inducing Input:
```java
@Test
  public void testReverseInPlace2() {
    int[] input = {1, 2, 3};
    ArrayExamples.reverseInPlace(input);
    //System.out.println(Arrays.toString(input));
    assertArrayEquals(new int[] {3, 2, 1}, input);
  }
```
This test would fail, as the input's original values are overwritten while the reversal is being performed, causing it to mirror the latter half of the input. 


Input that does not Induce Failure: 
```java
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3, 3, 3 };
    ArrayExamples.reverseInPlace(input1);
    //System.out.println(Arrays.toString(input1));
    assertArrayEquals(new int[]{ 3, 3, 3}, input1);
	}
```
Despite the incorrect implementation of the method being tested, this test would pass as the original input contains all the same values. Since the implementation mirrors the latter half of the input, and the first half and second half are identical, the method outputs an array with all the same values, identical to the input, and the expected output. 

The Symptom:
![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/RunJUnit.png)
The symptom revealing the error in the implementation is the one failed JUnit test, meaning that something is wrong in how the array was being reversed, and the expected output was not reached.

Incorrect, Original Implementation:
```java
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

Correct Implementation:
```java
static void reverseInPlace(int[] arr) {
    int length = arr.length;
    for(int i = 0; i < length / 2; i++) {
      int temp = arr[i];
      arr[i] = arr[length - i - 1];
      arr[length - i - 1] = temp;
    }
  }
```
The bug in the original code is that when it is looping through the array, it overwrites the beginning element, so when it goes to replace the ending element, it just replaces it with itself. This causes it to mirror the second half of the input array, so {1, 2, 3, 4,5} becomes {5, 4, 3, 4, 5}. I fixed it by dividing the for loop by two, then swapping the element at the beginning and the end by using a temp variable to hold the original beginning index. The swap would then occur, with the temp variable being used to prevent the beginning from being overwritten, then the for loop moves forward one element, which is to be swapped with one before the last element and so on. Overall, this fixes the implementation, and successfully reverses the array, which we know because both of the JUnit tests pass this time.



Part 2 Researching Grep Commands: 

1. grep -v

![grep -v 1](grep-v1.png)
Grep -v is an invert matcher, meaning that it searches and displays the lines that do not contain the pattern input into the command. In this example it is displaying all of the lines that do not contain the word "smoking". This could be useful for finding lines that do not contain a certain keyword, or even for removing in line comments in code by searching for "//".

![grep -v 2](grep-v2.png)
Grep -v, the invert matcher, searches and displays all the lines that do nto contain the pattern from the command. In this example, it displays all the lines that do not contain the phrase "hepatitis C", showing that it works for phrases, and is case sensitive. This could be useful paired with the recursive -r command, so that you could display all the files that do not contain a certain pattern. 

2. grep -c

![grep -c 1](grep-c1.png)
Grep -c is a command that only returns the number of lines that the pattern is present in. In this example, it returns the number of lines that the phrase "breast cancer" is present in. This could be useful for figuring out whether a file has relevant information or not searching for a keyword and checking the number of lines it is present. 

![grep -c 2](grep-c2.png)
Grep -c counts the number of lines that the pattern is present. In this example, it returns 0 because the pattern "Daniel Caeser" is not present in any of the lines. This command could also be used along with other commands, for example -v, in which it would count all the lines that do not contain a phrase, which is useful for determining the relevance of the information within a file. 

3. grep -n

![grep -n 1](grep-n1.png)
Grep -n acts just like grep except it also prints out the line number at which each line with the pattern. In this example, the line and the line number is displayed for every line that has the word "cigarette". This could be useful when searching for any keyword within a file, so that you can go into the file and edit at each of those points.

![grep -n 2](grep-n2.png)
Grep -n displays all the lines that contain the pattern, while also including the line number associated with those lines. In this example, nothing is returned because "Marvin Gaye" is not present in the file. This tool would be especially useful when dealing with large data files, so that you can easily find something of interest, and be able to go in a validate it.

4. grep -i 

![grep -i 1](grep-i1.png)
Grep -i acts just like the regular grep command, but it ignores capitalization. In this example, it displays the lines that contain the word "female" regardless of capitalization. This can be useful for finding keywords regardless of if they are capitalized or not.

![grep -i 2](grep-i2.png)
Grep -i displays all the lines that contain the pattern, regardless of capitalization. In this example, it returns all the lines that contain the word "protein" whether capitalized or not. This could be useful as it provides a more comprehensive list of lines, that will not miss out on any instances due to capitalization.

Source: 
[Man7.org](https://man7.org/linux/man-pages/man1/grep.1.html)

