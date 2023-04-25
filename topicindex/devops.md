# Introduction
DevOps is a set of practices, tools, and a cultural philosophy that automate and integrate the processes between software development and IT teams.
# OS Concepts
## Process Management
Process management involves various tasks like creation, scheduling, termination of processes, and a dead lock.
Process is a program that is under execution, which is an important part of modern-day operating systems. 
The OS must allocate resources that enable processes to share and exchange information
## Therads & Concurrency
Concurrency is the execution of the multiple instruction sequences at the same time. 
It happens in the operating system when there are several process threads running in parallel. 
The running process threads always communicate with each other through shared memory or message passing.
## sockets
A socket is one endpoint of a two way communication link between two programs running on the network. 
The socket mechanism provides a means of inter-process communication (IPC) by establishing named contact points between 
which the communication take place.
## POSIX BASICS
The Portable Operating System Interface (POSIX) is a family of standards specified by the IEEE Computer Society
for maintaining compatibility between operating systems.[1] POSIX defines both the system- and 
user-level application programming interfaces (API), along with command line shells and utility interfaces, 
for software compatibility (portability) with variants of Unix and other operating systems.[1][2] 
POSIX is also a trademark of the IEEE.[1] POSIX is intended to be used by both application and system developers
## Networking Concetps
## Starup Management(Intid)
All these service works on several scripts and these scripts are stored in /etc/init.d location, 
this init.d is a daemon which is the first process of the Linux system. Then other processes, services, daemons, and threads are started by init.
So init.d is a configuration database for the init process. Now let’s check some daemon scripts by printing some processes,
a daemon script holds functions like start, stop, status, and restart. Let’s check ssh as an example.
> cat /etc/init.d/ssh
- [link1](https://www.geeksforgeeks.org/what-is-init-d-in-linux-service-management/)
- [link2](https://www.tecmint.com/systemd-replaces-init-in-linux/)
## Service Management(Systemd)
A systemd is a System Management Daemon named with UNIX convention to add ‘d‘ at the end of daemon. 
So, that they can be easily recognized. Initially it was released under GNU General Public License,
but now the releases are made under GNU Lesser General Public License. Similar to init,
systemd is the parent of all other processes directly or indirectly and is the first process that starts at boot hence typically assigned a “pid=1“.
- [link1](https://www.tecmint.com/systemd-replaces-init-in-linux/)
## I-O Management
I/O Requests are managed by Device Drivers in collaboration with some system programs inside the I/O device. The requests are served by OS using three simple segments 
* I/O Traffic Controller : Keeps track of the status of all devices, control units, and communication channels.
* I/O scheduler : Executes the policies used by OS to allocate and access the device, control units, and communication channels.
* I/O device handler : Serves the device interrupts and heads the transfer of data.
## Virtualization
OS virtualization is the use of software to allow a piece of hardware to run multiple operating system images at the same time
## Memory Storage
When an operating system manages the computer's memory, there are two broad tasks to be accomplished:

Each process must have enough memory in which to execute, and it can neither run into the memory space of another process nor be run into by another process.
The different types of memory in the system must be used properly so that each process can run most effectively.
Disk storage is only one of the memory types that must be managed by the operating system, and it's also the slowest. Ranked in order of speed, the types of memory in a computer system are:

* High-speed cache: This is fast, relatively small amounts of memory that are available to the CPU through the fastest connections. Cache controllers predict which pieces of data the CPU will need next and pull it from main memory into high-speed cache to speed up system performance.
* Main memory: This is the RAM that you see measured in gigabytes when you buy a computer.
* Secondary memory: This is often a hard drive (HDD) or solid state drive (SSD) inside the computer which serves as virtual RAM under the control of the operating system.
- [link1](https://computer.howstuffworks.com/operating-system7.htm)
## File systems
A file is a collection of related information that is recorded on secondary storage. Or file is a collection of logically related entities. From user’s perspective a file is the smallest allotment of logical secondary storage. 
The name  of the file is divided into two parts as shown below:
* name
* extension, separated by a period.
- [link1](https://www.geeksforgeeks.org/file-systems-in-operating-system/)
# Operating system
Its(a software) interface between the user and Hardware, which performs
* Filemanagement
* Memory Management
* Process Management
* handling input and ouput
* Peripheral devices like harddisks,printers
- [link1](https://github.com/ag143/Json/blob/main/devops/OsConcepts.md)
## Linux
Just like Windows, iOS, and Mac OS, Linux is an operating system. In fact, one of the most popular platforms on the planet, Android, is powered by the Linux operating system. An operating system is software that manages all of the hardware resources associated with your desktop or laptop. To put it simply, the operating system manages the communication between your software and your hardware. Without the operating system (OS), the software wouldn’t function.
The Linux operating system comprises several different pieces:

* Bootloader –  The software that manages the boot process of your computer. For most users, this will simply be a splash screen that pops up and eventually goes away to boot into the operating system.
* Kernel – This is the one piece of the whole that is actually called ‘Linux’. The kernel is the core of the system and manages the CPU, memory, and peripheral devices. The kernel is the lowest level of the OS.
* Init system – This is a sub-system that bootstraps the user space and is charged with controlling daemons. One of the most widely used init systems is systemd, which also happens to be one of the most controversial. It is the init system that manages the boot process, once the initial booting is handed over from the bootloader (i.e., GRUB or GRand Unified Bootloader).
* Daemons – These are background services (printing, sound, scheduling, etc.) that either start up during boot or after you log into the desktop.
* Graphical server – This is the sub-system that displays the graphics on your monitor. It is commonly referred to as the X server or just X.
* Desktop environment – This is the piece that the users actually interact with. There are many desktop environments to choose from (GNOME, Cinnamon, Mate, Pantheon, Enlightenment, KDE, Xfce, etc.). Each desktop environment includes built-in applications (such as file managers, configuration tools, web browsers, and games).
* Applications – Desktop environments do not offer the full array of apps. Just like Windows and macOS, Linux offers thousands upon thousands of high-quality software titles that can be easily found and installed. Most modern Linux distributions (more on this below) include App Store-like tools that centralize and simplify application installation. For example, Ubuntu Linux has the Ubuntu Software Center (a rebrand of GNOME Software) which allows you to quickly search among the thousands of apps and install them from one centralized location.
- [link1](https://www.linux.com/what-is-linux/)
### SUSE Linux
SUSE Linux is a computer operating system developed by SUSE
- [link1](https://en.wikipedia.org/wiki/SUSE_Linux)
### Debian
Debian (/ˈdɛbiən/),[5][6] also known as Debian GNU/Linux, is a Linux distribution composed of free and open-source software, developed by the community-supported Debian Project
- [link](https://en.wikipedia.org/wiki/Debian
// ### Fedora
### Ubuntu
Ubuntu Desktop is a Linux distribution developed by Canonical, and it’s one of the most popular distributions, thanks to its ease of use. It’s also one of the top choices for people who are getting started with Linux. The server edition, which we won’t be focusing on here, is also operating in the majority of internet servers.
- [link](https://www.howtogeek.com/763775/what-is-ubuntu/
### Centos
The CentOS Project
Community-driven free software effort focused around the goal of providing a rich base platform for open source communities to build upon.
- [link](https://www.centos.org/
### RHEL
Red Hat Enterprise Linux (RHEL) is a commercial open-source Linux distribution developed by Red Hat for the commercial market.
- [link](https://en.wikipedia.org/wiki/Red_Hat_Enterprise_Linux
## Unix
### FreeBSD
- [link](https://www.geeksforgeeks.org/difference-between-linux-and-freebsd/)
### OpenBSD
- [link](https://www.geeksforgeeks.org/difference-between-windows-and-openbsd/)
### NetBSD
- [link](https://www.geeksforgeeks.org/difference-between-windows-and-netbsd/)
## Windows
Microsoft Windows (also referred to as Windows or Win) is a graphical operating system developed and published by Microsoft. It provides a way to store files, run software, play games, watch videos, and connect to the Internet.
- [link](https://www.computerhope.com/jargon/w/windows.htm
# Managingservers
# Terminal
## Text maniputlation Tools
### awk
1. AWK Operations: 
- (a)Scans a file line by line 
- (b)Splits each input line into fields 
- (c) Compares input line/fields to pattern 
- (d) Performs action(s) on matched lines 

2. Useful For: 
- (a) Transform data files 
- (b) Produce formatted reports 

3. Programming Constructs: 
- (a) Format output lines 
- (b) Arithmetic and string operations 
- (c) Conditionals and loops 

```
ajay manager account 45000
sunil clerk account 25000
varun manager sales 50000
amit manager account 47000
tarun peon sales 15000
deepak clerk sales 23000
sunil peon sales 13000
satvik director purchase 80000 
```

1. Default behavior of Awk
> $ awk '{print}' employee.txt

2. Print the lines which match the given pattern. 
> $ awk '/manager/ {print}' employee.txt 

3. Splitting a Line Into Fields
> $ awk '{print $1,$4}' employee.txt 

- NR: NR command keeps a current count of the number of input records. Remember that records are usually lines. Awk command performs the pattern/action statements once for each record in a file. 
- NF: NF command keeps a count of the number of fields within the current input record. 
- FS: FS command contains the field separator character which is used to divide fields on the input line. The default is “white space”, meaning space and tab characters. FS can be reassigned to another character (typically in BEGIN) to change the field separator. 
- RS: RS command stores the current record separator character. Since, by default, an input line is the input record, the default record separator character is a newline. 
- OFS: OFS command stores the output field separator, which separates the fields when Awk prints them. The default is a blank space. Whenever print has several parameters separated with commas, it will print the value of OFS in between each parameter. 
- ORS: ORS command stores the output record separator, which separates the output lines when Awk prints them. The default is a newline character. print automatically outputs the contents of ORS at the end of whatever it is given to print. 

3.1. Use of NR built-in variables (Display Line Number)  
> $ awk '{print NR,$0}' employee.txt 

3.2. Use of NF built-in variables (Display Last Field) 
> $ awk '{print $1,$NF}' employee.txt 

3.3. Another use of NR built-in variables (Display Line From 3 to 6)  
> $ awk 'NR==3, NR==6 {print NR,$0}' employee.txt 

1) To print the first item along with the row number(NR) separated with ” – “ from each line in geeksforgeeks.txt:  
> $ awk '{print NR "- " $1 }' geeksforgeeks.txt 

2) 2) To return the second column/item from geeksforgeeks.txt: 
> $ awk '{print $2}' geeksforgeeks.txt 

3) To print any non empty line if present  
> $ awk 'NF < 0' geeksforgeeks.txt

4) To find the length of the longest line present in the file:  
> $ awk '{ if (length($0) > max) max = length($0) } END { print max }' geeksforgeeks.txt

5) To count the lines in a file:  
> $ awk 'END { print NR }' geeksforgeeks.txt 
> 3

6) Printing lines with more than 10 characters:  
> $ awk 'length($0) > 10' geeksforgeeks.txt 

7) To find/check for any string in any specific column:  
> $ awk '{ if($3 == "B6") print $0;}' geeksforgeeks.txt

8) To print the squares of first numbers from 1 to n say 6:  
> $ awk 'BEGIN { for(i=1;i<=6;i++) print "square of", i, "is",i*i; }' 

- [link](https://www.geeksforgeeks.org/awk-command-unixlinux-examples/)

### sed
SED command in UNIX stands for stream editor and it can perform lots of functions on file like searching, find and replace, insertion or deletion
> testfile
```
unix is great os. unix is opensource. unix is free os.
learn operating system.
unix linux which one you choose.
unix is easy to learn.unix is a multiuser os.Learn unix .unix is a powerful.
```

- Replacing or substitute string
> $ sed 's/unix/linux/' geekfile.txt

- Replacing the nth occurrence of a pattern in a line
> $sed 's/unix/linux/2' geekfile.txt

- Replacing all the occurrence of the pattern in a line
> $sed 's/unix/linux/g' geekfile.txt

- Replacing from nth occurrence to all occurrences in a line
> $sed 's/unix/linux/3g' geekfile.txt

- Parenthesize first character of each word 
> $ echo "Welcome To The Geek Stuff" | sed 's/\(\b[A-Z]\)/\(\1\)/g'
> (W)elcome (T)o (T)he (G)eek (S)tuff

- Replacing string on a specific line number
> $sed '3 s/unix/linux/' geekfile.txt
 
- Duplicating the replaced line with /p flag
> $sed 's/unix/linux/p' geekfile.txt
 
- Printing only the replaced lines
> $sed -n 's/unix/linux/p' geekfile.txt
 
- Replacing string on a range of lines
> $sed '1,3 s/unix/linux/' geekfile.txt
 
- Deleting lines from a particular file
> $ sed '5d' filename.txt
 
- To Delete a last line
> $ sed '$d' filename.txt
 
- To Delete line from range x to y
> $ sed '3,6d' filename.txt

- [link](https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/)
### grep
The grep filter searches a file for a particular pattern of characters, and displays all lines that contain that pattern
1. Case insensitive search
> $grep -i "UNix" geekfile.txt

2. Displaying the count of number of matches
> $grep -c "unix" geekfile.txt

3. Display the file names that matches the pattern
>  $grep -l "unix" *
>  $grep -l "unix" f1.txt f2.txt f3.xt f4.txt

4. Checking for the whole words in a file
> $ grep -w "unix" geekfile.txt

5. Displaying only the matched pattern 
> $ grep -o "unix" geekfile.txt

6. Show line number while displaying the output using grep -n
> $ grep -n "unix" geekfile.txt

7. Inverting the pattern match
> $ grep -v "unix" geekfile.txt

8. Matching the lines that start with a string
> $ grep "^unix" geekfile.txt

9. Matching the lines that end with a string
> $ grep "os$" geekfile.txt

10. Specifies expression with -e option. Can use multiple times
> $grep –e "Agarwal" –e "Aggarwal" –e "Agrawal" geekfile.txt

11.  -f file option Takes patterns from file, one per line.
> $cat pattern.txt

12.  Print n specific lines from a file:  
> $grep -A[NumberOfLines(n)] [search] [file]
> $grep -B[NumberOfLines(n)] [search] [file]  
> $grep -C[NumberOfLines(n)] [search] [file]  
> $grep -A1 learn geekfile.txt

13.  Search recursively for a pattern in the directory
> $grep -iR geeks /home/geeks

- [link](https://www.geeksforgeeks.org/grep-command-in-unixlinux/?ref=lbp)

### sort
SORT command is used to sort a file, arranging the records in a particular order. By default, the sort command sorts file assuming the contents are ASCII. 
```
abhishek
chitransh
satish
rajan
naveen
divyam
harsh
```

- Sorting a file: Now use the sort command 
> $ sort filename.txt

- Sort function with mix file i.e. uppercase and lower case:
> $ sort mix.txt

- Options with sort function:
- 1. -o Option:
> $ sort inputfile.txt > filename.txt
> $ sort -o filename.txt inputfile.txt

- 2. -r Option: Sorting In Reverse Order
> $ sort -r inputfile.txt

3. -n Option:
> $sort -n filename.txt

4. -nr option
>  $sort -nr file1.txt

5. -k Option
> $sort -k filename.txt

6. -c option
> $ sort -c filename.txt

7. -u option: To sort and remove duplicates 
> $ sort -u filename.txt

8. -M Option: To sort by month pass the -M option to sort
> $ sort -M filename.txt


- [link](https://www.geeksforgeeks.org/sort-command-linuxunix-examples/?ref=lbp)
### uniq
The uniq command in Linux is a command-line utility that reports or filters out the repeated lines in a file. 
```
$cat kt.txt
I love music.
I love music.
I love music.

I love music of Kartik.
I love music of Kartik.

Thanks.
```
> $uniq kt.txt
- -c – -count : It tells how many times a line was repeated by displaying a number as a prefix with the line.
- -d – -repeated : It only prints the repeated lines and not the lines which aren’t repeated.
- -D – -all-repeated[=METHOD] : It prints all duplicate lines and METHOD can be any of the following: 
- none : Do not delimit duplicate lines at all. This is the default.
- prepend : Insert a blank line before each set of duplicated lines.
- separate : Insert a blank line between each set of duplicated lines.
- -f N – -skip-fields(N) : It allows you to skip N fields(a field is a group of characters, delimited by whitespace) of a line before determining the uniqueness of a line.
- -i – -ignore case : By default, comparisons done are case sensitive but with this option case insensitive comparisons can be made.
- -s N – -skip-chars(N) : It doesn’t compare the first N characters of each line while determining uniqueness. This is like the -f option, but it skips individual characters rather than fields.
- -u – -unique : It allows you to print only unique lines.
- -z – -zero-terminated : It will make a line end with 0 bytes (NULL), instead of a newline.
- -w N – -check-chars(N) : It only compares N characters in a line.
- – – help : It displays a help message and exit.
- – – version : It displays version information and exit.
- [link](https://www.geeksforgeeks.org/uniq-command-in-linux-with-examples/?ref=lbp)
### cat
Cat(concatenate) command is very frequently used in Linux. It reads data from the file and gives their content as output. It helps us to create, view, concatenate files.
- [link](https://www.geeksforgeeks.org/cat-command-in-linux-with-examples/?ref=rp)
### cut
The cut command in UNIX is a command for cutting out the sections from each line of files and writing the result to standard output.
```
Andhra Pradesh
Arunachal Pradesh
Assam
Bihar
Chhattisgarh
```

1) List without ranges
> $ cut -b 1,2,3 state.txt

2) List with ranges
> $ cut -b 1-3,5-7 state.txt

3) In this, 1- indicate from 1st byte to end byte of a line
> $ cut -b 1- state.txt

4) In this, -3 indicate from 1st byte to 3rd byte of a line
> $ cut -b -3 state.txt

5) 2. -c (column): To cut by character use the -c option
> $ cut -c 2,5,7 state.txt
> $ cut -c 1-7 state.txt
> $ cut -c 1- state.txt
> $ cut -c -5 state.txt

6) 3. -f (field): -c option is useful for fixed-length lines
> $ cut -f 1 state.txt

- If -d option is used then it considered space as a field separator or delimiter:
> $ cut -d " " -f 1 state.txt

- Command prints field from first to fourth of each line from the file.
> $ cut -d " " -f 1-4 state.txt

4. –complement:
> $ cut --complement -d " " -f 1 state.txt
> $ cut --complement -c 5 state.txt

5. –output-delimiter: 
> $ cut -d " " -f 1,2 state.txt --output-delimiter='%'

6. –version:
$ cut --version

1. How to use tail with pipes(|):
> $ cat state.txt | cut -d ' ' -f 1 | sort -r
> $ cat state.txt | head -n 3 | cut -d ' ' -f 1 > list.txt

- [link](https://www.geeksforgeeks.org/cut-command-linux-examples/?ref=lbp)
### echo
- [link](https://www.geeksforgeeks.org/echo-command-in-linux-with-examples/#:~:text=echo%20command%20in%20linux%20is,the%20screen%20or%20a%20file.&text=In%20above%20example%2C%20text%20after,and%20omitted%20trailing%20new%20line.)
### fmt
- [link](https://www.geeksforgeeks.org/fmt-command-unixlinux/)
### tr
The tr command in UNIX is a command line utility for translating or deleting characters. It supports a range of transformations including uppercase to lowercase, squeezing repeating characters, deleting specific characters and basic find and replace. It can be used with UNIX pipes to support more complex translation
> $ tr [OPTION] SET1 [SET2]
- [link](https://www.geeksforgeeks.org/tr-command-in-unix-linux-with-examples/?ref=lbp)
### nl
- [link](https://www.geeksforgeeks.org/nl-command-in-linux-with-examples/)
### egrep
- [link](https://www.geeksforgeeks.org/egrep-command-in-linux-with-examples/)
### fgrep
- [link](https://www.geeksforgeeks.org/fgrep-command-in-linux-with-examples/)
### wc
> $ ls gfg | wc -l
> $ wc -w  state.txt | cut -c1
> or $ wc -w < state.txt
- [link](https://www.geeksforgeeks.org/wc-command-linux-examples/)

## Process Monitoring
### ps
Linux provides us a utility called ps for viewing information related with the processes on a system which stands as abbreviation for “Process Status”
- [link](https://www.geeksforgeeks.org/ps-command-in-linux-with-examples/)
### top
top command is used to show the Linux processes. It provides a dynamic real-time view of the running system.
- [link](https://www.geeksforgeeks.org/top-command-in-linux-with-examples/)
### htop
- [link](https://www.geeksforgeeks.org/htop-command-in-linux-with-examples/#:~:text=htop%20command%20in%20Linux%20system,many%20improvements%20over%20top%20command.)
### atop
- [link](https://www.geeksforgeeks.org/installing-atop-tool-to-monitor-the-system-process-in-linux/)
### lsof
lsof command stands for List Of Open File. This command provides a list of files that are opened. Basically, it gives the information to find out the files which are opened by which process. With one go it lists out all open files in output console.
- [link](https://www.geeksforgeeks.org/lsof-command-in-linux-with-examples/)
## Network
### nmap
- [link](https://www.geeksforgeeks.org/nmap-command-in-linux-with-examples/)
### tcpdump
- [link](https://www.geeksforgeeks.org/tcpdump-command-in-linux-with-examples/)
### ping
- [link](https://www.geeksforgeeks.org/what-is-ping/)
### mtr
- [link](https://www.javatpoint.com/linux-mtr)
### traceroute
- [link](https://www.geeksforgeeks.org/traceroute-command-in-linux-with-examples/)
### dig
- [link](https://www.geeksforgeeks.org/dig-command-in-linux-with-examples/)
### airmon
- [link](https://linuxhint.com/airmon-ng_kali_linux/)
### airodump
- [link](https://www.aircrack-ng.org/doku.php?id=airodump-ng)
### iptables
- [link](https://www.geeksforgeeks.org/iptables-command-in-linux-with-examples/)
### netstat
- [link](https://www.geeksforgeeks.org/netstat-command-linux/)
## (bash)shell scripting
- [link](https://github.com/ag143/shellscript)
## Editors
### Vim
- [link](https://www.educba.com/vim-command-in-linux/)
### Nano
- [link](https://www.nano-editor.org/dist/v2.2/nano.html)
### powershell
- [link](https://www.tutorialspoint.com/powershell/index.htm)
- [link](https://github.com/ag143/obselete/blob/main/topicindex/powershell.md)
### Emacs
- [link](https://www.gnu.org/software/emacs/manual/html_node/emacs/index.html)
## Compile apps
### gcc
- [link](https://www.guru99.com/c-gcc-install.html)
### make
- [link](https://www.tutorialspoint.com/makefile/makefile_quick_guide.htm)
## system performance
### nmon
- [link](https://www.geeksforgeeks.org/linux-nmon/)
### iostat
- [link](https://www.geeksforgeeks.org/iostat-command-in-linux-with-examples/)
### sar
- [link](https://www.geeksforgeeks.org/sar-command-linux-monitor-system-performance/)
### vmstat
- [link](https://www.geeksforgeeks.org/vmstat-command-in-linux-with-examples/#:~:text=vmstat%20command%20in%20Linux%2FUnix,as%20virtual%20memory%20statistic%20reporter.)
## Others
### strace
- [link](https://www.geeksforgeeks.org/strace-command-in-linux-with-examples/)
### dtrace
- [link](https://man7.org/linux/man-pages/man1/dtrace.1.html#:~:text=The%20dtrace%20command%20converts%20probe,file%20via%20the%20%2DG%20option.)
### systemtap
- [link](https://documentation.suse.com/sles/15-SP1/html/SLES-all/cha-tuning-systemtap.html)
### uname
- [link](https://www.geeksforgeeks.org/uname-command-in-linux-with-examples/)
### df
- [link](https://www.geeksforgeeks.org/df-command-linux-examples/)
### history
- [link](https://www.geeksforgeeks.org/history-command-in-linux-with-examples/)
# Networking-Security-Protocols
## Emails
### SMTP
- [link](https://tecadmin.net/send-email-smtp-server-linux-command-line-ssmtp/)
### IMAPS
- [link](https://www.funoracleapps.com/2022/01/how-to-access-imap-server-from-command.html)
### POP3S
- [link](https://unix.stackexchange.com/questions/201818/checking-pop-mail-account-using-terminal)
### DMARC
- [link](https://linuxincluded.com/testing-spf-dkim-and-dmarc/)
### SPF
- [link](https://linuxincluded.com/testing-spf-dkim-and-dmarc/)
### Domain Keys
- [link](https://tecadmin.net/setup-dkim-with-postfix-on-ubuntu-debian/)
## HTTP
- [link](https://www.geeksforgeeks.org/understanding-http-using-browsers/)
## HTTPS
- [link](https://www.geeksforgeeks.org/explain-working-of-https/)
## FTP
- [link](https://www.geeksforgeeks.org/file-transfer-protocol-ftp/)
## SSL/TLS
- [link](https://www.geeksforgeeks.org/secure-socket-layer-ssl/)
- [link](https://www.geeksforgeeks.org/difference-between-secure-socket-layer-ssl-and-transport-layer-security-tls/)
## SSH
- [link](https://www.geeksforgeeks.org/introduction-to-sshsecure-shell-keys/)
## PORTFOrwarding
- [link](https://www.geeksforgeeks.org/port-forwarding-on-router-and-why-do-we-need-it/)
- [link](https://www.geeksforgeeks.org/ssh-port-forwarding/)
# Setup
## Reverse Proxy
- [link](https://www.cloudflare.com/learning/cdn/glossary/reverse-proxy/)
## Forward Proxy
- [link](https://www.geeksforgeeks.org/what-is-proxy-server/)
## Caching server
- [link](https://www.geeksforgeeks.org/caching-system-design-concept-for-beginners/)
## Load Balancer
- [link](https://www.geeksforgeeks.org/load-balancer-system-design-interview-question/)
## Firewall
- [link](https://www.geeksforgeeks.org/introduction-of-firewall-in-computer-network/)
## Webserver
### IIS
- [link](https://stackify.com/iis-web-server/)
### Nginx
- [link](https://www.tutorialspoint.com/ubuntu/ubuntu_nginx.htm)
### Apache
- [link](https://www.guru99.com/apache.html)
### Tomcat
- [link](https://www.javatpoint.com/what-is-tomcat)
### Caddy
- [link](https://www.tecmint.com/install-caddy-web-server-in-centos-ubuntu/)
# Infrastructrue as Code
## Containers
- [link](https://github.com/ContainerSolutions/kubernetes-examples)
### Docker
> - Docker version
> - Docker search 
> - Docker pull
> - Docker run 
> - Docker ps
> - Docker stop 
> - Docker restart 
> - Docker kill
> - Docker exec 
> - Docker login
> - Docker commit 
> - Docker push 
> - Docker network 
> - Docker history 
> - Docker rmi 
> - Docker ps -a
> - Docker copy
> - Docker logs   
> - Docker volume 
> - Docker logout 
- [link](https://github.com/ag143/docker)
- [link](https://github.com/collabnix/dockerlabs)
- [link](https://github.com/docker/getting-started)
- [link](https://takacsmark.com/dockerfile-tutorial-by-example-dockerfile-best-practices-2018/)
- [link](https://www.analyticsvidhya.com/blog/2022/06/writing-dockerfile-is-simple/)
- [link](https://www.tutorialspoint.com/docker/docker_file.htm)
- [link](https://www.simplilearn.com/tutorials/docker-tutorial/what-is-dockerfile)
- [link](https://linuxtechlab.com/learn-create-dockerfile-example/)
- [link](https://github.com/docker/compose)
- [link](https://docs.docker.com/compose/)
- [link](https://www.baeldung.com/ops/docker-compose)
- [link](https://www.okteto.com/docs/reference/compose/)
// ### LXC
## Configuration Management
### Ansible
- [link](https://github.com/ag143/ansible-for-devops)
### Chef
### Salt
### Puppet
## Container Orchestration
### docker swarm
### Helm
Helm is a package manager for Kubernetes that allows developers and operators to more easily package, configure, and deploy applications and services onto Kubernetes clusters.
- helm create chart-name
- helm create hello-world
- helm lint ./hello-world
- helm template ./hello-world
- helm install --name hello-world ./hello-world
- helm ls --all
- helm upgrade hello-world ./hello-world
- helm rollback hello-world 1
- helm uninstall hello-world
- helm package ./hello-world
- helm repo index my-repo/ --url https://.github.io/my-repo
- helm search repo
- helm --help
- helm repo update --help
- helm search hub wordpress
- helm repo add bitnami https://charts.bitnami.com/bitnami
- helm repo update
- helm install my-release bitnami/wordpress
- helm list
- helm uninstall my-release
- helm install --set wordpressBlogName="Helm Tutorials" my-release-2 bitnami/wordpress
- helm install --set wordpressBlogName="Helm Tutorials" --set wordpressEmail="john@example.com" my-release-3 bitnami/wordpress
- helm install --values values.yaml my-release-4 bitnami/wordpress

### Kubernetes
![alt text](https://ag143.github.io/obselete/topicindex/k8images/k8_basic_flow.png)

> - kubectl version
> - kubectl cluster-info
> - kubectl get nodes
> - kubectl get pods
> - kubectl describe pods
> - kubectl get services
> - kubectl expose deployment/kubernetes-bootcamp --type="NodePort" --port 8080
> - kubectl describe services/kubernetes-bootcamp
> - export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')
> - kubectl describe deployment
> - kubectl get pods -l app=kubernetes-bootcamp
> - kubectl get services -l app=kubernetes-bootcamp
> - export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')
> - kubectl label pods $POD_NAME version=v1
> - kubectl describe pods $POD_NAME
> - kubectl get pods -l version=v1
> - kubectl delete service -l app=kubernetes-bootcamp
> - kubectl get services
> - curl $(minikube ip):$NODE_PORT
> - kubectl exec -ti $POD_NAME -- curl localhost:8080
> - kubectl get deployments
> - kubectl get rs
> - kubectl scale deployments/kubernetes-bootcamp --replicas=4
> - kubectl get deployments
> - kubectl get pods -o wide
> - kubectl describe deployments/kubernetes-bootcamp
> - kubectl describe services/kubernetes-bootcamp
> - kubectl scale deployments/kubernetes-bootcamp --replicas=2
> - kubectl set image deployments/kubernetes-bootcamp kubernetes-bootcamp=jocatalin/kubernetes-bootcamp:v2
> - kubectl set image deployments/kubernetes-bootcamp kubernetes-bootcamp=gcr.io/google-samples/kubernetes-bootcamp:v10
> - kubectl rollout undo deployments/kubernetes-bootcamp
- [link](https://github.com/ag143/obselete/blob/main/topicindex/k8.md)
- [link](https://github.com/ag143/nodejs)
- [link](https://github.com/kubernetes/examples)
- [link](https://github.com/FairwindsOps/k8s-workshop)
- [link](https://github.com/WB3Tech/hello-k8s)
- [link](https://github.com/k8spatterns/examples)
- [link](https://github.com/tjaw09a/k8-helloworld)
// ### Docker Swarm
// ### Mesos
// ### Nomad
## Infrastructure Provisioning
### Terraform
- [link](https://app.terraform.io/public/signup/account?product_intent=terraform)
- [link](https://www.terraform.io/intro
### CloudFormation
- [link](https://www.w3schools.com/aws/aws_cloudessentials_awscloudformation.php)
// ### Pulumi
## Service Mesh
### Istio
### ENvoy
### Linkerd
### Consul
# CICD Tools
## Git
- get config
- ---------
- git config user.name
- git config user.email
- set config
- ----------
- git config --global user.email "email id"
- git config --global user.name "userid"
- initialize
- ----------
- git init
- clone
- -----
- git clone <ssh or https url>
- add files
- ---------
- git add <file or .>
- commit
- ------
- git commit -m "commit message"
- (amend)
- git commit -a
- push
- ----
- git push
- git push [variable name] master
- status
- ------
- git status
- current branch
- --------------
- git branch
- checkout
- --------
- git checkout <branchname>
- merge
- -----
- git merge <branchname>
- remote add
- ----------
- git remote add [variable name] [Remote Server Link]
- pull
- ----
- git pull
- stash
- ---------
- git stash save
- git stash pop
- git stash list
- git stash drop
- [link](https://git-scm.com/docs)
## Gitlabci
- [link](https://docs.gitlab.com/ee/ci/)
- to search existing file in project
> https://gitlab.com/api/v4/projects/11648088/search?scope=commits&search=test1
> Create new file in gitlab
> Post url: https://gitlab.com/api/v4/projects/11648088/repository/files/test1.txt?ref=master&private_token=<token>
> Headers: Content-Type:application/json
> payload: {"branch": "master", "author_email": "author@example.com", "author_name": "Firstname Lastname", 
>    "content": "change content", "commit_message": "update existing file"}
> Update existing content
> Put url: https://gitlab.com/api/v4/projects/11648088/repository/files/test1.txt?ref=master&private_token=<token>
> Headers: Content-Type:application/json

> payload:
> {"branch": "master", "author_email": "author@example.com", "author_name": "Firstname Lastname", 
>    "content": "change content", "commit_message": "update existing file"}
> # This works
> curl -u USER:PASS https://api.github.com/repos/USER/REPO/contents/a.txt --request PUT --data-ascii $'{"path": "a.txt", "content": "bXkgbmV3IGZpbGUgY29udGVudHM=", "message": "hello"}'


## GIthub actions
- [link](https://github.com/actions/starter-workflows)
- [link](https://docs.github.com/en/actions)
// ## Bamboo
## Azure Devops
- [link](https://github.com/CodeSizzler/AzureDevOps)
## Jenkins
- [link](https://github.com/ag143/Jenkinslearning)
// ## Travisci
// ## Team City
// ## Circle CI
# Build Tools
## Maven
Maven is a build automation tool used primarily for Java projects. Maven can also be used to build and manage projects written in C#, Ruby, Scala, and other languages. 
### mvn clean install -Dmaven.test.skip=true
> 	Clears the target directory and builds the project described by your Maven POM file without running - unit tests, and installs the resulting artifact (JAR) into your local Maven repository

### mvn dependency:tree
> Prints out the dependency tree for your project - based on the dependencies configured in the pom.xml file.
### Build Phase	Description
### validate	
> Validates that the project is correct and all necessary information is available. This also makes sure the dependencies are downloaded.
### compile	
> Compiles the source code of the project.
### test	
> Runs the tests against the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed.
### package	
> Packs the compiled code in its distributable format, such as a JAR.
### install	
> Install the package into the local repository, for use as a dependency in other projects locally.
### deploy	
> Copies the final package to the remote repository for sharing with other developers and projects.

### *Executing one of these build phases is done by simply adding the build phase after the mvn command, like this:*

### mvn compile
> This example Maven command executes the compile build phase of the default build life cycle. This Maven command also executes all earlier build phases in the default build life cycle, meaning the validate build phase.

### Executing Build Phases
> You can execute a build phase located inside a build life cycle by passing the name of the build phase to the Maven command. Here are a few build phase command examples:

### mvn pre-clean
> preclean
### mvn compile
> compile    
### mvn package
> Maven will find out what build life cycle the specified build phase belongs to, so you don't need to explicitly specify which build life cyle the build phase belongs to.
### set new module version in parent pom and child module
> mvn versions:set -DnewVersion= &ltnext  major or min version&gt
 
### change the version of property value
> mvn versions:update-property -Dproperty=&ltfrontend.version&gt -DnewVersion=[0.13.2]  


## npm
# Monitor
## Logs Management
- [link](https://sematext.com/guides/log-management/)
### Elastic Stack
- [link](https://logz.io/learn/complete-guide-elk-stack/#elk-in-production)
// ### Graylog
### Splunk
- [link](https://www.javatpoint.com/splunk)
// ### PaperTrail
## Infrastructure Monitoring
### Promotheus
- [link](https://github.com/prometheus/prometheus)
### Nagios
- [link](https://www.guru99.com/nagios-tutorial.html)
### Grafana
- [link](https://github.com/grafana/grafana)
### Zabbix
- [link](https://techblog.geekyants.com/zabbix-an-introduction-to-the-server-monitoring-tool)
//### Monit
### Datadog
- [link](https://www.techtarget.com/searchitoperations/definition/Datadog)
## Application Monitoring
// ### Jaeger
### New Relic
### AppDynamics
// ### Instana
// ### OpenTracing
# Cloud Providers
## AWS
### AWS Cloud Practitioner
- [link](https://github.com/open-guides/og-aws#lambda)
- [link](https://github.com/mikeroyal/AWS-Guide\)
- [link](https://github.com/ag143/AWS-Interview-Questions-Answers)
- [link](https://github.com/acritelli/aws-labs)
- [link](https://github.com/miztiik/AWS-Demos)
//## Google Cloud
## Azure
- [link](https://github.com/ag143/Azure-in-bullet-points/blob/master/AZ-900%20Microsoft%20Azure%20Fundamentals/az900_singlefile.md)
### Az900 Azure fundamanetals
- [link](https://github.com/osmanys/az900-training)
- [link](https://github.com/johnthebrit/AZ900CertCourse)
- [link](https://github.com/CodeSizzler/AZ900-Handouts)
- [link](https://github.com/ricmmartins/guia-estudo-az900)
- [link](https://digitaltraining.cloud/quizzes/az-900-microsoft-azure-fundamentals-practice-questions-2021/)
- [link](https://digitaltraining.cloud/quizzes/az-900-microsoft-azure-fundamentals-practice-questions-2021-set-2/)
- [link](https://digitaltraining.cloud/quizzes/az-900-microsoft-azure-fundamentals-practice-questions-2021-set-3/)
- [link](https://www.meshcloud.io/2022/10/31/mastering-landing-zones-like-a-superhero/)
- [link](https://infosecwriteups.com/ms-azure-fundamentals-revision-notes-ee5ce9fbafd1)
- [link](https://github.com/ruthrootz/azure-certifications-study-notes/tree/main/az-900)
- [link](https://www.techdoodles.co.uk/blog/2021/2/22/microsoft-azure-fundamentals-az-900-study-notes)
- [link](https://blog.devgenius.io/azure-az-900-notes-4bd94e166978)
- [link](https://github.com/undergroundwires/Azure-in-bullet-points)
### Az104 Azure Administrator
- [link](https://github.com/timothywarner/az104)
### Az400 Azure devops expert
- [link](https://github.com/timothywarner/az400)
- [link](https://github.com/MicrosoftLearning/AZ400-DesigningandImplementingMicrosoftDevOpsSolutions)
## Heroku
// ## Alibaba Cloud
// ## Digital Ocean
// ## Linode
// ## Vultr
# language
## Python
- [link](https://github.com/TheAlgorithms/Python)
- [link](https://github.com/ag143/python)
- [link](https://github.com/ag143/python3-in-one-pic)
- [link](https://github.com/Asabeneh/30-Days-Of-Python)
- [link](https://github.com/OmkarPathak/Python-Programs)
- [link](https://github.com/ag143/30-Days-of-Python-3.6)
- [link](https://github.com/geekcomputers/Python)
// ## Ruby
// ## Nodejs
## Go
- [link](https://github.com/ag143/GolangTraining)
- [link](https://github.com/ag143/GoJS)
// ## Rust
// ## C
// ## C++
// ## java
