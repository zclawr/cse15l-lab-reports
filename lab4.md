<h3>1. Log into ieng6<h3>
  
ssh cs15lwi23abs@ieng6.ucsd.edu ```<enter>```
  
<h3>2. Clone your fork of the repository from your Github account<h3>
  
git clone git@github.com:zclawr/lab7.git ```<enter>```
  
<h3>3. Run the tests, demonstrating that they fail<h3>
  
cd lab7/
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java ```<enter>```
```<up><ctrl+a><ctrl+right><backspace><ctrl+e><ctrl+w>``` org.junit.runner.JUnitCore TestListExamples ```<enter>```

<h3>4. Edit the code file to fix the failing test<h3>
  
nano ListExamples.java <enter>
```<ctrl+v><up><up><up><up><up><up><up><ctrl+space><right><right><right><right><right><right><backspace>```2```<ctrl+o><enter><ctrl+x>```

<h3>5. Run the tests, demonstrating that they now succeed<h3>
  
```<up><up><up><enter>```
```<up><up><up><enter>```
  
<h3>6. Commit and push the resulting change to your Github account (you can pick any commit message!)<h3>
  
git add . ```<enter>```
git commit -m"fixed files" ```<enter>```
git push origin main ```<enter>```
