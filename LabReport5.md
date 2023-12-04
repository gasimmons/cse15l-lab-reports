**Lab Report 5**

Part 1: Debugging Scenario

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Screenshot%202023-12-03%20at%2010.05.15%20PM.png)
1. Student: Hey, I keep getting these errors when I run my JUnit test, and the output seems to make me think that the merge method is adding everything to the beginning of the list, creating the reversed order.
The actual value at index 0 is always what I thought would be at the final index of the array. Could someone help to identify if this is the issue, and if so, how to fix it, thanks!

2. TA: Hey student, are you sure that the bug is caused by how the strings are added to the array, or could it be something else causing the bug, such as the comparison method?
Regardless, I am not able to look at and debug your code specifically, but I recommend using JDB to identify where the bug arises. Use JDB with the classpath to JUnit, on the ListExampleTests file, and set a break point at the merge method using stop in ListExample.merge.
Once you hit the breakpoint, you will be able to use the step command to execute the line, and you can use print result, to keep checking the value of result for when the error arises.
Knowing where the issue occurs will make it much easier to debug your own code, good luck!

3. Here is what I ran to find the bug in JDB:

Student: Thank you for the tip, using JDB and going step by step, I noticed that the merge method was sorting in almost reverse order because it was selecting for what came last alphabetically, not what came first, as X should not have been sorted first. 
Knowing this, I went to the line containing the comparator, and I was able to find the bug.
I had accidently used greater than instead of less than when comparing the two strings, which resulted in adding the string that came second alphabetically first, and then the strings that come first alphabetically later.

4. There are three files involved in this scenario, ListExamples, which contains the merge and filter methods, ListExamplesTests which contains JUnit tests for the previous file, and test.sh, which compiles each of the files and runs the tests.
   Each of the files are within the gavinsimmons/CSE15L/Lab7 directory, alongside the lib directory, which is also within Lab7, and contains the junit and hamcrest jar files.



Here all the files before fixing the bug:


The bug was triggered by running the command bash test.sh, which contains commands to compile and run the tests as seen below:



To fix the bug, since I knew the issue was that it was selecting the later of the two string alphabetically, I went to where the comparison was being made, and flipped the greater than sign to be a less sign.
Less than 0 instead of greater than 0 would cause it to only enter the if statement if string1 came before string2, which would then add string1 to results first, creating the desired results of adding the strings to results in alphabetical order.




Part 2: Reflection
I work in a bioinformatics/computer science lab on campus, so I have had a ton of experience with bash and java prior to taking this class, and most of it ended up being review for me, however one thing that was completely new to me was JDB. 
JDB makes debugging so much easier for me, as I no longer need to place print statements throughout my code trying to pinpoint just where the error is. 
Being able to view the value of a variable at any specific step is really cool and helpful, because it is essentially the same as the print statements just much easier and faster.
Despite having a bit of a learning curve, once I got the hang of JDB, I was able to use it making debugging so much less of a hassle, especially thanks to the step command which will pretty much alert you as soon as the bug appears. 
