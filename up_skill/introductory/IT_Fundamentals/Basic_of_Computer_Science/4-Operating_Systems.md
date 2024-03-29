# Operating Systems

## OS Concept

An **operating system** (OS) is system software that manages computer hardware,
software resources, and provides common services for computer programs.  An
operating system interacts with various hardware manufacturers using a set of
drivers. A **driver** is a computer program that operates or controls a particular
type of device that is attached to a computer. A **shell** (e.g. NVIDIA, Samsung
Magician) might be used to make it easier to run and set drivers.

Type of OS:

- Desktop operating systems
  - Windows
  - OS X
  - Linux OS
- Mobile operating systems
  - Android
  - iOS

The main functions of an operating system are as follows:

- Managing a computer's resources (e.g. CPU, memory) between different programs
  and applications
- Establishing a graphical user interface
- Executing and providing services for applications software

## Windows: Command Line

A **command line** is a user interface navigated by typing corresponding commands
at prompts by using a keyboard instead of a mouse as in the case of using graphical
user interface (GUI). To start the command line in Windows OS, press Windows+R to
open "Run" box. Then, type cmd and click OK to open a regular Command Prompt or
type cmd and then press Ctrl+Shift+Enter to open an administrator Command Prompt.

### Switch Drive in Command Line

When working with command line, you may face the problem when the access to some
drives or directories may be blocked or limited by a system administrator on
computers belonging to a corporate organization or an educational institution.
If for this reason you need to change the drive that opens in the command line
by default, just type the desired drive name with a colon, like `D:`.

#### Run as Administrator

#### CD Command in Command Line

```bash
cd /?
```

## Windows: Processes

### Processes and Threads

In simple terms, a **process** is an executing program. One or more threads run
in the context of the process.

A **thread** is the basic unit to which the operating system allocates processor
time. A thread can execute any part of the process code, including the parts
currently being executed by another thread.

Each process can create a **child process**. In this case, the process which
has a child process is called the **parent process**.

### How to end/kill/close a process?

In the Task Manager, if you want to end a process, right-click on the desired
process and click *End task*.
If you want to end a process and all related child processes, right-click on the
desired process and click *End process tree*.

### Sorting in Task Manager

In the Task Manager, you can sort processes by Name, Status, CPU, Memory, Disk,
Network, and so on. To do this, just click on the header of the desired column
once or twice to sort by descending or ascending order, respectively.

## Windows: Services

### Restart a Service from the Command Line

SC is a command-line program used for communicating with the Service Control Manager
and services.

```powershell
sc <server> [command] [service name] <option1> <option2>...
```

where **service name** is the name of the service. If the name contains spaces,
enclose it in quotation marks, "service name."

- `&&`

    is "and" operator. If two commands are chained together using &&, then the
    second command will run only if the first command has been finished successfully.

- `&`

    is "or" operator. If two commands are chained together using &, then the second
    command will run after the first command regardless of whether the first one
    has been finished successfully or not.

| Request                     | Command                                         |
|-----------------------------|-------------------------------------------------|
|To stop a service            |sc stop [service name]                           |
|To start a service           |sc start [service name]                          |
|To restart a running service |sc stop [service name] && sc start [service name]|
|If you are not sure whether  |                                                 |
|a service is already running,|                                                 |
|and want to restart or to    |                                                 |
|start it                     |sc stop [service name] & sc start [service name] |

If we talk about the start of a service, you can start it with parameters, if necessary.

```powershell
sc [<ServerName>] start <ServiceName> [<ServiceArguments>]
```

where:

- **ServerName**: Specifies the name of the remote server on which the service
  is located. The name must use the Universal Naming Convention (UNC) format
  (for example, \\myserver). To run SC.exe locally, omit this parameter.
- **ServiceName**: Specifies the service name returned by the getkeyname
  operation.
- **ServiceArguments**: Specifies the service arguments that should be passed
  for the service to be started.

## Windows: Users and Groups

### Users & Groups

A **user account** is a collection of settings and permissions that Windows uses
to understand what actions you are allowed to perform, what files and folders you
have access to, what devices you can use, and so on.

A **domain** is the minimal structural unit in **Active Directory**. It may include
network objects, such as users, computers, printers, shared resources, etc.
**Active Directory** (AD) is a directory service that stores information about
objects on the network and makes this information easy for administrators and
users to find and use.

## Windows: Environment Variables

An **environment variable** is a text variable of the operating system storing
some information, for example, system settings data, a path to a folder, etc.

There are two types of environment variables:

- User variables
- System variables

  - Imagine that you have a folder named "Subfolder" with the following path:
    C:\Users\<UserName>\Documents\Folder\Subfolder

  - Create a user environment variable which will contain this path.
    Variable name: MyFolder
    Variable value: C:\Users\<UserName>\Documents\Folder\Subfolder
    After clicking "OK" in all windows, you can use it.
  - Open File Explorer (earlier, Windows Explorer). In the address bar, type
    the variable name enclosed in percent signs %MyFoider%, press Enter, and
    you will be taken to the desired folder.

Command *echo* will print the command but not execute it
Command *set* create a new variable
Command *setx* create a variable in user variable and write it into the system
Command *setx/m* would you use to create a global environment variable and add
it to system variables

## Linux: Shell

The **shell** is a command line interface that takes commands and executes them.
In other words, the shell processes commands and returns the output.

**Terminal**, or a terminal emulator, is a program that allows you to communicate
with the shell through the window.

| Command | Description                                                                                  |
|---------|----------------------------------------------------------------------------------------------|
|man      |(short for "manual")returns a detailed manual of a command                                    |
|ps -aux  |shows processes that are currently running; the list of the processes is static               |
|pwd      |(short for "print working directory")prints the current working directory                     |
|more     |displays long text files per page at a time; you can navigate only forward                    |
|ls       |lists files and directories in the current directory                                          |
|less     |displays long text files per page at a time; you can navigate both forward and backward       |
|cd       |(short for "change directory")changes the current working directory                           |
|grep     |searches content in text files                                                                |
|mkdir    |creates a new folder                                                                          |
|kill     |terminates a process                                                                          |
|echo     |prints a string of a text to the terminal window                                              |
|vi       |a text editor                                                                                 |
|cat      |(short for "concatenate")reads data from a file and displays its content on the screen        |
|wget     |download a file from the Internet                                                             |
|top      |shows processes that are currently running; the list of the processes is updated every second |
|sudo     |runs a program as a super user                                                                |
|help     |provides the description of a command. Not all commands support the parameter ‑h or ‑help. For such commands, you can use man.

## Linux: File System

A **file system** is a system of storing files and organizing directories (catalogs).
A file system allows to systematize programs and data, and ensure the orderly
management of these objects.

If we compare Windows and Linux, these operating systems work on different file
systems. New Windows computers use the file system NTFS, while older ones use
the file system FAT32. As for Linux, computers with this operating system mostly
use the file systems EXT3 or EXT4.
While in Windows files are stored on data drives like C: D: E:, in Linux, there
are no drives at all. Linux has a hierarchical file system, where there is a root
directory from which other directories branch.

## Linux: Users and Groups

| USER               | GROUP              | OTHER              |
|--------------------|--------------------|--------------------|
| read write execute | read write execute | read write execute |

## Linux: Environment Variables

As in Windows, in Linux, an environment variable is a variable that has a name
and a value and stores some information. For example, an environment variable
can contain the location of a file or some system settings.
You can use one of the following commands for this type of a variable:

- `env`

  To get all environment variables of the current session and their values,
  the command `env` can be used. The result of this command is the list of
  environment variables where each variable is represented in the form: `NAME=VALUE`

- `echo`

  To display the value of a particular variable, the command echo can be used:

  ```bash
  echo $VariableName
  ```

- `export`

  In the current session, to set the value of an environment variable, we can
  use the command export in the following way:

  ```bash
  export VariableName=VariableValue
  ```

One important thing to note is that in Linux, an environmental variable can be
classified by the duration of existence:

- Local environment variables exist only in a local session.
- Global environment variables exist in a global session.
