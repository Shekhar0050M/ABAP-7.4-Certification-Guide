# ABAP-7.4-Certification-Guide
 A repository containing detailed guidelines for SAP ABAP

## Cover
## SAP Press
## Title Page
## Copyright
## Contents
## Acknowledgments
### The Authors
- David Haslam
- Puneet Asthana
## Preface
### Structure of this Book
- Part 1
- Part 2
### Glimpse into the Exam Structure
- Competency level - A, B, C, D
- Exam topic
### Practice Questions
1. Question Stimulus - varies but intention is scenario specific
2. Actual Question
3. Question Hint
4. Answers
   - Multiple response - more than one choice
   - Multiple choice - one choice at a time
   - True/False
   - Fill in the blanks
5. Sequence/Ranking - mark the correct option in sequence  
### Summary
Practice with sample tests, read document, apply for certification, pass and get the certificate.
## Part 1: General Introduction
### ABAP Development Certification Track: Overview
#### Certification Exam Scoring Changes
##### Certification Levels
1. Associate: 1-3 years of knowledge and experience
2. Professional
3. Master
##### Advanced Certification Levels
 One round sitting examination could be attempted 3 times a year only. After failing, wait for 30 days for next attempt. Fee doesn't varies.
#### Becoming an SAP Certified ABAP Development Associate: Overview
1. C_TAW12_740
2. SAP Certified Development Associate—ABAP with SAP NetWeaver 7.40
#### Associate Examination Specifics
1. Software components: SAP NetWeaver 7.40
2. Number of questions: 80
3. Duration: 180 minutes
### Courses and Experience
#### Training Courses for ABAP
1. TAW 10
2. TAW 11
3. TAW 12
4. BC400
5. BC401
6. BC402
7. BC405
8. BC414
9. BC425
10. BC430
11. NET310
12. NW001
#### Sources of information
1. SAP Community Network (SCN) - http://scn.sap.com
2. SAP Help Portal - http://help.sap.com
#### Strategic Understanding
- Monitor your comprehension
- Always check the logic behind the ideas
- Watch out for anything that seems counter intuitive
- Test your own understanding
- Generate your own examples
- Think in pictures, shapes and colors
- Use mnemonics/memory-training devices for important ideas.
- Use repetition
#### SAP Examination Strategies
 There is never a strategy. Just drink lots of water.
#### General Examination Strategies
 There is never a strategy. Just drink lots of water.
#### Summary
 Additional sources of information that can be useful for the certification examination.
## Part 2: Exam Preparation
### SAP NetWeaver: Overview
#### Objectives of this Portion of the Test
### ABAP Workbench Usage
1. Objectives of this Portion of the Test
   - ABAP Workbench and development tools
   - ABAP Workbench settings
   - The use of various browsers in the ABAP Workbench
   - The Front-End Editor and the settings to improve productive
   - Development Packages and Transport Organizer
2. Key Concepts Refresher
3. ABAP Workbench
4. Repository Browser
5. Repository Information System
6. Workbench Settings
7. ABAP Editor and Workbench Settings
8. ABAP Workbench Tools in Detail
9. Enhancement Information System
10. Packages and Their Attributes
11. Transport Organizer
12. Practice Questions
13. Practice Question Answers and Explanations
14. Takeaway
15. Refresher
16. Summary
### ABAP Debugger Program Usage
1. Various ways to start the debugger
2. Breakpoints
3. Watchpoints
4. Assertions
5. Viewing and modifying data objects
6. Understanding the architecture of the debugger
7. Key Concepts Refresher
   - New and Classic Debugger
      - SYSTEM -> UTILITIES -> DEBUG ABAP or SYSTEM -> UTILITIES -> DEBUG SCREEN
      - shortcut: /h and press ENTER
      - Execute debugging 
      - Select desired line AND select SET/DELETE breakpoint 
   - New Debugger Tools and UI
   - Assertions and Breakpoints
   - New Debugger Customization and Settings
      - SY-SUBRC: system variable containing the statement return code
      - SY-TABIX: system varible containing the internal table row last accessed
      - SY-DATUM: show system current date
      - SY-UZEIT: show system current time
      - SY_UNAME: show userID of current user
### ABAP Types and Data Objects
1. Objectives
   - Data types and data objects
   - Predefined and generic data types
   - Valid operations on the various data objects and their usage in programs
   - Local data types and the global data types
   - Structure declarations and the differences between flat, nested and deep structures
2. Key concepts refresher
   - difference betweeen predefined and generic data types and their usage within the program
   - syntax of the data declaration
   - valid operations of the data objects

## ABAP Types and Data Objects
1. Data types - Data types are used for the definition of data objects - define technical attributes of data objects - define how data stored in memory - operations are possible on the data objects based on the data type - used for definition of interface parameters - used for input output field  in the ABAP programs - used to declare PARAMETERS and SELECT-OPTIONS for program selection screens and dynpro screen fields 
2. Data types 
   - Predefined data types
   - Local data types 
   - Global data types
      - ABAP dictionary objects
      - ABAP dictionary type group
![alt text](images/ABAP%20Data%20Types.png)
3. Data objects - Data objects are temporary storage in the program and occupy memory to store data.
      - Literals - unnamed data objects with fixed values
      - Numeric literals - sequence of digits that contain a plus or minus sign - value ranges from -2^31+1 to 2^31-1 - WRITE: 12345.
      - Text field literals - sequence of cahracters in inverted commas - value ranges from 1 to 255 characters in length - WRITE: 'A text literal'.
      - String literals - sequence of characters enclosed with back quotes - WRITE: `A STRING literal`
      - Constants - named data objects with fixed values and defined statically using a declarative statement - CONSTANTS: c_nump TYPE P DECIMALS 3 VALUE '123.657'. c_city TYPE C LENGTH 10 VALUE 'BERLIN'
      - Text Symbols - TEXT-XXX, where XXX is the text ID  for the text symbol maintained in the text pool - WRITE text-001. WRITE 'THIS is an English text'(002). - SE11 -> syst
      - Predefined data objects - ABAP dictionary - SYST
![alt text](images/ABAP%20Dictionary%20Structure%20SYST.png)
      - Variables - data objects - allows to store data locally for the program in memory
      - DATA keyword - declare data 
      ```
      DATA: count type I, count2 TYPE I value 10.
      DATA: itab TYPE STANDARD TABLE OF mara. 
      SELECT matnr bismt FROM mara INTO CORRESPONDING FIELDS OF TABLE itab WHERE mtart EQ 'FERT'. 
      LOOP AT itab INTO DATA(wa). 
      WRITE:/ wa-matnr, wa-bismt. 
      ENDLOOP. 
      READ TABLE itab WITH KEY matnr = '1400-500' INTO DATA(wa2). 
      DATA: itab TYPE STANDARD TABLE OF mara. 
      LOOP AT itab ASSIGNING FIELD-SYMBOL(<line>). 
      WRITE:/ <line>-matnr, <line>-bismt. 
      ENDLOOP. 
      READ TABLE itab WITH KEY matnr ='ABC' ASSIGNING FIELD-SYMBOL(<line2>). 
      oref->meth( IMPORTING p1 = DATA(a1)IMPORTING p2 = DATA(a2)... ).
      ```
      - STATICS - declare the data with the static validity within the procedure 
      ```
      REPORT DEMO_STATIC_DATA_OBJECT. 
      DO 5 TIMES. 
      PERFORM dataobject_example. 
      ENDDO. 
      FORM dataobject_example. 
      DATA count1 TYPE I. 
      STATICS count2 TYPE I. 
      count1 = count1 + 1. 
      count2 = count2 + 1. 
      WRITE: / 'Count1: ', count1, 'Count2: ', count2. 
      ENDFORM.
      --OUTPUT--
      Count1: 1 Count2: 1 
      Count1: 1 Count2: 2 
      Count1: 1 Count2: 3 
      Count1: 1 Count2: 4 
      Count1: 1 Count2: 5
      ```
      - The *variable count1 does not retain the value* because it is declared with the *DATA* keyword, whereas the variable count2, declared with the *STATICS* keyword, *retains the value for the runtime of the program*.
   - CLASS-DATA: declare a static attribute for the class - is valid for all instances  of the class within the program
   - PARAMETERS: declare an elementary data object - displayed as input field on the selection screen
   - SELECT-OPTIONS: declare an internal table - displayed as input field on selection screen 
## ABAP Data types - predefined data types provided by the ABAP runtime environment
1. Four character types 
   - Numeric types (N) 
   - Character text(C)
   - Data type(D)
   - Time type(T) - each character occupies 2 to 4 bytes
2. Three numeric types 
   - Integer (I)
   - Floating point numbers(F)
   - packed number(P) - used to display and calculate numbers
3. Integer type - whole number
   ```
   DATA: num1 TYPE I value 5. 
         num2 TYPE I VALUE 2. 
         Result TYPE I. 
   Result = num1 / num2.
   ```
4. STRING - variable-length character string 
5. XSTRING - variable-length hexadecimal byte sequence ::: {TYPES: , DATA: }
## Local Data types - present inside ABAP program and are visible to the program only 
```
TYPES: <type_name> ... [TYPE <ABAP-Type> |   LIKE <obj>].
TYPES: BEGIN OF Address_ty. 
         firstname TYPE C LENGTH 20 lastname TYPE C LENGTH 20. 
         street  TYPE C LENGTH 20. 
         city TYPE C LENGTH 20. 
       END OF address_ty.
DATA: addrs TYPE address_ty. 
      addrs-firstname = 'Bob', 
      addrs-lastname = 'Johnson', 
      addrs-street = '123 Adam Lane'. 
WRITE: addrs-firstname,
       addrs-lastname, 
       addrs-street.
TYPES: BEGIN OF stru1, 
         fld1 TYPE I, 
         BEGIN OF stru2, 
            fld2 TYPE C, 
            fld3 TYPE I, 
         END OF stru2, 
       END of stru1
TYPES: <Table_type> TYPE <tablekind> OF <linetype> [WITH <key>].
```
## Global data types - a available system- wide
1. To define a data object that refers to a data type defined in the type group SLIS, you have to declare the type group in the ABAP program with the syntax TYPE-POOLS: SLIS and then define the data object with reference to the data type defined in the type group.
   - TYPE-POOLS: SLIS.
   - DATA: fieldcat TYPE slis_t_fieldcat_alv.
## Data Object Visibility
   - Visibility of the data object is dependent on the context of the variable
   - Variable defined with DATA statement - subroutine between FORM and ENDFORM, it is local data object for the subroutine - data is not visible and is not accessible outside the subroutine
   - If data is inside function module, then it is a local data object for the function module.
   - Data-objects at start of the program - with DATA, PARAMETERS or SELECT-OPTIONS - visible to entire program and are global data objects
   - Data object is declared between MODULE and ENDMODULE of PAI or PBO module for the screen
   - Data objects are defined with TABLES - visible to entire program 
### Internal Table Definition and Use
1. Internal tables - program variables and store multiple identical structured data records in the ABAP runtime memory - process large data sets in a structured manner 
2. Data types - Line Type and Table Key
3. Types of tables - Standard tables, Sorted tables, Hashed tables, Indexed, Not specified
4. Table key is pimary key - primary_key
5. Components of primary key declared using - UNIQUE, NON-UNIQUE KEY, specified
6. Move-corresponding statements is used to move the identical rows from internal table from itab1 to itab2  
7. COLLECT keyword is used to populate an internal table 
### SQL Statements Including Update Strategies
1. Data Modelling - implement appropriate table definitions, including their relationships with each other in ABAP Dicitionary
2. Data Retrieval - SAP provides openSQL - openSQL statements are dynamically converted to corresponding native sql - independent of database
   - Types of reuse components encapsulate databse access: 
      - Logical databases
      - Function modules
      - BAPIs
      - Method of global classes
![alt text](images/SAP%20LUW%20within%20a%20Database%20LUW.png)
![alt text](images/Locking%20Data%20through%20Database%20LUWs.png)
3. Lock modes
   - E - Extensible - lock for data change - accumulative
   - X - Exclusive - lock for data change - exclusive
   - S - Shared - locked for protective data display - shared lock
![alt text](images/Process%20Flow%20of%20an%20Update.png)
### Basic ABAP Programs and Interface Creation
![alt text](images/Project%20Timeline%20of%20a%20Change%20Request.png)
- Executable programs (REPORT)
- Module pools (PROGRAM)
- Function groups (FUNCTION-POOL)
- Class pools (CLASS-POOL)
- Interface pools (INTERFACE-POOL)
- Subroutine pools (PROGRAM)
- Type groups (TYPE-POOL)
4. ABAP Event Blocks
   - LOAD-OF-PROGRAM - triggered when the program is initially loaded into memory
   - INITIALIZATION - triggered by the actual start of the program
   - START-OF-SELECTION - triggered when program has completed all selection screen events
   - GET node - event block whose result is triggered by the ABAP runtime environment
   - END-OF-SELECTION - data read by the logical database can be processed
   - AT SELECTION-SCREEN - defines event blocks  that is triggered by the ABAP runtime environment during selection screen processing 
   - TOP-OF-PAGE - triggered by ABAP runtime environment during the creation of a list
   - END-OF-PAGE - triggered by ABAP runtime environment during the creation of a basic list
   - AT LINE-SELECTION - display of screen list event is triggered by ABAP runtime environment
   - AT USER-COMMAND - display of a screen list event is triggered by the ABAP runtime environment
- ABAP syntax is platform-independent
![alt text](images/Method%20Parameters.png)
![alt text](images/Method%20Exceptions.png)
-  AUTHORITY-CHECK - code an authorization check
- Dialog Messages 
### ABAP Dictionary
- Data elements - elementary ABAP Dictionary type - describe a single field or data element
- Structures - complex data type consists of multiple components
- Table types -  complete description of internal table
1. Basic and Complex data types
   - Domains - ABAP dictionary object that is used to describe technical attributes of a data element 
   - CONVERSION_EXIT_XXXXX_INPUT - display format of SAP internal format 
   - CONVERSION_EXIT_XXXXX_OUTPUT - converts the SAP internal format to the display format 
   - Structures consists of sequence of components
   - Table type for ABAP Dicitionary
      - Line type - defines the structure and the data type of the internal table
      - Access mode - access the data in the internal table
      - Key - specify the key for the internal table
### Unicode
### Classical Screens
![alt text](images/Context%20Menu%20to%20Create%20Program%20Objects.png)
### Selection Screens
### ABAP Object-Oriented Programming
![alt text](images/Instance%20and%20Static%20Components%20Declaration.png)
![alt text](images/Attribute%20Declaration%20in%20a%20Class.png)
### ALV Grid Control

### User Interface (Web Dynpro)

### Class Identification Analysis and Design
### Enhancements and Modifications

### Table Relationships
### The Authors
### Index
*------ Transaction Codes ------*
- PA30 - Maintain HR Master Data
- SE38 - ABAP Editor: Initial Screen - Create Program
- SE16 - Data Browser: Initial Screen - Table Name
- SE11 - ABAP Dictionary: Initial Screen 
   - Create database
   - view
   - data type
   - type group
   - domain
   - search help
   - lock object
- SE24 - Class Builder: Initial Screen - Object type
- SE80 - Object Navigator
- SU53 - Display Authorization Data for User ??????
- SE24 - Class Builder - Intitial Screen
*------ SYSTEM VARIABLES ------*
- SY-DATUM -  current date
- SY-UZEIT - Current time
- SY-UNAME - User ID of current user
- SY-SUBRC - it is a return value and it seems that it will contain value as per the preceding line of code executed, 0 for success
- SY-TABIX - find the current line in the internal table 
- SY-INDEX - gives the number of loop passes - E.G. in DO loop
```
REPORT ZSHEKHAR01.
```
```
WRITE:12345.
```
```
WRITE: 'A text literal'.
```
```
WRITE: `A STRING literal`.
```
```
CONSTANTS: c_nump TYPE P DECIMALS 3 VALUE '123.657',
           c_city TYPE C LENGTH 10 VALUE 'BERLIN'.
```
```
WRITE text-001.
WRITE 'THIS is an English text'(002).
```
```
DATA: count TYPE I,
      count2 TYPE I VALUE 10.
```
```
"Declaration of field symbols
DATA: itab TYPE STANDARD TABLE OF mara.

SELECT matnr bismt FROM mara
       INTO CORRESPONDING FIELDS OF TABLE itab
       WHERE mtart EQ 'FERT'.

LOOP AT itab INTO DATA(wa).
     WRITE:/ wa-matnr, wa-bismt.
ENDLOOP.

READ TABLE itab WITH KEY matnr = '1400-500' INTO  DATA(wa2).
```
```
"Declaration of actual parameters
DATA: itab TYPE STANDARD TABLE OF mara.

LOOP AT itab ASSIGNING FIELD-SYMBOL(<line>)
     WRITE:/ <line>-matnr, <line>-bismt.
ENDLOOP.

READ TABLE itab WITH KEY matnr = 'ABC'
     ASSIGNING FIELD-SYMBOL(<line2>).
```

```
"Declaration of Table Work Area
oref->meth( IMPORTING p1 = DATA(a1)
      IMPORTING p2 = DATA(a2)
...).
```
```
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
```
```
"Usage of Data Keyword
DATA: var1 TYPE I.
DATA: var2 LIKE var1.
DATA: var3  TYPE STRING VALUE 'Hello'.
DATA: num1 TYPE I VALUE 5,
      num2 TYPE I VALUE 2,
      RESULT TYPE I.
      RESULT = num1 / num2.
DATA: pack_num1 TYPE P LENGTH 8 DECIMALS 2,
      pack_num2 TYPE P LENGTH 8 DECIMALS 2 VALUE '2.55'.
DATA: dec_num1 TYPE decfloat16,
      dec_num2 TYPE decfloat34.
DATA: hex(1) TYPE X VALUE '09'.
```
```
"Syntax to declare incompete data types
DATA var1 TYPE C.         "character variable of length 1
DATA: var2(3) TYPE C.         "character variable of length 3
DATA: var3 TYPE C LENGTH 3.         "character variable of length 3
```
```
"Syntax for data types and data objects
TYPES: v_char1(2) TYPE C.
TYPES: v_char2 TYPE C LENGTH 10.
TYPES: num1 TYPE P DECIMALS 2.
DATA: name(20) TYPE C.
DATA: price TYPE P DECIMALS 2.
```
```
TYPES: <type_name> ... [TYPE <ABAP-Type> | LIKE <obj> ].
TYPES: char1 TYPE C LENGTH 8,
       num1 TYPE N LENGTH 6,
       pack1 TYPE P LENGTH 3 DECIMALS 2.
```
```
"Define the structure data type in an ABAP program
TYPES: BEGIN OF address_ty,
             firstname TYPE C LENGTH 20,
             lastname TYPE C LENGTH 20,
             street TYPE C LENGTH 30,
             city TYPE C LENGTH 20,
       END OF address_ty.
```
```
"Access individual components of the structure data  type in the program
DATA: addrs TYPE address_ty,
      addrs-firstname = 'Bob',
      addrs-lastname = 'Johnson',
      addrs-street = '123 Adam Lane'.
WRITE: addrs-firstname, addrs-lastname, addrs-street.
```
```
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
```
```
"Syntax to create a table type
TYPES: <Table_type> TYPE <tablekind> OF <linetype> [WITH <key>].
TYPES: BEGIN OF flightinfo,
          carrid TYPE s_carr_id,
          carrname TYPE s_carrname,
          connid TYPE s_conn_id,
          fldate TYPE SY-DATUM,
          fltime TYPE s_fltime,
       END OF flightinfo.

TYPES: itab TYPE SORTED TABLE OF flightinfo
            WITH UNIQUE KEY carrid.
```
```
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
```
```
"Line Type Definition for Internal Table
TYPES: BEGIN OF mat_type,
          material TYPE matnr,
          plant TYPE werks_d,
          qty TYPE P DECIMALS 2,
       END OF mat_type.
```
```
"Standard table type definition with refernce to line type
TYPES: itab_type TYPE STANDARD TABLE OF mat_type
                 WITH NON-UNIQUE KEY material.

```
```
"Standard table type definition with reference to the table type defined
DATA: itab_lt TYPE itab_type.
"or
DATA: itab_lt TYPE STANDARD TABLE OF mat_type.
```
```
"Line type Definition with reference to ABAP Dictionary Structure
TYPES: BEGIN OF mat_ty.
          INCLUDE STRUCTURE mara.
TYPES: END OF mat_ty.
```
```
"Internal Table Definition with reference to ABAP Dictionary Table
DATA: itab_lt_01 TYPE STANDARD TABLE OF mara
              WITH NON-UNIQUE KEY matnr.

DATA: itab_wa LIKE LINE OF itab_lt.

DATA: itab TYPE TABLE OF mara INITIAL SIZE 4.
DATA: lt_mara TYPE TABLE OF mara WITH EMPTY KEY.
```
```
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
```
```
"Sorted Internal Table Data Objects
DATA: itab01_lt TYPE itab01.
"or
DATA:  itab01_lt TYPE SORTED TABLE OF line_type
                 WITH UNIQUE KEY material plant.
```
```
"Define Internal table
DATA: itab_01 TYPE SORTED TABLE OF marc
           WITH  UNIQUE KEY matnr werks.

```
```
"Hashed internal table data objects
DATA: itab02_lt TYPE itab02.
"or
DATA: itab02_lt TYPE HASHED TABLE OF line_type
                WITH UNIQUE KEY material plant.
DATA: itab03 TYPE HASHED TABLE OF marc
             WITH UNIQUE KEY matnr werks.
```
```
"Definition of Internal table with header line
DATA: BEGIN OF itab_lt_001 OCCURS 0,
        material LIKE mard-matnr,
        plant LIKE mard-werks,
        mat_desc LIKE makt-maktx,
        stock LIKE mard-labst,
      END OF itab_lt_001.

 DATA: BEGIN OF itab_lt OCCURS 0,
         material TYPE matnr,
         plant TYPE werks_d,
         mat_desc TYPE maktx,
         stock TYPE labst,
                END OF itab_lt.
```
```
"Definition of Internal table with header line
TYPES: BEGIN OF itab_ty,
         matnr TYPE matnr,
         werks TYPE werks,
         maktx TYPE maktx,
         labst TYPE labst,
       END OF itab_ty.
DATA: itab_lt_0001 TYPE itab_ty OCCURS 0 WITH HEADER LINE.
```
```
"Syntax to populate an internal table with a select clause
DATA: itab_wa TYPE mara.
 DATA: mara_lt TYPE STANDARD TABLE OF mara.
 SELECT * FROM mara INTO TABLE mara_lt.
"Syntax to append
APPEND itab_wa to itab_lt
APPEND lines OF itab1 TO itab2.
APEEND lines OF itab1 FROM 1 TO 50 TO itab2.
```
```
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
```
INSERT LINES OF itab1 FROM <idx1> TO <idx2> INTO TABLE itab2.
```
```
MOVE-CORRESPONDING itab1 TO itab2.
```
```
"Syntax for move corresponding for internal tables
WRITE 'MOVE-CORRESPONDING FOR INTERNAL TABLES'.
TYPES: BEGIN OF ty_marc1,
          matnr TYPE matnr,
          werks TYPE werks,
          ekgrp TYPE ekgrp,
          dismm TYPE dismm,
          dispo TYPE dispo,
       END OF ty_marc1.
TYPES: BEGIN OF ty_marc2,
          matnr TYPE matnr,
          werks TYPE werks,
          ekgrp TYPE ekgrp,
       END OF ty_marc2.
TYPES: BEGIN OF ty_itab1,
          matnr TYPE matnr,
          bismt TYPE bismt,
          marc TYPE STANDARD TABLE OF ty_marc1 WITH EMPTY KEY,
       END OF ty_itab1.
TYPES: BEGIN OF ty_itab2,
          matnr TYPE matnr,
          bismt TYPE bismt,
          marc TYPE STANDARD TABLE OF ty_marc2 WITH EMPTY KEY,
       END OF ty_itab2.
DATA: matplant TYPE STANDARD TABLE OF ty_marc1,
      itab1 TYPE STANDARD TABLE OF ty_itab1,
      itab2 TYPE STANDARD TABLE OF ty_itab2.
SELECT matnr bismt FROM mara
       INTO CORRESPONDING FIELDS OF TABLE itab1
       WHERE mtart = 'FERT'.
LOOP AT itab1 INTO DATA(wa).
SELECT matnr werks ekgrp dismm dispo FROM marc
       INTO TABLE matplant
       WHERE matnr = wa-matnr.
MOVE-CORRESPONDING matplant TO wa-marc.
MODIFY itab1 FROM wa TRANSPORTING marc.
CLEAR matplant.
ENDLOOP.
MOVE-CORRESPONDING itab1 TO itab2 EXPANDING NESTED TABLES.
```
```
"Does not delete existing contents of itab2
MOVE-CORRESPONDING itab1 TO itab2 KEEPING TARGET LINES.
```
```
"Syntax of COLLECT Statement of Internal table
WRITE: / `Syntax of COLLECT Statement of Internal table`.
TYPES: BEGIN OF line_01,
          matnr TYPE matnr,
          qty1 TYPE I,
       END OF line_01.
DATA: itab_wa_01 TYPE line_01.
DATA: itab_001 TYPE STANDARD TABLE OF line_01.
      itab_wa_01-matnr = 'M1'.
      itab_wa_01-qty1 = 10.
COLLECT itab_wa_01 INTO itab_001.
WRITE: /  'Index of inserted/modified line'.
WRITE: / sy-tabix.
itab_wa_01-matnr = 'M2'.
itab_wa_01-qty1 = 20.
COLLECT itab_wa_01 INTO itab_001.
WRITE: / sy-tabix.
itab_wa_01-matnr = 'M1'.
itab_wa_01-qty1 = 10.
COLLECT itab_wa_01 INTO itab_001.
WRITE: / sy-tabix.
itab_wa_01-matnr = 'M2'.
itab_wa_01-qty1 = 40.
COLLECT itab_wa_01 INTO itab_001.
WRITE: / sy-tabix.
Clear itab_wa_01.
LOOP AT itab_001 into itab_wa_01.
WRITE: / itab_wa_01-matnr, itab_wa_01-qty1.
ENDLOOP.
```
```
"Syntax to read Internal table lines
DATA: itab_wa TYPE marc,
itab_lt TYPE STANDARD TABLE OF marc.
FIELD-SYMBOLS: <fs> TYPE marc.
READ TABLE itab INDEX 10 INTO itab_wa.
```
```
"Code to append and modify and internal table
WRITE: / `Code to append and modify and internal table`.
TYPES: BEGIN OF line,
          matnr TYPE matnr,
          qty1 TYPE I,
       END OF line.
DATA: itab_wa TYPE line.
DATA: itab_lt TYPE STANDARD TABLE OF line.
itab_wa-matnr = 'M1'.
itab_wa-qty1 = 10.
APPEND itab_wa to itab_lt.
itab_wa-matnr = 'M2'.
itab_wa-qty1 = 20.
APPEND itab_wa to itab_lt.
itab_wa-matnr = 'M3'.
itab_wa-qty1 = 30.
APPEND itab_wa to itab_lt.
LOOP AT itab_lt WHERE matnr = 'M1'. INTO itab_wa.
itab_wa-qty1 = 100.
MODIFY itab_lt FROM itab_wa TRANSPORTING qty1.
ENDLOOP.
SELECT * from KNA1 INTO CORRESPONDING FIELDS OF TABLE itab02.
 SORT itab02 by kunnr.
 READ TABLE itab02 WITH KEY kunnr = '12345'
 INTO wa BINARY SEARCH.
```
```
"Syntax for the LOOP statement
TYPES: BEGIN OF itab_ty,
          matnr TYPE matnr,
          werks TYPE werks_d,
       END OF itab_ty.
DATA: itab_lt TYPE STANDARD TABLE OF itab_ty.
DATA: wa LIKE LINE OF itab_lt.
SELECT matnr werks FROM marc INTO TABLE itab_lt.
LOOP at itab_lt into wa.
     WRITE: / wa-matnr, wa-werks.
ENDLOOP.

"LOOP examples
LOOP AT itab_lt INTO wa WHERE matnr = '12345'.
WRITE: / wa-matnr, wa-werks.
ENDLOOP.

LOOP AT itab_lt FROM 1 TO 10 INTO wa.
WRITE: / wa-matnr, wa-werks.
ENDLOOP
```
```
"Modify table with specified components only i.e. fld1 and fld2
MODIFY TABLE itab FROM wa TRANSPORTING fld1 fld2.
```
```
"Using delete statement to delete line from internal tables
DELETE itab INDEX idx.
DELETE itab FROM idx1 TO idx2.
DELETE itab WHERE MATERIAL = '12345'.
DELETE ADJACENT DUPLICATES FROM itab COMPARING material plant.
DELETE ADJACENT DUPLICATES FROM itab.
DELETE TABLE itab WITH TABLE KEY material = '12345' plant = 'abcd'.
```
```
"Using sort method
SORT itab.
SORT itab ascending.
SORT itab descending.
SORT itab BY material plant DESCENDING.
SORT itab AS TEXT.
SORT itab by (stab).
```
```
"Empty the internal table
"Deletes or intializes the internal table body lines
CLEAR itab[].
REFRESH itab.
"Clears the header line
CLEAR itab.
"Clear the header line and body of internal table
CLEAR: itab, itab[].
"or
CLEAR: itab.
REFRESH itab.
```
```
"Table body is deleted and memory area for the reserved internal table is released
FREE itab.
```
```
"Ways of accessing a row in a table
DATA(wa) = itab[2].
DATA(wa) = itab[matnr = '123' werks = '1000'].
DATA(wa) = itab[ KEY primary_key COMPONENTS matnr = '1400-500' werks = '1000' ].
```
```
"Line Index to identify the index of a row in an internal table
LINE_INDEX( table_exp ).
DATA(idx1) = LINE_INDEX( itab[ matnr = '1400-500' werks = '1000' ] ).
WRITE:/ 'index:-' , idx1.
```
```
"Example code for line exists
IF line_exists( itab[ matnr = '1400-500' werks = '1000' ] ).
  DATA(wa2) = itab[ KEY primary_key COMPONENTS matnr = '1400-500' werks = '1000' ].
  WRITE:/ 'Line exists', wa-matnr, wa-werks.
ENDIF.
```
```
"SELECT example
SELECT fldate planetype seatsocc seatsmax
FROM sflight
INTO (fldate,planetype,seatsocc,seatsmax)
WHERE carrid = flight-carrid
AND connid = flight-connid.
ENDSELECT.
```
```
SELECT *
FROM sflight
LEFT JOIN scarr
ON sflight~carrid = scarr~carrid
INTO CORRESPONDING FIELDS OF TABLE gt_sflight
WHERE sflight~carrid IN s_carrid
AND sflight~connid IN s_connid
AND sflight~fldate IN s_fldate.
```
```
"Call to an lock object
CALL FUNCTION 'ENQUEUE_ESRDIRE'
EXPORTING
mode_trdir = l_enq_mode
name = incl2
x_name = ' '
_scope = '2'
_wait = ' '
EXCEPTIONS
foreign_lock = 01
system_failure = 02.
IF sy-subrc NE 0 AND rs38l-extern = space.
MESSAGE ID sy-msgid
TYPE 'E'
NUMBER sy-msgno
WITH sy-msgv1 sy-msgv2 sy-msgv3 sy-msgv4.
ENDIF.
```
```
"Call to an Update Module
CALL FUNCTION 'WFRULES_WRITE_DOCUMENT' IN UPDATE TASK
EXPORTING
objectid = objectid
tcode = tcode
utime = utime
udate = udate
username = username
planned_change_number = planned_change_number
upd_twfns = upd_twfns
upd_twfsa = upd_twfsa
TABLES
xtwfns = xtwfns
ytwfns = ytwfns
xtwfsa = xtwfsa
ytwfsa = ytwfsa.
```
```
"Code of an update module
FUNCTION wfrules_write_document .
CALL FUNCTION 'CHANGEDOCUMENT_OPEN'
EXPORTING
objectclass = 'WFRULES '
objectid = objectid
planned_change_number = planned_change_number
planned_or_real_changes = planned_or_real_changes
EXCEPTIONS
sequence_invalid = 1
OTHERS = 2.
CASE sy-subrc.
WHEN 1. MESSAGE a600 WITH 'SEQUENCE INVALID'.
WHEN 2. MESSAGE a600 WITH 'OPEN ERROR'.
ENDCASE.
```
```
"A New Introductory Statement for a Report
REPORT z_new_report
"A Modified Report Introductory Statement
REPORT z_new_report LINE-SIZE 250 NO STANDARD PAGE HEADING MESSAGE-ID z_message_class.
```
```
"Example of a MESSAGE-Based Exception
MESSAGE e008(38) WITH 'FOOBAR' RAISING table_cannot_be_loaded.
```
```
"Example of a Class-Based Exception
RAISE EXCEPTION TYPE cx_sy_dynamic_osql_semantics EXPORTING textid = cx_sy_dynamic_osql_semantics=>unknown_table_name token = 'FOOBAR'.
```
```
"Call to a Subroutine with Both USING and CHANGING
IF cursor_field = 'SOURCE_ID' AND cursor_value NE space.
PERFORM create_request
USING cursor_value
abap_pgeditor->abap_editor->context->context_type
CHANGING l_wb_request.
ELSE.
```
```
"The Subroutine (FORM Routine)
FORM create_request USING p_name TYPE progname
p_type
CHANGING p_l_wb_request.
DATA: l_scope_objects TYPE rinfoobj,
l_scope_objtypes TYPE rseutypes,
l_object_type TYPE seu_objtype,
l_object_name TYPE rsfind.
l_object_type = p_type.
l_object_name = p_name.
CALL METHOD
cl_wb_infosystem=>create_where_used_list_request
EXPORTING
p_object_type = p_object_type
p_object_name = l_object_name
p_scope_objects = l_scope_objects
p_scope_object_types = l_scope_objtypes
IMPORTING
p_wb_request = p_l_wb_request
EXCEPTIONS
execute_in_batch = 1
action_cancelled = 2
error_occured = 3
OTHERS = 4.
ENDFORM. "create_request
```
```
"Method coding
method convert_number_base.
data:
lv_factor type P length 10,
lv_converted_number type P length 10,
lv_src_nbr type C length 99,
lv_iterations type I,
lv_position type I,
lv_max_value type I,
lv_digit type I,
lv_exponent type I.
field-symbols:
<digit> type C.
constants:
lc_starting_factor type I value '19',
lc_number_base type C length 36
value '0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ'.
if source_base is initial or
destination_base is initial.
raise base_not_identified.
endif.
lv_iterations = strlen( lc_number_base ).
```
```
"Calculating Bytes per Character
DATA:
lv_text TYPE C LENGTH 1,
lv_hex TYPE X LENGTH 1,
lv_blen TYPE I,
lv_clen TYPE I,
lv_bytes TYPE I.
DESCRIBE FIELD lv_text: LENGTH lv_blen IN BYTE MODE,
LENGTH lv_clen IN CHARACTER MODE.
lv_bytes = lv_blen / lv_clen.
```
```
"PBO and PAI Module Definition
*&--------------------------------------------*
*& Module INIT_SCREEN_100 OUTPUT
*&--------------------------------------------*
MODULE init_screen_100 OUTPUT.
CLEAR input.
SET PF-STATUS 'STATUS_100'.
radio1 = 'X'.
CLEAR: radio2, radio3.
ENDMODULE. "INIT_SCREEN_100 OUTPUT
*&--------------------------------------------*
*& Module USER_COMMAND_100 INPUT
*&--------------------------------------------*
MODULE user_command_100 INPUT.
output = input.
box1 = radio1.
box2 = radio2.
box3 = radio3.
IF exit NE space.
LEAVE PROGRAM.
ENDIF.
ENDMODULE. "USER_COMMAND_100 INPUT
```
```
"Controlled ABAP Dialog
PROCESS BEFORE OUTPUT.
MODULE init_screen_100.
PROCESS AFTER INPUT.
MODULE user_command_0100.
MODULE module_1.
FIELD box2.
MODULE module_2.
FIELD: box1, box3.
MODULE module_3.
```
```
"Input Check with CHAIN and ENDCHAIN Statements
PROCESS BEFORE OUTPUT.
MODULE init_screen_9001.
PROCESS AFTER INPUT.
MODULE cancel AT EXIT-COMMAND.
FIELD input1 MODULE module_1.
FIELD input2 MODULE module_2.
FIELD input3 MODULE module_3.
CHAIN.
FIELD input4.
MODULE chain_module_1.
FIELD input5.
FIELD input6 MODULE chain_module_2.
ENDCHAIN.
MODULE execution.
```
```
"Input Check Module
*---------------------------------------------*
* MODULE chain_module_1 INPUT
*---------------------------------------------*
MODULE chain_module_1 INPUT.
IF input4 < 10.
MESSAGE w000(fb) WITH text-003 '10' text-002.
ENDIF.
ENDMODULE " CHAIN_MODULE_1 INPUT
*---------------------------------------------*
* MODULE chain_module_2 INPUT
*---------------------------------------------*
MODULE chain_module_2 INPUT.
CLEAR sum.
sum = input4 + input5 + input6.
IF sum <= 100.
MESSAGE e000(fb) WITH text-004 '100' text-002.
ENDIF.
ENDMODULE. " CHAIN_MODULE_2 INPUT
```
```
"Conditional ABAP Dialog
PROCESS BEFORE OUTPUT.
MODULE init_screen_9002.
PROCESS AFTER INPUT.
MODULE cancel AT EXIT-COMMAND.
CHAIN.
FIELD: input1, input2.
MODULE chain_module_1 ON CHAIN-INPUT.
FIELD input3
MODULE chain_module_2 ON CHAIN-REQUEST.
ENDCHAIN.
```
```
"Module for AT EXIT-COMMAND
*&--------------------------------------------*
*& Module CANCEL INPUT
*&--------------------------------------------*
MODULE cancel INPUT.
CASE ok_code.
WHEN 'BACK'.
LEAVE.
SET SCREEN 0.
LEAVE SCREEN.
WHEN 'EXIT'.
LEAVE.
SET SCREEN 0.
LEAVE SCREEN.
WHEN 'CANCEL'.
SET SCREEN 0.
LEAVE SCREEN.
ENDCASE.
LEAVE PROGRAM.
ENDMODULE. " CANCEL INPUT
```
```
"Input Check in Screen Flow Logic
PROCESS BEFORE OUTPUT.
MODULE init_screen_0100.
PROCESS AFTER INPUT.
MODULE cancel AT EXIT-COMMAND.
FIELD carrier VALUES (not 'AA', 'LH', between 'QF' and 'UA').
MODULE module_1.
FIELD connect SELECT *
FROM spfli
WHERE carrid = carrier AND connid = connect
WHENEVER NOT FOUND SEND ERRORMESSAGE 107
WITH carrier connect.
MODULE module_2.
```
```
"Example Code to Deactivate Function Code
MODULE status_0100 output.
APPEND 'CHANGE' TO fcode.
APPEND 'CHANGE' TO fcode.
SET PF-STATUS 'STATUS_100' EXCLUDING fcode.
ENDMODULE.
```
```
"Template for ABAP Class
CLASS CL1 DEFINITION.
PUBLIC SECTION.
DATA: d1, d2.
METHODS: M1.
EVENTS: EV1.
PROTECTED SECTION.
DATA: d3, d4.
METHODS: M2.
EVENTS: EV2.
PRIVATE SECTION.
DATA: d5, d6.
METHODS: M3.
EVENTS: EV3.
ENDCLASS.
CLASS CL1 IMPLEMENTATION.
METHOD M1.
ENDMETHOD.
METHOD M2.
ENDMETHOD.
METHOD M3.
ENDMETHOD.
ENDCLASS.
```
```
"Create object
DATA: ref_var TYPE REF TO cl_article_hierarchy.
START-OF-SELECTION.
CREATE OBJECT ref_var.
```
```
"Create constants
CONSTANTS: const1 TYPE C VALUE 'A'.
```
```
"Declaration of Method in a Local Class
CLASS c_team DEFINITION.
PUBLIC SECTION.
TYPES: biker_ref TYPE REF TO c_biker,
biker_ref_tab TYPE STANDARD TABLE OF biker_ref
WITH DEFAULT KEY,
BEGIN OF status_line_type,
flag(1) TYPE C,
text1(5) TYPE C,
id TYPE I,
text2(7) TYPE C,
text3(6) TYPE C,
gear TYPE I,
text4(7) TYPE C,
speed TYPE I,
END OF status_line_type.
CLASS-METHODS: class_constructor. "Static Attribute
METHODS: constructor,
create_team,
selection,
execution.
PRIVATE SECTION.
CLASS-DATA: team_members TYPE I,
counter TYPE I.
DATA: id TYPE I,
status_line TYPE status_line_type,
status_list TYPE SORTED TABLE OF status_line_type
WITH UNIQUE KEY id,
biker_tab TYPE biker_ref_tab,
biker_selection LIKE biker_tab,
biker LIKE LINE OF biker_tab.
METHODS: write_list.
ENDCLASS. "c_team DEFINITION
```
```
"Implementation of Methods in a Local Class
CLASS c_team IMPLEMENTATION.
METHOD class_constructor.
tit1 = 'Team members ?'.
CALL SELECTION-SCREEN 100 STARTING AT 5 3.
IF sy-subrc NE 0.
LEAVE PROGRAM.
ELSE.
team_members = members.
ENDIF.
ENDMETHOD. "class_constructor
METHOD constructor.
counter = counter + 1.
id = counter.
ENDMETHOD. "constructor
METHOD create_team.
DO team_members TIMES.
CREATE OBJECT biker
EXPORTING
team_id = id
members = team_members.
APPEND biker TO biker_tab.
CALL METHOD biker->status_line
IMPORTING
line = status_line.
APPEND status_line TO status_list.
ENDDO.
ENDMETHOD. "create_team
METHOD selection.
CLEAR biker_selection.
DO.
READ LINE sy-index.
IF sy-subrc <> 0. EXIT. ENDIF.
IF sy-lisel+0(1) = 'X'.
READ TABLE biker_tab INTO biker INDEX sy-index.
APPEND biker TO biker_selection.
ENDIF.
ENDDO.
CALL METHOD write_list.
ENDMETHOD. "selection
METHOD execution.
CHECK NOT biker_selection IS INITIAL.
LOOP AT biker_selection INTO biker.
CALL METHOD biker->select_action.
CALL METHOD biker->status_line
IMPORTING
line = status_line.
MODIFY TABLE status_list FROM status_line.
ENDLOOP.
CALL METHOD write_list.
ENDMETHOD. "execution
METHOD write_list.
SET TITLEBAR 'TIT'.
sy-lsind = 0.
SKIP TO LINE 1.
POSITION 1.
LOOP AT status_list INTO status_line.
WRITE: / status_line-flag AS CHECKBOX,
status_line-text1,
status_line-id,
status_line-text2,
status_line-text3,
status_line-gear,
status_line-text4,
status_line-speed.
ENDLOOP.
ENDMETHOD. "write_list
ENDCLASS. "c_team IMPLEMENTATION
```
```
"Calling Instance Methods
REPORT demo_class_counter .
*-----------------------------------------------------------*
* CLASS counter DEFINITION
*-----------------------------------------------------------*
*-----------------------------------------------------------*
CLASS counter DEFINITION.
PUBLIC SECTION.
METHODS: set IMPORTING value(set_value) TYPE I,
increment,
get EXPORTING value(get_value) TYPE I.
PRIVATE SECTION.
DATA count TYPE i.
ENDCLASS. "counter DEFINITION
*-----------------------------------------------------------*
* CLASS counter IMPLEMENTATION
*-----------------------------------------------------------*
*
*-----------------------------------------------------------*
CLASS counter IMPLEMENTATION.
METHOD set.
count = set_value.
ENDMETHOD. "set
METHOD increment.
ADD 1 TO count.
ENDMETHOD. "increment
METHOD get.
get_value = count.
ENDMETHOD. "get
ENDCLASS. "counter IMPLEMENTATION
DATA number TYPE I VALUE 5.
DATA cnt TYPE REF TO counter.
START-OF-SELECTION.
CREATE OBJECT cnt.
CALL METHOD cnt->set
EXPORTING
set_value = number.
DO 3 TIMES.
CALL METHOD cnt->increment.
ENDDO.
CALL METHOD cnt->get
IMPORTING
get_value = number.
WRITE number.
```
```
"Create ALV Grid
DATA:
gt_sflight TYPE TABLE OF sflight,
gs_layout TYPE lvc_s_layo,
gr_alv_grid TYPE REF TO cl_gui_alv_grid,
gr_custom_container TYPE REF TO cl_gui_custom_container.
IF gr_custom_container IS NOT BOUND.
* Create an instance of a container
CREATE OBJECT gr_custom_container
EXPORTING
container_name = 'ALV_CONTAINER_01'
EXCEPTIONS
cntl_error = 1
cntl_system_error = 2
create_error = 3
lifetime_error = 4
lifetime_dynpro_dynpro_link = 5
OTHERS = 6.
IF sy-subrc NE 0.
MESSAGE a001(z_message_class).
* Container could not be created, program terminated
ENDIF.
* Create an instance of alv control
CREATE OBJECT gr_alv_grid
EXPORTING
i_parent = gr_custom_container.
ENDIF.
gs_layout-grid_title = 'Flights'(100).
CALL METHOD gr_alv_grid->set_table_for_first_display
EXPORTING
i_structure_name = 'SFLIGHT'
is_layout = gs_layout
CHANGING
it_outtab = gt_sflight.
```
```
"Event Handler
METHOD onactiongoto_out_01 .
wd_this->fire_out_01_plg(
).
ENDMETHOD.
```
```
"Functional Method Usage
lv_calc_amt = lv_source_amt / lv_factor.
IF lv_amt NE lr_util->round_up( lv_calc_amt ).
lv_amt = lr_util->round_up( lv_calc_amt ).
ENDIF.
```
```
"Example of a Static Method Call
LOOP AT <table> ASSIGNING <wa>.
MOVE-CORRESPONDING <wa> TO <structure>.
zcl_utility=>create_csv_from_record(
EXPORTING
separator = gc_comma
quote_all_fields = 'F'
output_initial_values = 'X'
source_contents = <structure>
rcd_ref_descr = lr_struct_type
IMPORTING
csv_record = ls_output
EXCEPTIONS
invalid_structure_component = 1
unable_to_preserve_space = 2
OTHERS = 3
).
ASSERT sy-subrc = 0.
```
```
"Example of an Up Cast
DATA:
lv_name TYPE C LENGTH 30,
lr_person TYPE REF TO lcl_person,
lr_manager TYPE REF TO lcl_manager,
lr_employee TYPE REF TO lcl_employee.
CREATE OBJECT lr_manager.
lr_person = lr_manager. " Up cast
lv_name = lr_person->get_name( ).
```
```
"Declarations for Generic Handling
TYPES:
llt_person TYPE REF TO lcl_person,
ltt_person TYPE STANDARD TABLE OF llt_person.
DATA:
lv_salary TYPE betrg,
lv_name TYPE name1,
lr_person TYPE REF TO lcl_person,
lt_person TYPE ltt_person,
lr_manager TYPE REF TO lcl_manager,
lr_employee TYPE REF TO lcl_employee.
FIELD-SYMBOLS:
<person> TYPE REF TO lcl_person.
```
```
"Up Cast and Polymorphism Calls
APPEND INITIAL LINE TO lt_person ASSIGNING <person>.
<person> = lr_manager.
APPEND INITIAL LINE TO lt_person ASSIGNING <person>.
<person> = lr_employee.
LOOP AT lt_person ASSIGNING <person>.
lv_name = <person>->get_name( ).
lv_salary = <person>->get_salary( ).
WRITE: / lv_name, lv_bonus.
ENDLOOP.
```
```
"Down Cast
lr_manager ?= lr_person. "Down cast
```
```
"Object Reference to an Interface Component (set_fieldcatalog)
l_r_bi_query_ad->if_rsroa_bi_query~set_fieldcatalog(l_ts_fieldcatalog ).
```
```
"ALIAS for an Interface Component
ALIASES true FOR if_salv_c_bool_sap~true.
IF lv_state EQ true.
```
