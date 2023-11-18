**Lab Report 4**

1. Log into ieng6

Keys Pressed:
```
ssh <space> cs15lfa23bj@ieng6.ucsd.edu <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%201.png)

2. Clone your fork of the repository from your Github account (using the SSH URL)

Keys Pressed:
  ```
  git <space> clone <space> <command v>(git@github.com:gasimmons/lab7.git) <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%202.png)

3. Run the tests, demonstrating that they fail

Keys Pressed:
```  
  cd <space> lab7
  <command v>(javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java) <enter>
  <command v>(java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore <space> ListExamplesTests <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%203.png)

4. Edit the code file to fix the failing test

Keys Pressed:
  ```
  vim ListExamples.java<enter>
  :44 <enter>
  <right><right><right><right><right> r2 <esc>
  :wq <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%204.png)

5. Run the tests, demonstrating that they now succeed

Keys Pressed:
  ```
  <up><up><up><enter>
  <up><up><up><enter>
  ```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%205.png)


6. Commit and push the resulting change to your Github account (you can pick any commit message!)

Keys Pressed:
```
  git <space> add <space> ListExamples.java <enter>
  git <space> commit <space> -m <space> "Index1 ---> Index2" <enter>
  git <space> push <enter>
```

![](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Step%206.png)

   
