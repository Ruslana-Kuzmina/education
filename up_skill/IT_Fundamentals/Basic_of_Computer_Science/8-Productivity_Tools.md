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


