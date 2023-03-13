<h1>Lab Report 5:</h1>
<h3><i>Based on Lab Report 3</i></h3>

We didn't cover <code>locate</code> in class, so I figured it could be an interesting command to explore. 

<h2>Default usage:</h2>

<img width="989" alt="image" src="https://user-images.githubusercontent.com/122490447/224842676-8cd93025-8f10-4a86-be16-688ba79813db.png">

The <code>locate</code> command uses a compressed database file containing file paths in order to return every file that matches parts of the specified pattern (that the user has read access to). It should be noted that when first executing <code>locate></code>, a prompt will be given to generate the compressed database file. The database is updated based on a cron job that, by default, runs every 24 hours. A cron job is a scheduled sort of command, in this case specific to macOS.

<h2>Options:</h2>

<h3><code>-l</code></h3>

<img width="989" alt="image" src="https://user-images.githubusercontent.com/122490447/224843155-97af5f1d-6731-4073-a8a3-2e4ad0c939cd.png">

Limits the number files outputted to the argument given following the -l option. This is useful when parsing for common patterns. Alternatively, the command output could be piped to less as follows:

<img width="735" alt="image" src="https://user-images.githubusercontent.com/122490447/224843716-b8fcc4e6-043d-4d74-9b97-387740e401b8.png">


Sources used:
https://linuxize.com/post/locate-command-in-linux/

<h3><code>-i</code></h3>

<img width="973" alt="image" src="https://user-images.githubusercontent.com/122490447/224844589-a7f89c69-8d7c-498c-83a3-a95629a534c1.png">

Ignores the case of the pattern, where any character in the pattern is interpreted as upper <b>and</b> lower case. Notice that files named:
<code>page.php</code> and <code>Page.php</code> are both outputted.

Sources used:
https://linuxize.com/post/locate-command-in-linux/

<h3><code>-c</code></h3>

<img width="726" alt="image" src="https://user-images.githubusercontent.com/122490447/224844870-7a9dde53-8b58-460c-b312-a3b5f51d80b3.png">

Outputs the number of files found matching the pattern inputted. This is helpful as it removes the need to pipe the output of <code>locate</code> out to <code>wc</code> to count the number of files. This less efficient piping method can be seen below:

<img width="726" alt="image" src="https://user-images.githubusercontent.com/122490447/224845353-d94799ea-b5f7-4078-ac88-71ed8f42a395.png">


Sources used:
https://linuxize.com/post/locate-command-in-linux/

<h3><code>-S</code></h3>

<img width="726" alt="image" src="https://user-images.githubusercontent.com/122490447/224845860-bf10f539-41a0-4fbd-89c1-e64fd952adf2.png">

Prints statistics and information about the compressed database file containing the file paths that are searched when the <code>locate</code> command is executed. This is especially helpful as it outputs the path of the database file, which can be shared as a representation of every file on a machine in a compressed form, which has practical applications, especially pertaining to virtual machines.

Sources used:
https://linuxize.com/post/locate-command-in-linux/

