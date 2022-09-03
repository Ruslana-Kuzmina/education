# Questions

## Computer Hardware Basic

- Which component of a system unit loses its information if power is removed?
	* [ ] Hard disk drive
	* [X] Random access memory
	* [ ] Solid state drive

- Which connector type is used to connect HDD and/or SSD with other elements inside a system unit?
	* [ ] DVI
	* [ ] PCI
	* [ ] USB
	* [x] SATA

## Data Representatiom and Computer Architecrure

- Convert the number 10895 to the hexadecimal system
	* [ ] 0010 1010 1000 1111
	* [x] 2A8F
	* [ ] 67733
	* [ ] F8A2

- Represent −23 using an 8-bit two’s complement.
	* [ ] 0001 0111
	* [x] 1110 1001
	* [ ] 1110 1000
	* [ ] 0001 0110


### Text, Encodings, Unicode

- Which of the following encodings have fixed length?
	* [x] ASCII
	* [ ] UTF-8
	* [ ] UTF-16
	* [x] UTF-32

- Which of the following encodings is the most frequently used encoding nowadays?
	* [ ] ASCII
	* [x] UTF-8
	* [ ] UTF-16
	* [ ] UTF-32

 - How many symbols are there in the Unicode?
	* [ ] 256
	* [ ] 2*32 = 4,294,967,296
	* [x] About 100,000
	* [ ] About 1,000,000
	* [ ] About 10,000

### Colors and Images 

- How many bytes are needed to store a 200 x 300 bitmap image using true color?
	* [ ] 180,000
	* [ ] Slightly more than 1,920,000
	* [ ] 60,000
	* [ ] 1,920,000
	* [ ] About 60,000
	* [x] Slightly more than 180,000

Count 200*300*3= 180000, but we choose more because some additional space is also needed for the header which contains information about the image width, height, color depth, and other

- How many bytes are needed to store a 100 x 300 bitmap image using true color?
	* [ ] 90,000
	* [x] Slightly more than 90,000.
	* [ ] Slightly more than 960,000.
	* [ ] 960,000
	* [ ] About 30,000.
	* [ ] 30,000

- Which of the following formats is used for vector graphics?
	* [ ] png
	* [ ] bmp
	* [x] svg
	* [ ] jpeg
	* [ ] gif

## Formal Languages

- Select all the words that match the regular expression [ec]ar.
	* [x] ear
	* [x] car
	* [ ] bar
	* [ ] march

## Operating Systems

- In Windows OS, how can you delete a service?
	* [ ] Task Manager -> Services -> Find the required process and right-click on it -> Choose "Stop"
	* [x] Open Command Line as Administrator -> Type the command: sc delete <ServiceName>
	* [ ] Services -> Find the required process and right-click on it -> Choose "Stop"
	* [ ] Open Command Line -> Type the command: sc delete <ServiceName>

- In Windows OS, which command would you use to create a global environment variable and add it to system variables?
	* [x] setx /m
	* [ ] echo
	* [ ] set
	* [ ] set /m
	* [ ] setx

- In Linux (Ubuntu), if you are working with a long text file, which command would you use to display the file per page at a time and navigate both forward and backward?
	* [x] less
	* [ ] split
	* [ ] grep
	* [ ] vi
	* [ ] more

- In Linux (Ubuntu), what will be the result of the following command?
export ex = name

	* [ ] The environment variable "name" with the value "ex" that exists in a global session.
	* [x] The environment variable "ex" with the value "name" that exists in a local session.
	* [ ] The environment variable "name" with the value "ex" that exists in a local session.
	* [ ] The environment variable "ex" with the value "name" that exists in a global session.

- In Windows OS, how to reference an environment variable in the command line?
	* [ ] Enclose the variable name in quotation marks.
	* [x] Enclose the variable name in percent signs.
	* [ ] Type the variable name.
	* [ ] Put a percent sign before the variable name.
	* [ ] Put a backslash before the variable name.

- In Windows OS, if a process is stuck, how can it be killed?
	* [ ] Command Line -> Type kill <NameOfTheRequiredProcess>
	* [x] Task Manager -> Details -> Find the required process and right-click on it -> Choose "End task"
	* [ ] Services -> Find the required service and right-click on it -> Propertes -> Set Startup Type to "Disabled"
	* [ ] Services -> Find the required process and right-click on it -> Choose "Stop"

- In Windows OS, which command-line command can you use to read a file?
	* [ ] cat
	* [x] type
	* [ ] echo
	* [ ] read

- How can the following access rights be performed in Linux (Ubuntu):
"A group can read and write the file, others can only read the file, and an owner can read, write, and execute a file."?
	* [x] - rwx rw - r - -
	* [ ] - rw - r - - rwx
	* [ ] - rw - rwx r - -
	* [ ] r - - rw - rwx
	* [ ] rw r rwx

- Select a true statement.
	* [ ] As in Windows, in Linux, the system is installed on drive C.
	* [x] In Linux, there are no drivers.
	* [ ] Linux computers use the file system NTFS.
	* [ ] Windows computers use the file systems EXT3 or EXT4.
	* [ ] In Linux, tmp directory contains frequently modified files.

## Network and Protocols

- What does DNS stand for?
	* [ ] Digital Name System
	* [x] Domain Name System
	* [ ] Dynamic Name Schema
	* [ ] Domain Name Science
	* [ ] Domain Name Schema

- Suppose you open the URL https://mail.google.com/mail/u/0/#sent in your browser. Which part of the URL is not used to form the HTTP request?
	* [ ] The prefix of the URL, "https://".
	* [x] The "#sent" part which is at the end of the URL.
	* [ ] The "mail." part in the hostname "mail.google.com".
	* [ ] The tail of the request after the hostname, "/mail/u/0/#sent".

- Which command line command can be used to find the IP address of your computer?
	* [ ] tracert
	* [ ] ping
	* [x] ipconfig
	* [ ] nslookup
	* [ ] netstat

## Databases

- What does SQL stand for?
	* [ ] Standard query language
	* [x] Structured query language
	* [ ] Standard quick language
	* [ ] Structured question language

- Which SQL command retrieves data from a table?
	* [ ] UPDATE
	* [x] SELECT
	* [ ] DELETE
	* [ ] RETRIEVE
	* [ ] GET

## Security

- What is a hash?
	* [ ] an encrypted password
	* [x] a virtually unique text image of data
	* [ ] a private key in asymmetric encryption
	* [ ] the result of XOR operation applied to a message and an encryption key

- Which of the following is the most used symmetric encryption nowadays?
	* [ ] RSA
	* [x] AES
	* [ ] SHA-2
	* [ ] TLS
	* [ ] XOR Cipher

- What type of encryption does TLS utilize?
	* [ ] symmetric encryption
	* [x] both symmetric and asymmetric encryption
	* [ ] asymmetric encryption
