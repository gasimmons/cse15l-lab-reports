**Lab Report 4**

1. Log into ieng6

Keys Pressed:
```
ssh <space> cs15lfa23bj@ieng6.ucsd.edu <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%201.png)

To log into ieng6, a remote computer, I used the ssh command with my specific username, and I already had my remote key saved, so I did not have to put in a password.


2. Clone your fork of the repository from your Github account (using the SSH URL)

Keys Pressed:
  ```
  git <space> clone <space> <command v>(git@github.com:gasimmons/lab7.git) <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%202.png)

Prior I created a fork of the repository that I wanted to clone in, and I copied the repository. I then typed in the git clone command and pasted the link to the repository that I had previously copied and ran it by pressing enter to run the command and create the repository within the remote computer. 


3. Run the tests, demonstrating that they fail

Keys Pressed:
```  
  cd <space> lab7 <enter>
  <command v>(javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java) <enter>
  <command v>(java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore <space> ListExamplesTests <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%203.png)

Since I was in the home directory and needed to be in the lab7 directory, I used cd lab7 to get into it. From there I copied the command to compile all the files, and ran it using enter to compile everything. Finally I was able to run the commandds, again pasting the command to run the JUnit tests, but this time I also had to include the file ListExamplesTests, which contained the tests to run, then I clicked enter to run. The output was the results of the JUnit tests, in which two tests ran and one of which failed.


4. Edit the code file to fix the failing test

Keys Pressed:
  ```
  vim <space> ListExamples.java<enter>
  :44 <enter>
  <right><right><right><right><right> r 2
  :wq <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%204.png)

To fix the file to prevent it from failing the test, I used the vim command with the file that I wanted to edit, which was ListExamples.java, then I clicked enter to run. From previous trials trying to get my best time for this assignment, I knew the error was one line 44, so I used the command :44, to go to line 44. I then clicked the right arrow 5 times to put my cursor over the 1, clicked r to replace, and clicked 2 to replace the 1 with a 2. Since using replace puts you back into normal mode automatically, I just had to use :wq and then enter to save my changes and quit vim, returning me to the commmand line.


5. Run the tests, demonstrating that they now succeed

Keys Pressed:
  ```
  <up><up><up><enter>
  <up><up><up><enter>
  ```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%205.png)

To run the tests, showing that they work again, I repeated the commands from step 3, so I used the up arrow three times and clicked enter as the compile command was three up in the search history. Now that the files were compiled, I could again go up to the java command to run by using the up arrow three times as the command was three up in the search history again, and click enter on the run command. I know the tests succeeded because the output of running this command was two tests passing with an "OK".



6. Commit and push the resulting change to your Github account (you can pick any commit message!)

Keys Pressed:
```
  git <space> add <space> ListExamples.java <enter>
  git <space> commit <space> -m <space> "Index1 ---> Index2" <enter>
  git <space> push <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%206.png)

To commit and push the resulting change to my Github account, I need to do so in three steps. The first is using the git add command, with the file I edited, which is ListExamples.java, and then clicked enter to run it. This staged the changes to be ready for the next commit. The next step was git commit, and I added the -m with the message to avoid going into the vim editor again, and pressed enter. This commits the changes to Github, and displays the message for what I changed alongside it. Finally, I used git push and enter to upload the local repository to the remote repository. 

   
