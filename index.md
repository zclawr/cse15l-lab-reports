# Lab Report 1:

1.Look up your UCSD Student account at https://sdacs.ucsd.edu/~icc/index.php

2.Click the button beginning with cse15l, which will direct you to your CSE 15L class-specific account.

![image](https://user-images.githubusercontent.com/122490447/211925936-51e5161e-f1a2-42e3-8e0b-09342143405c.png)

3.Because this class-specific account does not carry over your UCSD Student account credentials, set a password if you have not already done so. If you would not like to reset your MyTritonLink campus-wide password, be sure to select no on that option via the dropdown pictured below. Regardless, the dropdown labelled: Change course-specific account passwords **MUST** be checked as yes.

![image](https://user-images.githubusercontent.com/122490447/211926451-45393696-9b8d-4be3-9a6c-0f50618a0e62.png)

4.Download and install Visual Studio Code if you do not already have it at https://code.visualstudio.com/.

5.Open Visual Studio Code, which should look similar to this page:

![image](https://user-images.githubusercontent.com/122490447/211929895-2cbe7da2-7fc4-4f2f-8fae-1136fe079fd7.png)

6.If you are on Windows, install git, which provides important bash-based terminal commands that we will use, at https://gitforwindows.org/

7.Go to Visual Studio Code and open a new terminal on it, either via (Ctrl or Cmd + `) or following the terminal dropdown option pictured below.

![image](https://user-images.githubusercontent.com/122490447/211927340-438d33cd-122a-494a-81ad-02028af5888a.png)

8.To connect to the ieng6 campus server, use the ssh command below, replacing the brackets and bracket-bounded content with your CSE 15L account-specific characters, pictured below as the last 3 characters in the username.
```
$ ssh cs15lwi23{YOUR ACCOUND-SPECIFIC CHARACTERS HERE}@ieng6.ucsd.edu
```
![image](https://user-images.githubusercontent.com/122490447/211927745-5219027d-face-43c0-bd01-5799bad43c29.png)

9.If this is your first time connecting to the server, you'll likely get a message asking about the authenticity of the server. Type yes.

10.You will be prompted to enter the password that you set for your CSE 15L course-specific account on step 3. Type in this password, and press enter (note that you will not be able to see the password as you are typing because it doesn't display characters for the field).

![image](https://user-images.githubusercontent.com/122490447/211930201-4316b466-bea3-4de6-bf70-798ac9888ba7.png)

11.You're now connected to the server! Try typing in a series of commands to navigate the remote directory. For starters, perhaps, try entering in pwd like the example below. Follow the link for a cheat sheet on common terminal commands to try, at https://www.educative.io/blog/bash-shell-command-cheat-sheet.

![image](https://user-images.githubusercontent.com/122490447/211930114-7f830a31-b73d-45eb-82da-07ccabe3fe85.png)
