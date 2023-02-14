<h1>Lab Report 3</h1>
<h2>Command-line Options with <code>find</code></h2>
<h3><code>-type</code></h3>

```console
[cs15lwi23abs@ieng6-203]:written_2:134$ find . -type d    
.
./non-fiction
./non-fiction/OUP
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Berk
./non-fiction/OUP/Castro
./non-fiction/OUP/Fletcher
./non-fiction/OUP/Kauffman
./non-fiction/OUP/Rybczynski
./travel_guides
./travel_guides/berlitz1
./travel_guides/berlitz2
```
Finds all existing paths where there is a directory, which is indicated by the <code>d</code> argument following the <code>-type</code> option.

```console
[cs15lwi23abs@ieng6-203]:written_2:135$ find . -type f
./non-fiction/OUP/Abernathy/ch1.txt
./non-fiction/OUP/Abernathy/ch14.txt
./non-fiction/OUP/Abernathy/ch15.txt
./non-fiction/OUP/Abernathy/ch2.txt
./non-fiction/OUP/Abernathy/ch3.txt
./non-fiction/OUP/Abernathy/ch6.txt
./non-fiction/OUP/Abernathy/ch7.txt
./non-fiction/OUP/Abernathy/ch8.txt
./non-fiction/OUP/Abernathy/ch9.txt
./non-fiction/OUP/Berk/CH4.txt
./non-fiction/OUP/Berk/ch1.txt
./non-fiction/OUP/Berk/ch2.txt
./non-fiction/OUP/Berk/ch7.txt
...
```
Finds all existing paths where there is a file, which is indicated by the <code>f</code> argument following the <code>-type</code> option.

Sources:
  
https://man7.org/linux/man-pages/man1/find.1.html

<h3><code>-exec</code></h3>

```console
[cs15lwi23abs@ieng6-203]:written_2:145$ find . -name "*-History.txt" -exec rm -i {} \;
rm: remove regular file './travel_guides/berlitz2/Algarve-History.txt'? 
rm: remove regular file './travel_guides/berlitz2/Amsterdam-History.txt'? 
rm: remove regular file './travel_guides/berlitz2/Athens-History.txt'? 
rm: remove regular file './travel_guides/berlitz2/Bahamas-History.txt'? 
rm: remove regular file './travel_guides/berlitz2/Bali-History.txt'? 
rm: remove regular file './travel_guides/berlitz2/Barcelona-History.txt'?
...
```
Finds all existing paths given the prior options, in this case <code>-name</code>, and executes the argument following <code>-exec</code> as a command on each. 
In this case, the command to execute is <code>rm</code>, where the <code>-i</code> option prompts the user to agree to the removal of the file, and the <code>{} \;</code>
causes the command to execute for each file found, similar to <code>xargs</code>.
```console
[cs15lwi23abs@ieng6-203]:written_2:148$ find . -name "*-History.txt" -exec less {} \;
A Brief History
Little is known of the earliest Stone Age inhabitants of Europe<E2><80><99>s southwestern extremity. The ancient Greeks called them the Cynetes (or Cunetes). Whatever their origins, their cultu
re evolved under the pressure and influence of foreign forces. Among the many invading armies that settled here and contributed to nascent Portuguese culture were Phoenicians, who settled in th
e area around 1,000 b.c., followed by the Celts, Iberians, Greeks, and Carthaginians.
But it was the Romans, who arrived late in the third century b.c., who most greatly influenced all of Iberia. They built towns, industries, roads, and bridges, developed agriculture, and bequea
thed the Latin language, of which Portuguese is a direct descendant. The Romans named the southwestern province of the peninsula Lusitania, oddly enough for one of the Celtiberian tribes they d
efeated, and by the third century a.d. had introduced Christianity. By the beginning of the fourth century the Algarve had a bishop in place, based in Faro. But Rome had already fallen into dec
ay, and soon hordes of northern tribesmen took over the empire. The Algarve fell to the Visigoths in the mid-fifth century.
Under Moorish Rule
In a.d. 711, the Moors brought powerful armies from North Africa and launched a devastating attack on the Iberian peninsula, conquering much of what would become Spain and Portugal. They impose
d Islam and left an indelible influence on the countryside and the population of the Algarve. The Moorish legacy can still be seen in the form of wells and waterwheels, squat white houses, the 
dark complexions of the people, and in the very name given the region<C2><A0><E2><80><94><C2><A0>taken from Al-Gharb, which means <E2><80><9C>country of the west<E2><80><9D> (when the Moors con
quered the territory, it was the most westerly in the known world).
The Moors governed their Iberian kingdoms from across the border in Seville, but the Algarve had its own regional capital and huge, invulnerable fortress. The capital was Chelb (or Xelb), and i
t was bigger and better defended than Lisbon. Today the town, known as Silves, (see page 38) is a provincial outpost whose only besiegers are busloads of tourists who climb the narrow streets u
p to the old Moorish ramparts.
...
```
Finds all existing paths given the prior options, in this case <code>-name</code>, and executes the argument following <code>-exec</code> as a command on each. 
In this case, the command to execute is <code>less</code>, and the <code>{} \;</code> causes the command to execute for each file found, similar to <code>xargs</code>.

Sources:

https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

https://ss64.com/bash/rm.html
  
<h3><code>-fls</code></h3>

```console  
[cs15lwi23abs@ieng6-203]:written_2:149$ find . -name "*-History.txt" -fls history_files.txt
[cs15lwi23abs@ieng6-203]:written_2:150$ ls
history_files.txt  non-fiction  travel_guides
[cs15lwi23abs@ieng6-203]:written_2:151$ less history_files.txt 
221227548   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    15389 Feb  8 11:55 ./travel_guides/berlitz2/Algarve-History.txt
221227552   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    15758 Feb  8 11:55 ./travel_guides/berlitz2/Amsterdam-History.txt
221227556   28 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    20481 Feb  8 11:55 ./travel_guides/berlitz2/Athens-History.txt
221227560   20 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    16802 Feb  8 11:55 ./travel_guides/berlitz2/Bahamas-History.txt
221227564   20 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    16431 Feb  8 11:55 ./travel_guides/berlitz2/Bali-History.txt
221227567   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    13127 Feb  8 11:55 ./travel_guides/berlitz2/Barcelona-History.txt
221227570   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    12702 Feb  8 11:55 ./travel_guides/berlitz2/Beijing-History.txt
221227573   28 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    22126 Feb  8 11:55 ./travel_guides/berlitz2/Berlin-History.txt
221227580   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    12872 Feb  8 11:55 ./travel_guides/berlitz2/Budapest-History.txt
221227583   20 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    19139 Feb  8 11:55 ./travel_guides/berlitz2/California-History.txt
221227586   52 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    46093 Feb  8 11:55 ./travel_guides/berlitz2/Canada-History.txt
221227588   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    13919 Feb  8 11:55 ./travel_guides/berlitz2/CanaryIslands-History.txt
221227591   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    15364 Feb  8 11:55 ./travel_guides/berlitz2/Cancun-History.txt
221227594   36 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    29333 Feb  8 11:55 ./travel_guides/berlitz2/China-History.txt
221227597   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    16143 Feb  8 11:55 ./travel_guides/berlitz2/Costa-History.txt
221227600   12 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    11981 Feb  8 11:55 ./travel_guides/berlitz2/CostaBlanca-History.txt
221227602   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    15760 Feb  8 11:55 ./travel_guides/berlitz2/Crete-History.txt
221227606   12 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    11789 Feb  8 11:55 ./travel_guides/berlitz2/Cuba-History.txt
221227609   20 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    18933 Feb  8 11:55 ./travel_guides/berlitz2/Nepal-History.txt
221227612   28 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    20746 Feb  8 11:55 ./travel_guides/berlitz2/NewOrleans-History.txt
221227615   20 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    20387 Feb  8 11:55 ./travel_guides/berlitz2/Poland-History.txt
221227617   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    14604 Feb  8 11:55 ./travel_guides/berlitz2/Portugal-History.txt
221227620   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    13736 Feb  8 11:55 ./travel_guides/berlitz2/PuertoRico-History.txt
221227623   16 -rwxr-x---   1 cs15lwi23abs ieng6_cs15lwi23    14266 Feb  8 11:55 ./travel_guides/berlitz2/Vallarta-History.txt
```
Similar to <code>ls</code>, <code>fls</code> writes the results of <code>find</code> as a list of files into the file given as an argument, with additional information about each file.
This is helpful for getting a more broad overview of the file contents of a large directory, as permissions, date modified, and other properties can be viewed.
```console
[cs15lwi23abs@ieng6-203]:written_2:158$ find . -type d -fls directories.txt
[cs15lwi23abs@ieng6-203]:written_2:159$ ls
directories.txt  history_files.txt  non-fiction  portugal_files.txt  travel_guides
[cs15lwi23abs@ieng6-203]:written_2:160$ cat directories.txt 
221227376    4 drwxr-s---   4 cs15lwi23abs ieng6_cs15lwi23     4096 Feb 13 17:47 .
221227391    4 drwxr-s---   3 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./non-fiction
221227392    4 drwxr-s---   8 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./non-fiction/OUP
221227393    4 drwxr-s---   2 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./non-fiction/OUP/Abernathy
221227403    4 drwxr-s---   2 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./non-fiction/OUP/Berk
221227408    4 drwxr-s---   2 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./non-fiction/OUP/Castro
221227423    4 drwxr-s---   2 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./non-fiction/OUP/Fletcher
221227430    4 drwxr-s---   2 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./non-fiction/OUP/Kauffman
221227440    4 drwxr-s---   2 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./non-fiction/OUP/Rybczynski
221227444    4 drwxr-s---   4 cs15lwi23abs ieng6_cs15lwi23     4096 Feb  8 11:55 ./travel_guides
221227445    8 drwxr-s---   2 cs15lwi23abs ieng6_cs15lwi23     8192 Feb  8 11:55 ./travel_guides/berlitz1
221227547    8 drwxr-s---   2 cs15lwi23abs ieng6_cs15lwi23     8192 Feb  8 11:55 ./travel_guides/berlitz2
```  
Similar to <code>ls</code>, <code>fls</code> writes the results of <code>find</code> as a list of files into the file given as an argument, with additional information about each file.
In this case, by combining <code>fls</code> with <code>type</code>, which is discussed above, <code>fls</code> is helpful for understanding detailed properties of all of the subdirectories in a large directory.

Sources:

https://man7.org/linux/man-pages/man1/find.1.html
  
<h3><code>-maxdepth</code></h3>

```console  
[cs15lwi23abs@ieng6-203]:written_2:163$ find . -maxdepth 1 -type f
./history_files.txt
./portugal_files.txt
./directories.txt
```
The <code>-maxdepth</code> option forces the <code>find</code> command to only search <code>arg</code> subdirectory levels deep, where <code>arg</code> 
is the argument given to the option, in this case <code>1</code>. In this instance, because <code>1</code> was given as the argument, <code>find</code> 
only returns the files in the immediate subdirectory.
```console
[cs15lwi23abs@ieng6-203]:written_2:165$ find . -maxdepth 3 -type f
./travel_guides/berlitz1/HandRHawaii.txt
./travel_guides/berlitz1/HandRHongKong.txt
./travel_guides/berlitz1/HandRIbiza.txt
./travel_guides/berlitz1/HandRIsrael.txt
./travel_guides/berlitz1/HandRIstanbul.txt
./travel_guides/berlitz1/HandRJamaica.txt
./travel_guides/berlitz1/HandRJerusalem.txt
./travel_guides/berlitz1/HandRLakeDistrict.txt
./travel_guides/berlitz1/HandRLasVegas.txt
./travel_guides/berlitz1/HandRLisbon.txt
...
```  
The <code>-maxdepth</code> option forces the <code>find</code> command to only search <code>arg</code> subdirectory levels deep, where <code>arg</code> 
is the argument given to the option, in this case <code>3</code>. In this instance, because <code>3</code> was given as the argument, <code>find</code> 
returns the files up to the third subdirectory level.

Sources:

https://man7.org/linux/man-pages/man1/find.1.html
