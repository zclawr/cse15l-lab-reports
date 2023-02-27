<h1>Lab Report 4</h1>
<h3>1. Log into ieng6</h3>
  
![image](https://user-images.githubusercontent.com/122490447/221680547-de1a9018-c457-4815-89dd-45cce897eaff.png)

```ssh cs15lwi23abs@ieng6.ucsd.edu <enter>```

Because the machine running these commands generated an SSH key and added it as an authenticated key to the ieng6 machine, no password entry is required!
<h3>2. Clone your fork of the repository from your Github account</h3>
  
![image](https://user-images.githubusercontent.com/122490447/221680711-a7f4975b-59ec-400a-89a8-f5b251968d08.png)

```git clone git@github.com:zclawr/lab7.git <enter>```

Because the GitHub account containing this repository had the ieng6 SSH key added to its authenticated keys, the <code>git clone</code> can be made without an HTTP request and with an SSH request instead.
<h3>3. Run the tests, demonstrating that they fail</h3>
  
![image](https://user-images.githubusercontent.com/122490447/221681360-05beaa9a-13c6-43a8-a9f1-c677e5479dc1.png)

```cd lab7/ <enter>```

```javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java <enter>```

```<up><ctrl+a><ctrl+right><backspace><ctrl+e><ctrl+w> org.junit.runner.JUnitCore ListExamplesTests <enter>```

After cloning we need to enter into the local repository's directory, and in order to run the tests the java files must be compiled and ran with some JUnit classpaths. Because these paths are the same for both the compiling and running of the tests, the up arrow is used to access the compiling command and some edits are made to the target file and command name, rather than typing out the full classpaths again.
<h3>4. Edit the code file to fix the failing test</h3>
  
![image](https://user-images.githubusercontent.com/122490447/221681663-0025ec9b-4390-40a0-a24b-3a1cd47a6485.png)

![image](https://user-images.githubusercontent.com/122490447/221681757-dec447fb-e5eb-46bc-b72f-ea00126c2384.png)

```nano ListExamples.java <enter>```

```<ctrl+v><up><up><up><up><up><up><up><ctrl+space><right><right><right><right><right><right><backspace> 2 <ctrl+o><enter><ctrl+x>```

In order to edit the file, we must <code>nano</code> into it, and edit the method causing issues, which in this case we know to be <code>merge()</code>. A series of special character inputs are made in order to navigate to the end of the file and to the correct line and word, in that order, with some efficiency. The edit is made, the changes are saved, and the file is exited.
<h3>5. Run the tests, demonstrating that they now succeed</h3>
  
![image](https://user-images.githubusercontent.com/122490447/221681807-06e83961-a0bb-4d9b-a12e-e238b2688cca.png)

```<up><up><up><enter>```

```<up><up><up><enter>```

Because the tests have already been compiled and ran before, both compiling and running commands can be accessed solely with the up arrow as no classpath or naming information has changed.
<h3>6. Commit and push the resulting change to your Github account (you can pick any commit message!)</h3>
  
![image](https://user-images.githubusercontent.com/122490447/221681990-1b788393-47c2-49ce-9a88-f4f3a7f6f03e.png)

```git add . <enter>```

```git commit -m"fixed files" <enter>```

```git push origin main <enter>```

The files are committed and pushed to GitHub as per usual, and the commit message can be whatever we choose.
