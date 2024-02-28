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
![alt text](images/ABAP%20Data%20Types.png)
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
![alt text](images/ABAP%20Dictionary%20Structure%20SYST.png)
---
>>>>>>> Variables - data objects - allows to store data locally for the program in memory
---
>>>>>>>> DATA keyword - declare data - DATA: count type I, count2 TYPE I value 10. - DATA: itab TYPE STANDARD TABLE OF mara. SELECT matnr bismt FROM mara INTO CORRESPONDING FIELDS OF TABLE itab WHERE mtart EQ 'FERT'. LOOP AT itab INTO DATA(wa). WRITE:/ wa-matnr, wa-bismt. ENDLOOP. READ TABLE itab WITH KEY matnr = '1400-500' INTO DATA(wa2). - DATA: itab TYPE STANDARD TABLE OF mara. LOOP AT itab ASSIGNING FIELD-SYMBOL(<line>). WRITE:/ <line>-matnr, <line>-bismt. ENDLOOP. READ TABLE itab WITH KEY matnr ='ABC' ASSIGNING FIELD-SYMBOL(<line2>). - oref->meth( IMPORTING p1 = DATA(a1)IMPORTING p2 = DATA(a2)... ).
---
>>>>>>>> STATICS - declare the data with the static validity within the procedure - { REPORT DEMO_STATIC_DATA_OBJECT. DO 5 TIMES. PERFORM dataobject_example. ENDDO. FORM dataobject_example. DATA count1 TYPE I. STATICS count2 TYPE I. count1 = count1 + 1. count2 = count2 + 1. WRITE: / 'Count1: ', count1, 'Count2: ', count2. ENDFORM. : Count1: 1 Count2: 1 Count1: 1 Count2: 2 Count1: 1 Count2: 3 Count1: 1 Count2: 4 Coun>>t1: 1 Count2: 5}
>>>>>>>> The *variable count1 does not retain the value* because it is declared with the *DATA* keyword, whereas the variable count2, declared with the *STATICS* keyword, *retains the value for the runtime of the program*.
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
## Global data types - a available system- wide
>> To define a data object that refers to a data type defined in the type group SLIS, you have to declare the type group in the ABAP program with the syntax TYPE-POOLS: SLIS and then define the data object with reference to the data type defined in the type group.
>>> TYPE-POOLS: SLIS.
>>> DATA: fieldcat TYPE slis_t_fieldcat_alv.
## Data Object Visibility - visibility of the data object is dependent on the context of the variable
>>> Variable defined with DATA statement - subroutine between FORM and ENDFORM, it is local data object for the subroutine - data is not visible and is not accessible outside the subroutine
>>> If data is inside function module, then it is a local data object for the function module.
>>> Data-objects at start of the program - with DATA, PARAMETERS or SELECT-OPTIONS - visible to entire program and are global data objects
>>> Data object is declared between MODULE and ENDMODULE of PAI or PBO module for the screen
>>> Data objects are defined with TABLES - visible to entire program 
### Internal Table Definition and Use
> Internal tables - program variables and store multiple identical structured data records in the ABAP runtime memory - process large data sets in a structured manner 
> Data types - Line Type and Table Key
> Types of tables - Standard tables, Sorted tables, Hashed tables, Indexed, Not specified
> Table key is pimary key - primary_key
> Components of primary key declared using - UNIQUE, NON-UNIQUE KEY, specified
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
```
*&---------------------------------------------------------------------*
*& Report  ZSHEKHAR01
*&
*&---------------------------------------------------------------------*
*&
*&
*&---------------------------------------------------------------------*
REPORT ZSHEKHAR01.

""""""""""""""""""""""""""
WRITE:12345.
WRITE: 'A text literal'.
WRITE: `A STRING literal`.

"""""""""""""""""""""""""
CONSTANTS: c_nump TYPE P DECIMALS 3 VALUE '123.657',
           c_city TYPE C LENGTH 10 VALUE 'BERLIN'.

"""""""""""""""""""""""""
WRITE text-001.
WRITE 'THIS is an English text'(002).

"""""""""""""""""""""""""
DATA: count TYPE I,
      count2 TYPE I VALUE 10.

"""""""""""""""""""""""""
"Declaration of field symbols
" DATA: itab TYPE STANDARD TABLE OF mara.

" SELECT matnr bismt FROM mara
"     INTO CORRESPONDING FIELDS OF TABLE itab
"                                  WHERE mtart EQ 'FERT'.

" LOOP AT itab INTO DATA(wa).
"     WRITE:/ wa-matnr, wa-bismt.
" ENDLOOP.

" READ TABLE itab WITH KEY matnr = '1400-500' INTO  DATA(wa2).

"""""""""""""""""""""""""
"Declaration of actual parameters
" DATA: itab TYPE STANDARD TABLE OF mara.

" LOOP AT itab ASSIGNING FIELD-SYMBOL(<line>)
"     WRITE:/ <line>-matnr, <line>-bismt.
" ENDLOOP.

" READ TABLE itab WITH KEY matnr = 'ABC'
"                          ASSIGNING FIELD-SYMBOL(<line2>).

"""""""""""""""""""""""""
"Declaration of Table Work Area
" oref->meth( IMPORTING p1 = DATA(a1)
"         IMPORTING p2 = DATA(a2)
" ...).

"""""""""""""""""""""""""
"STATISTICS keyword
DO 5 TIMES.
  PERFORM dataobject_example.
ENDDO.
FORM dataobject_example.
DATA    count1 TYPE I.
STATICS     count2 TYPE I.
count1 = count1 + 1.
count2 = count2 + 1.
WRITE:/ 'Count1: ', count1, 'Count2: ', count2.
ENDFORM.

"""""""""""""""""""""""""
"Usage of Data Keyword
DATA: var1 TYPE I.
DATA: var2 LIKE var1.
DATA: var3  TYPE STRING VALUE 'Hello'.
DATA: num1 TYPE I VALUE 5,
      num2 TYPE I VALUE 2,
      RESULT TYPE I.
"     RESULT = num1 / num2.
DATA: pack_num1 TYPE P LENGTH 8 DECIMALS 2,
      pack_num2 TYPE P LENGTH 8 DECIMALS 2 VALUE '2.55'.
DATA: dec_num1 TYPE decfloat16,
      dec_num2 TYPE decfloat34.
DATA: hex(1) TYPE X VALUE '09'.

"Syntax to declare incompete data types
"DATA var1 TYPE C.         "character variable of length 1
"DATA: var2(3) TYPE C.         "character variable of length 3
"DATA: var3 TYPE C LENGTH 3.         "character variable of length 3

"Syntax for data types and data objects
TYPES: v_char1(2) TYPE C.
TYPES: v_char2 TYPE C LENGTH 10.
TYPES: num1 TYPE P DECIMALS 2.
DATA: name(20) TYPE C.
DATA: price TYPE P DECIMALS 2.

"""""""""""""""""""""""""
"TYPES: <type_name> ... [TYPE <ABAP-Type> | LIKE <obj> ].
"TYPES: char1 TYPE C LENGTH 8,
"       num1 TYPE N LENGTH 6,
"       pack1 TYPE P LENGTH 3 DECIMALS 2.

"Define the structure data type in an ABAP program
TYPES: BEGIN OF address_ty,
             firstname TYPE C LENGTH 20,
             lastname TYPE C LENGTH 20,
             street TYPE C LENGTH 30,
             city TYPE C LENGTH 20,
       END OF address_ty.

"Access individual components of the structure data  type in the program
"DATA: addrs TYPE address_ty,
"      addrs-firstname = 'Bob',
"      addrs-lastname = 'Johnson',
"      addrs-street = '123 Adam Lane'.
"WRITE: addrs-firstname, addrs-lastname, addrs-street.


"Define a nested structure type locally in an ABAP program
TYPES: BEGIN OF stru1,
          fldl TYPE I,
          BEGIN OF stru2,
             fld2 TYPE C,
             fld3 TYPE I,
          END of stru2,
       END OF stru1.

TYPES: BEGIN of addr1,
          street_no TYPE C LENGTH 30,
          city TYPE C LENGTH 20,
          state TYPE C LENGTH 30,
          country TYPE C LENGTH 20,
       END OF addr1.

TYPES: BEGIN OF contact_det,
          firstname TYPE C LENGTH 20,
          lastname TYPE C LENGTH 20,
          address TYPE addr1,
          phoneno TYPE C LENGTH 15,
       END OF contact_det.

"Syntax to create a table type
"TYPES: <Table_type> TYPE <tablekind> OF <linetype> [WITH <key>].
TYPES: BEGIN OF flightinfo,
          carrid TYPE s_carr_id,
          carrname TYPE s_carrname,
          connid TYPE s_conn_id,
          fldate TYPE SY-DATUM,
          fltime TYPE s_fltime,
       END OF flightinfo.

TYPES: itab TYPE SORTED TABLE OF flightinfo
            WITH UNIQUE KEY carrid.

"Syntax for MESH Declaration
TYPES:
      BEGIN OF line1,
        col1 TYPE I,
      END OF line1,
      t_itab1 TYPE SORTED TABLE OF line1
                   WITH NON-UNIQUE KEY col1,
      BEGIN OF line2,
        col1 TYPE I,
        col2 TYPE I,
      END OF line2,
      t_itab2 TYPE SORTED TABLE OF line2
                   WITH NON-UNIQUE KEY col1 col2,
      BEGIN OF MESH t_mesh,
         snode1 TYPE t_itab1
            ASSOCIATION to_node2 TO snode2 ON col1 = col1,
         snode2 TYPE t_itab2,
      END OF MESH t_mesh.

"Line Type Definition for Internal Table
TYPES: BEGIN OF mat_type,
          material TYPE matnr,
          plant TYPE werks_d,
          qty TYPE P DECIMALS 2,
       END OF mat_type.

"Standard table type definition with refernce to line type
TYPES: itab_type TYPE STANDARD TABLE OF mat_type
                 WITH NON-UNIQUE KEY material.

"Standard table type definition with reference to the table type defined
DATA: itab_lt TYPE itab_type.
"or
"DATA: itab_lt TYPE STANDARD TABLE OF mat_type.

"Line type Definition with reference to ABAP Dictionary Structure
TYPES: BEGIN OF mat_ty.
          INCLUDE STRUCTURE mara.
TYPES: END OF mat_ty.

"Internal Table Definition with reference to ABAP Dictionary Table
DATA: itab_lt_01 TYPE STANDARD TABLE OF mara
              WITH NON-UNIQUE KEY matnr.

DATA: itab_wa LIKE LINE OF itab_lt.

DATA: itab TYPE TABLE OF mara INITIAL SIZE 4.
DATA: lt_mara TYPE TABLE OF mara WITH EMPTY KEY.

"Syntax for Sorted and Hashed Table types
TYPES: BEGIN OF line_type,
          material TYPE matnr,
          plant TYPE werks_d,
          po_numb TYPE ebeln,
       END OF line_type.
TYPES: itab01 TYPE SORTED TABLE OF line_type
              WITH UNIQUE KEY material plant.
TYPES: itab02 TYPE HASHED TABLE OF line_type
              WITH UNIQUE KEY material plant.

"Sorted Internal Table Data Objects
DATA: itab01_lt TYPE itab01.
"or
"DATA:  itab01_lt TYPE SORTED TABLE OF line_type
"                 WITH UNIQUE KEY material plant.

"Define Internal table
DATA: itab_01 TYPE SORTED TABLE OF marc
           WITH  UNIQUE KEY matnr werks.

"Hashed internal table data objects
DATA: itab02_lt TYPE itab02.
"or
"DATA: itab02_lt TYPE HASHED TABLE OF line_type
"                WITH UNIQUE KEY material plant.
DATA: itab03 TYPE HASHED TABLE OF marc
             WITH UNIQUE KEY matnr werks.

"Definition of Internal table with header line
DATA: BEGIN OF itab_lt_001 OCCURS 0,
        material LIKE mard-matnr,
        plant LIKE mard-werks,
        mat_desc LIKE makt-maktx,
        stock LIKE mard-labst,
      END OF itab_lt_001.

" DATA: BEGIN OF itab_lt OCCURS 0,
"         material TYPE matnr,
"         plant TYPE werks_d,
"         mat_desc TYPE maktx,
"         stock TYPE labst,
"       END OF itab_lt.

"Definition of Internal table with header line
TYPES: BEGIN OF itab_ty,
         matnr TYPE matnr,
         werks TYPE werks,
         maktx TYPE maktx,
         labst TYPE labst,
       END OF itab_ty.
DATA: itab_lt_0001 TYPE itab_ty OCCURS 0 WITH HEADER LINE.

"Syntax to populate an internal table with a select clause
" DATA: itab_wa TYPE mara.
" DATA: mara_lt TYPE STANDARD TABLE OF mara.
" SELECT * FROM mara INTO TABLE mara_lt.
"Syntax to append
"APPEND itab_wa to itab_lt
"APPEND lines OF itab1 TO itab2.
"APEEND lines OF itab1 FROM 1 TO 50 TO itab2.
"""""""""""""""""""""""""""""""""

"Code for the INSERT statement
START-OF-SELECTION.
    TYPES: BEGIN OF line,
             material TYPE matnr,
             plant TYPE werks_d,
             quantity TYPE menge_d,
           END OF line.
    DATA: itab01 TYPE SORTED TABLE OF line
                 WITH UNIQUE KEY material.
    DATA: itab_wq TYPE line.
          itab_wq-material = 'M2'.
          itab_wq-plant = '1000'.
          itab_wq-quantity = 100.
    INSERT itab_wq INTO TABLE itab01.
    itab_wq-material = 'M1'.
    itab_wq-plant = '1000'.
    itab_wq-quantity = 200.
    INSERT itab_wq INTO TABLE itab01.
    itab_wq-material = 'M3'.
    itab_wq-plant = '1000'.
    itab_wq-quantity = 100.
    INSERT itab_wq INTO TABLE itab01.
END-OF-SELECTION.
```