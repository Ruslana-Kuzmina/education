# Productivity Tools

## Hotkeys

One way to increase your work productivity is to use hotkeys (also called keyboard
shortcuts) while interacting with an operating system or an application. A **hotkey**
is a key or a special combination of keys on a keyboard; pressing a hotkey enables
the performance of a certain task. Exactly what task will be performed after pressing
a hotkey depends on an operating system or an application. To check the hotkeys
that can be used for a certain OS or application, visit its help menu. However,
there are hotkeys that are commonly used in different applications and OS, e.g.
F1 is commonly used to open Help.

- Windows

|Hotkey                               |  Description                                      |
|-------------------------------------|---------------------------------------------------|
|Windows logo key + Left Arrow        |Maximize the window to the left side of the screen||
|Windows logo key + Right Arrow       |Maximize the window to the right side of the screen|
|Windows logo key + Up Arrow          |Maximize the window.                               |
|Windows logo key + Down Arrow        |Minimize the window.                               |
|Windows logo key + P                 |Choose a presentation display mode.                |
|Windows logo key + L                 |Lock your PC or switch accounts.                   |
|Windows logo key + M                 |                                                   |
|(or Windows logo key + D)            |Minimize all windows.                              |
|Windows logo key + R                 |Open the Run dialog box.                           |
|Alt + Tab (or Windows logo key + Tab)|Switch between open apps.                          |
|Alt + F4                             |Close the active item, or exit the active app.     |
|Ctrl + Shift + Esc                   |Open Task Manager                                  |

- Internet Browsers

|Hotkey             |Description                      |
|-------------------|---------------------------------|
|Ctrl + T           |New Tab                          |
|Ctrl + N           |New Window                       |
|Ctrl + W           |Close Tab                        |
|Ctrl + L           |Select URL address bar           |
|Ctrl + F           |Find in This Page                |
|Ctrl + Tab         |Go one Tab to the Right          |
|Ctrl + Shift + Tab |Go one Tab to the Left           |
|F11                |Toggle Full Screen               |
|F12                |Toggle Developer Tools           |

- IDE (Java and INTELLIJ IDEA)

|Hotkey          |Description             |
|----------------|------------------------|
|Ctrl + D        |Duplicate a current line|
|Ctrl + Y        |Delete a line at caret  |
|Alt + Insert    |Generate code..         |

## Vittualization and Remote Machines

### Virtualization and Its Types

**Virtualization** is the process of creating a software-based, or virtual,
representation of real objects (e.g. applications, servers, and networks) by
using special software (called a **hypervisor**). These obtained virtual objects
have access to the resources of a primary (also called host or physical) system.

Traditional computer system and virtual machine

- Application             = Application + Operation System
- Operation System        = Virtualization Software
- Computer hardware       = Computer hardware

A **virtual machine** (VM) is an emulation of a computer system. It uses software
instead of a physical computer to run programs and applications. There might be
one or more VMs installed on a single physical machine. Each VM installed on the
same host might run its own operating system; they can also function separately
from each other and the host.

In general, VMs have the following characteristics:

- **Partitioning**: there might be several VMs on a single "host" and the
  resources of the physical system are divided between VMs.
- **Isolation**: a VM can be isolated from other VMs on the same physical machine
  in order to prevent any security issues and guarantee a high level of the
  utilization of resources.
- **Encapsulation**: in fact, VMs and their states are files saved on a host.
  Thus, they can be easily moved/copied (also to a different “host” machine)
  and checked by antimalware programs.

There are several types of virtualization:

- Hardware (or Server) Virtualization
  A technology that creates a situation when multiple operating systems run as
  VMs on a single "host". Such virtualization increases the efficiency of the
  system, provides higher server availability, and reduces operating costs.

- Mobile Virtualization
   This is hardware virtualization applied to a mobile phone or a connected
   wireless device.

- Network Virtualization
  A process of combining resources of several physical networks into a single
  virtual network or dividing a single physical network into segments or
  separate virtual networks. Network virtualization enables the movement of VMs
  across different domains without reconfiguring network settings, and reduces
  the time needed to deploy or update applications. Network virtualization enables
  the implementation of cloud techniques.

- Desktop Virtualization
  A technology that creates a situation when the desktop environment and its
  applications are separated from the physical machine used to access it. In this
  case, workstation load is simulated in order to access the required desktop which,
  as a result, can be reached from different devices.

- Application Virtualization
  A technology that enables users to access the applications using different devices
  than those where these applications are installed.

- Storage Virtualisation (or cloud storage)
  A technology that allows to combine all physical storage resources so that they
  look and can be managed like a single storage.

There are also two different subtypes of virtualization:

- Paravirtualization
  - The guest OS is only partially isolated by a VM from the virtualization layer
     and computer hardware.
  - It uses the so called **hypercalls** – calls made by the operating system or
     by the process for a hypervisor when some services are required to be performed.
  - It is considered to be more secure, faster, but less portable and compatible
     compared to full virtualization.

- Full virtualization
  - The guest OS is fully isolated by a VM from the virtualization layer and
     computer hardware.
  - It uses binary translation and the direct approach as techniques for operations.
  - It is considered to be less secure, slower, but more portable and compatible
     compared to paravirtualization.

## Hypervisors and Their Types

A **hypervisor** is computer software, firmware, or hardware that creates and
runs virtual machines. Thus, thanks to a hypervisor, it becomes possible to run
another operating system on your computer. For example, working on Windows 10, you
can start a virtual machine with Linux. And it is possible without reinstalling
the main Windows 10 system. You can create any number of virtual machines and it
all depends on your computer's resources.

Main tasks of the hypervisor:

- running multiple operating systems simultaneously
- easier software installations
- testing and disaster recovery
- portability
- clean architecture

There are three main types of hypervisors:

- Type Native
  This type assumes that a hypervisor is located above hardware as a hardware and
  software implementation. Operating systems come from a hypervisor. This type is
  typical for server computers.
  In case of native hypervisors, if there is a crash of a single OS, this does
  not affect the other OSs and VMs installed on the same host. At the same time,
  if anything affects the parent OS with a hosted hypervisor, this will also affect
  the corresponding guest OS. Therefore, native hypervisors are considered more secure
  than hosted ones. They are also faster and more efficient as they generate less
  overhead, while under hosted hypervisors, the OS does not directly communicate
  with computer’s hardware.
  Examples: VMware ESXi, Citrix XenServer.
  Guest OS
  Hypervisor
  Hardware

- Type Hosted
  This type assumes that the parent operating system is located above hardware,
  and the hypervisor is installed in it. Guest operating systems come from a hypervisor.
  The type is typical for user computers when the virtualization task is a secondary
  task of the computer.
  Examples: VMware Workstation, QEMU, Parallels Desktop, VirtualBox.
  Guest OS
  Hypervisor
  Host OS
  Hardware

- Type Hybrid
  This type is a middle ground between Native and Hosted types. A Hybrid hypervisor
  consists of two parts: a thin hypervisor that controls the processor and memory,
  and a special service OS that runs under its control.
  The advantages of hosted hypervisors are that they are typically much easier
  to install and that in case they are used, a wide range of hardware can be
  supported as the parent OS directly communicates with computer’s hardware.
  Examples: Microsoft Virtual Server, Sun Logical Domains, Xen, Citrix XenServer,
  Microsoft Hyper-V, VMware Workstation.

  ## Cloud

  **"cloud"** is used to define servers that can be accessed over the Internet,
  and the software and databases that run on those servers.

  |Applications + Databases|
              |
  |         Servers        |
              |
  |        Internet        |

  **"Cloud computing"** is a term used to define specific client-server computing
  architecture. It is based on virtualization technology and enables users to reach
  applications and files without being bound to a specific device. For example,
  one can reach their account in Facebook using different cell phones or tablets.
  Though users are expected to pay for using cloud services, they have a chance
  of reducing their expenses as there is no more need to manage physical servers
  and machines.

  Сloud service models:

  - **SAAS** - Cloud users are provided with access to applications hosted on cloud
    servers. Examples: Salesforce, Gmail.
  - **PAAS** - Cloud users are provided with everything needed to develop their own
    applications (i.e. cloud-hosted development tools, operating systems, infrastructure).
    Example: Microsoft Azure.
  - **IAAS** - Cloud users are provided with servers and storage hosted on the cloud.
    This infrastructure is used by them to develop their own applications while they
    use their own development tools and operating system. Example: OpenStack.

## Backups

A **data backup** (or simply a backup) is a saved and stored copy of computer
data that can be used to recover these data in case of their damage, deletion
or when an early version of these data is required. It should be noted that
backup systems might vary upon their functionality, for example, not all of
them can reconstitute complex configurations like a computer system or a database
server.

An **information repository** is a storage used to aggregate and save the data
from the source system. An example of a simple information repository is your
external hard drive where important files are copied and you can see the date
of the file saved. A more complicated example of an information repository is a
relational database.

A computer **backup rotation scheme** is a system that determines how many backups
of different dates should be stored for each piece of data, and for how long they
should be stored before they are replaced with the next backup versions. One of
the rules that can be applied under the backup rotation scheme is the 3-2-1 rule
under which all the following ideas should be true:

3-2-1 Rule

- There should be at least 3 copies of data.
- Copies should be stored on 2 different types of storage media – this eliminates
  the possibility of data loss due to similar reasons.
- 1 copy should be kept offsite; this might be a remote geographical location or
  cloud storage. This reduces the possibility of data loss due to factors like fire
  and floods as well as the possibility of theft of the physical data storage.

### Backup Methods

- **Unstructured**
  One does not properly record the information about the data stored.
  - Characteristics:
    - Easy to implement.
    - Low level of recoverability.
  - Example: A set of DVDs without systematic information about what is stored on
    them.

- **Full only/System imaging**
  Complete source data copies are taken at one or more specific points in time.
  - Characteristics:
  More used to deploy a stored configuration to several devices than to backup
  changing systems.
  - Example: Records of configurations of computer systems.

- **Incremental**
  It stores the data that was changed since some reference point in time. Copies
  of unchanged data are not stored.
  Reference point is a full backup of all data made once or at infrequent intervals.
  A restoring process starts from restoring a full backup to which incremental
  backups are then applied.
  - Characteristics:
    - Increase the speed of a backup and decrease the disk/storage space.
    - Restoring of data may be time-consuming.
    - Risk of incomplete data recovery if any of the backup media is damaged or missing.
  - Example: A full backup is made on Monday. On Tuesday, only those files that
    were modified on Monday are backed up. On Wednesday, only those files that
    were modified on Tuesday are backed up.

- **CDP**
  CDP means Continuous Data Protection.
  Near-CDP systems make a backup very frequently,at a specific time interval,
  say every 15 minutes, or every hour.
  CDP (or true-CDP) systems, in turn, instantly back up data as soon as it has
  been created or modified.
  - Characteristics:
    - Near-CDP systems allow to roll back to a given point in time when true-CDP
      systems allow to roll back to any point in time.
    - Compared with true-CDP, near-CDP systems are not so resource-consuming and
      expensive.
  - Some examples of CDP products:
    - Microsoft Data Protection Manager
    - Symantec NetBackup RealTime
    - BakBone Software NetVault
    - CA XOsoft
    - EMC RecoverPoint
    - DoubleTake Software Double-Take Backup (near-CDP but can be upgraded to true-CDP)

- **Reverse Incremental**
  The first step is the creation of a full backup. Then, when each new backup is
  created, all data from the previous (full) backup is moved to a new backup, and
  the previous backup is replaced by an increment. Therefore, the latest (the newest)
  backup is always full, and the pervious (old) backups, on the contrary, are always
  increments.
  - Characteristics:
    Because the last backup is always full and does not depend on the previous
    backups, it is possible to restore the data quite quickly (of course if we
    talk about restoring the most recent versions). By contrast, restoring older
    versions takes more time.

- **Differential**
  The starting point is a full backup. Then, each successive backup stores data
  that was changed since the initial full copy, not the previous backup.
  - Characteristics:
  In comparison to the incremental backup, the differential backup allows to
  restore data faster. This is due to the fact that for restoring, one only needs
  the initial full backup and the last differential backup.
  - Some examples of differential backup systems:
    - Acronis Backup
    - Backup Exec
    - Commvault

#### Types of Backup Destination

- Hard disc
- Optical storage (CDs, DVDs)
- Solid State Drive (SSD)
- Remote Backup Service

## Version Control

**Version control** is the practice of tracking and managing changes made to a file
over time. For example, one can track who made what changes to the program code
and when.

**Version control systems**, in turn, are a category of software tools that record
the changes and allow one to roll back to a particular version at any time.

### Types of Version Control Systems

- Local Version Control Systemss
  stores all changes in a database on your computer, locally. This is quite a rare
  case in practice.
- Centralized Version Control Systems
  stores all versions of files on the server, allowing different users to have
  access to these files.
- Distributed Version Control Systems
  keeps a complete copy of the repository on the side of each developer. Each
  copy of the repository is a full backup of all data. Exemples, GIT

#### GIT

The main difference between Git and other version control systems is how Git stores
and uses information. Most version control systems store a list of changes to each
file compared to its original version. Git does not store differences with the original
file. Instead, every time when one commits or saves a file, Git makes a snapshot
of this file and stores the reference to this snapshot. And if the file was not
changed, Git does not save the same file again, it simply takes a link to the
previous identical file that has already been stored.

Because Git is a differential version control system, each user has a full copy of
the repository stored locally. For this reason, Git users can easily work offline
and, if necessary, connect to the network, for example, for synchronization.

##### Important Features of Git

In Git, files can reside in three states:

- **Modified**. Files have already been modified but have not been committed yet.
- **Staged**. Files are modified and are marked to go to the next commit.
- **Committed**. Files have already been stored in the local database.

Three Sections of a Project:

- Working Directory - is a temporary space where you can modify files.
- Staging Area - is a file that stores information about what will be included
  in the next commit. This file is contained within a .git directory.
- .git directory (Repository) - is copied to a local computer when a user clones
  a repository. It stores the object data base of a project and metadata (who and
  when committed a change, what file was changed, etc.)










