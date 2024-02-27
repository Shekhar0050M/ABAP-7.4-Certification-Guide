# ABAP-7.4-Certification-Guide
A repository containing detailed guidelines for SAP ABAP

## Cover
## SAP Press
## Title Page
## Copyright
## Contents
## Acknowledgments
### The Authors
> David Haslam
> Puneet Asthana
## Preface
### Structure of this Book
> Part 1
> Part 2
### Glimpse into the Exam Structure
> Competency level - A, B, C, D
> Exam topic
### Practice Questions
> Question Stimulus - varies but intention is scenario specific
> Actual Question
> Question Hint
> Answers
>> Multiple response - more than one choice
>> Multiple choice - one choice at a time
>> True/False
>> Fill in the blanks
> Sequence/Ranking - mark the correct option in sequence  
### Summary
> Practice with sample tests, read document, apply for certification, pass and get the certificate.
## Part 1: General Introduction
### ABAP Development Certification Track: Overview
#### Certification Exam Scoring Changes
##### Certification Levels
> Associate: 1-3 years of knowledge and experience
> Professional
> Master
##### Advanced Certification Levels
> One round sitting examination could be attempted 3 times a year only. After failing, wait for 30 days for next attempt. Fee doesn't varies.
#### Becoming an SAP Certified ABAP Development Associate: Overview
> C_TAW12_740
> SAP Certified Development Associate—ABAP with SAP NetWeaver 7.40
#### Associate Examination Specifics
> Software components: SAP NetWeaver 7.40
> Number of questions: 80
> Duration: 180 minutes
### Courses and Experience
#### Training Courses for ABAP
> TAW 10
> TAW 11
> TAW 12
> BC400
> BC401
> BC402
> BC405
> BC414
> BC425
> BC430
> NET310
> NW001
#### Sources of information
> SAP Community Network (SCN) - http://scn.sap.com
> SAP Help Portal - http://help.sap.com
#### Strategic Understanding
> Monitor your comprehension
> Always check the logic behind the ideas
> Watch out for anything that seems counter intuitive
> Test your own understanding
> Generate your own examples
> Think in pictures, shapes and colors
> Use mnemonics/memory-training devices for important ideas.
> Use repetition
#### SAP Examination Strategies
> There is never a strategy. Just drink lots of water.
#### General Examination Strategies
> There is never a strategy. Just drink lots of water.
#### Summary
> Additional sources of information that can be useful for the certification examination.
## Part 2: Exam Preparation
### SAP NetWeaver: Overview
#### Objectives of this Portion of the Test
> Verify your general knowledge
##### Practice Questions
1. The Internet Communication Manager (ICM)…
 [] Replaced SAP ITS.
 [x] Allows SAP NetWeaver Application Server to process HTTP requests.
 [] Allows the ABAP stack and the Java stack to exchange data.
2. The Java stack and the ABAP stack of an SAP NetWeaver Application Server
must always be installed together.
 [] True
 [x] False
3. A work process…
 [] Stays linked toa screen through the dispatcher.
 [] Becomes inactive while waiting for a user.
 [x] Uses a common memory area called shared memory.
4. Each work process… (Select all that apply.)
 [x] Is independent of other work processes.
 [] Uses a pool of database connections established when the SAP NetWeaver Application Server ABAP started.
 [x] Uses a database connection to a work process established when the SAP NetWeaver Application Server ABAP started.
 [x] Can only make database changes within a single database LUW.
 [] Can make database changes spanning multiple database LUWs.
5. Each work process is assigned a type of task that can be performed. Which statements related to this are true? Select all that apply.
 [] To switch a work process type requires a restart of the SAP NetWeaver Application Server ABAP.
 [x] All work processes have the same structure.
 [] All work processes communicate with the database.
 [x] All work processes communicate with the dispatcher.
 [] A work process can communicate directly with an external system through a Remote Function Call.
 [x] It is possible to have multiple enqueue work processes on an SAP NetWeaver Application Server.
 [] It is possible to have multiple spool work processes on an ABAP application server.
6. What is the difference between SAP Basis and SAP NetWeaver?
 [] There is no difference; the name change was driven by marketing alone.
 [] All versions of SAP NetWeaver require the use of Unicode.
 [x] All versions of SAP NetWeaver include the ability to handle HTTP requests.
7. The dispatcher handles all communication between users, work processes, and other (external) systems.
 [] True
 [x] False
8. The ABAP messaging channels (AMC) uses the WebSocket protocol to gain
two way communication instead of HTTP.
 [] True
 [x] False

##### Practice Question Answers and Explanations

1. Correct answer: B
Beginning with SAP NetWeaver 6.10, new technologies based on highly a scalable infrastructure were implemented to process HTTP requests directly
from the Internet or to send them as HTTP client requests to the Internet. The SAP kernel was enhanced to include a process known as the Internet Communication Manager (ICM) to achieve this functionality.
2. Correct answer: B
Different SAP NetWeaver components require the SAP NetWeaver Application Server to be run with certain stacks configured. It is possible to install
both the ABAP and Java stacks, but depending on the use of the server, it is possible to use just ABAP or just Java.
3. Correct answer: C
All of the work processes of an ABAP application server use a common main memory area called shared memory to save contexts or to buffer constant
data locally. The resources that all work processes use (for example, programs and table contents) are contained in shared memory. Memory management
in the AS ABAP ensures that the work processes always address the correct context.
4. Correct answers: A, C, D
Each individual work process works independently, which makes them suitable for a multiprocessor architecture. When you start up an AS ABAP, each ABAP application server registers its work processes with the database layer and receives a single dedicated channel for each. While the SAP NetWeaver Application Server is running, each work process is a user (acting as a client) of the database system (acting as a
server). You cannot change the work process registration while the system is running or reassign a database channel from one work process to another.
For this reason, a work process can only make database changes within a single database logical unit of work (LUW). A work process must open a  separate database LUW for each dialog step. The work process sends a commit command (database commit) to the database at the end of each dialog step in which it makes database changes. These commit commands are called implicit database commits because they are not explicitly written into the application program.
5. Correct answers: B, D, F
You can use the system administration functions to switch a work process while the system is running. Because each work process has the same structure, they are interchangeable. All work processes must communicate with the dispatcher (which assigns the user to a work process), but enqueue work processes and spool work processes do not communicate with the database. All communication for a work process occurs with either the dispatcher or the database. Whereas it is normal to only have one enqueue work process (a single enqueue work process is normally sufficient to perform the required tasks), it is possible to have multiple enqueue work processes running. In SAP NetWeaver Application Server you can have only one lock table, but multiple enqueue work processes, running. Each ABAP application server can contain multiple spool work processes.
6. Correct answer: C
The difference between SAP Basis and SAP NetWeaver is that the platform had become a web server. This included the capabilities to handle HTTP requests and includes a Java stack in addition to the existing ABAP stack.
7. Correct answer: B
The dispatcher does handle communication between the work process and the user but does not handle communication with external systems. External systems use the gateway for communications.
8. Correct answer: B
This is true for ABAP Push Channels (APC)—not ABAP Message Channels. ABAP Message Channels communicate between ABAP programs.
### ABAP Workbench Usage
> Objectives of this Portion of the Test
>> ABAP Workbench and development tools
>> ABAP Workbench settings
>> The use of various browsers in the ABAP Workbench
>> The Front-End Editor and the settings to improve productivity
>> Development Packages and Transport Organizer
> Key Concepts Refresher
> ABAP Workbench
> Repository Browser
> Repository Information System
> Workbench Settings
> ABAP Editor and Workbench Settings
> ABAP Workbench Tools in Detail
> Enhancement Information System
> Packages and Their Attributes
> Transport Organizer
> Practice Questions
> Practice Question Answers and Explanations
> Takeaway
> Refresher
> Summary
### ABAP Debugger Program Usage
> Various ways to start the debugger
> Breakpoints
> Watchpoints
> Assertions
> Viewing and modifying data objects
> Understanding the architecture of the debugger
> Key Concepts Refresher
>> New and Classic Debugger
>>> SYSTEM -> UTILITIES -> DEBUG ABAP or SYSTEM -> UTILITIES -> DEBUG SCREEN
>>> shortcut: /h and press ENTER
>>> Execute debugging 
>>> Select desired line AND select SET/DELETE breakpoint 
>> New Debugger Tools and UI
>> Assertions and Breakpoints
>> New Debugger Customization and Settings
>>> SY-SUBRC: system variable containing the statement return code
>>> SY-TABIX: system varible containing the internal table row last accessed
>>> SY-DATUM: show system current date
>>> SY-UZEIT: show system current time
>>> SY_UNAME: show userID of current user
### ABAP Types and Data Objects
> Objectives
>> Data types and data objects
>> Predefined and generic data types
>> Valid operations on the various data objects and their usage in programs
>> Local data types and the global data types
>> Structure declarations and the differences between flat, nested and deep structures
> Key concepts refresher
```
difference betweeen predefined and generic data types and their usage within the program
syntax of the data declaration
valid operations of the data objects
```
## ABAP Types and Data Objects
>>> Data types 
>>>> Data types are used for the definition of data objects - define technical attributes of data objects - define how data stored in memory - operations are possible on the data objects based on the data type - used for definition of interface parameters - used for input output field  in the ABAP programs - used to declare PARAMETERS and SELECT-OPTIONS for program selection screens and dynpro screen fields 
>>>>> Data types 
>>>>>> Predefined data types
>>>>>> Local data types 
>>>>>> Global data types
>>>>>>> ABAP dictionary objects
>>>>>>> ABAP dictionary type group
>>>>> Data objects 
>>>>>> Data objects are temporary storage in the program and occupy memory to store data.
>>>>>>> Literals - unnamed data objects with fixed values
>>>>>>>> Numeric literals - sequence of digits that contain a plus or minus sign - value ranges from -2^31+1 to 2^31-1 - WRITE: 12345.
---
>>>>>>>> Text field literals - sequence of cahracters in inverted commas - value ranges from 1 to 255 characters in length - WRITE: 'A text literal'.
---
>>>>>>>> String literals - sequence of characters enclosed with back quotes - WRITE: `A STRING literal`
---
>>>>>>> Constants - named data objects with fixed values and defined statically using a declarative statement - CONSTANTS: c_nump TYPE P DECIMALS 3 VALUE '123.657'. c_city TYPE C LENGTH 10 VALUE 'BERLIN'
---
>>>>>>> Text Symbols - TEXT-XXX, where XXX is the text ID  for the text symbol maintained in the text pool - WRITE text-001. WRITE 'THIS is an English text'(002). - SE11 -> syst
---
>>>>>>> Predefined data objects - ABAP dictionary - SYST
---
>>>>>>> Variables - data objects - allows to store data locally for the program in memory
---
>>>>>>>> DATA keyword - declare data - DATA: count type I, count2 TYPE I value 10. - DATA: itab TYPE STANDARD TABLE OF mara. SELECT matnr bismt FROM mara INTO CORRESPONDING FIELDS OF TABLE itab WHERE mtart EQ 'FERT'. LOOP AT itab INTO DATA(wa). WRITE:/ wa-matnr, wa-bismt. ENDLOOP. READ TABLE itab WITH KEY matnr = '1400-500' INTO DATA(wa2). - DATA: itab TYPE STANDARD TABLE OF mara. LOOP AT itab ASSIGNING FIELD-SYMBOL(<line>). WRITE:/ <line>-matnr, <line>-bismt. ENDLOOP. READ TABLE itab WITH KEY matnr ='ABC' ASSIGNING FIELD-SYMBOL(<line2>). - oref->meth( IMPORTING p1 = DATA(a1)IMPORTING p2 = DATA(a2)... ).
---
>>>>>>>> STATICS - declare the data with the static validity within the procedure - { REPORT DEMO_STATIC_DATA_OBJECT. DO 5 TIMES. PERFORM dataobject_example. ENDDO. FORM dataobject_example. DATA count1 TYPE I. STATICS count2 TYPE I. count1 = count1 + 1. count2 = count2 + 1. WRITE: / 'Count1: ', count1, 'Count2: ', count2. ENDFORM. : Count1: 1 Count2: 1 Count1: 1 Count2: 2 Count1: 1 Count2: 3 Count1: 1 Count2: 4 Count1: 1 Count2: 5}
---
>>>>>>>> CLASS-DATA: declare a static attribute for the class - is valid for all instances  of the class within the program
---
>>>>>>>> PARAMETERS: declare an elementary data object - displayed as input field on the selection screen
---
>>>>>>>> SELECT-OPTIONS: declare an internal table - displayed as input field on selection screen 
## ABAP Data types - predefined data types provided by the ABAP runtime environment
>>> Four character types - Numeric types (N), character text(C), data type(D), time type(T) - each character occupies 2 to 4 bytes
>>> Three numeric types - Integer (I), Floating point numbers(F), packed number(P) - used to display and calculate numbers
>>> Integer type - whole number - DATA: num1 TYPE I value 5. num2 TYPE I VALUE 2. Result TYPE I. Result = num1 / num2.
>>> STRING - variable-length character string 
>>> XSTRING - variable-length hexadecimal byte sequence ::: {TYPES: , DATA: }
## Local Data types - present inside ABAP program and are visible to the program only 
>> TYPES: <type_name> ... [TYPE <ABAP-Type> |   LIKE <obj>].
>> TYPES: BEGIN OF Address_ty. firstname TYPE C LENGTH 20 lastname TYPE C LENGTH 20. street  TYPE C LENGTH 20. city TYPE C LENGTH 20. END OF address_ty.
>> DATA: addrs TYPE address_ty. addrs-firstname = 'Bob', addrs-lastname = 'Johnson' addrs-street = '123 Adam Lane'. WRITE: addrs-firstname, addrs-lastname, addrs-street.
>> TYPES: BEGIN OF stru1, fld1 TYPE I, BEGIN OF stru2, fld2 TYPE C, fld3 TYPE I, END OF stru2, END of stru1
>> TYPES: <Table_type> TYPE <tablekind> OF <linetype> [WITH <key>].
### Internal Table Definition and Use
### SQL Statements Including Update Strategies
### Basic ABAP Programs and Interface Creation
### ABAP Dictionary
### Unicode
### Classical Screens
### Selection Screens
### ABAP Object-Oriented Programming
### ALV Grid Control
### User Interface (Web Dynpro)
### Class Identification Analysis and Design
### Enhancements and Modifications
### Table Relationships
### The Authors
### Index