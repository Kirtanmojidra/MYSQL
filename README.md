 # MYSQL

## Create DataBase 
   -       CREATE DATABASE <Name_Of_DataBase>
## Create Table 
  -         CREATE TABLE <Name_OF_TABLE>(
             <name Of field> DataType(size),
             <name Of field> DataType(size),
             <name Of field> DataType(size),
            ...
            ...
            col_N 
         );
        
  
### String DataType
Name|Range
---|---
CHAR(size)|0 to 255
VARCHAR(size)|0 to 65535
BINARY(size)|0 - 255 store binary value of number
VARBINARY(size)| 0-65535 store binary value of number
TINYTEXT| max 255 char
TEXT(size)| 65535 bytes
MEDIUMTEXT| 1,67,77,215 char
LONGTEXT| 4,29,49,67,295 char
TINYBLOB| 255 bytes
BLOB(size)| 65535 bytes
MEDIUMBLOB| 1,67,77,215 bytes
LONGBLOB| 4,29,49,67,295 bytes
ENUM| value is must in give data ex: ENUM(val_1,val_2,val_3,.....) List up to 65535 values
SET| same as ENUM but List of value max 64 value

## Numeric DataType
NAME|RANGE
---|---
BIT(size)|1 to 64
TINYINT(size)| -128 to 127
INT(size)| -2,14,74,83,648 to 2,14,74,83,647
INTEGER(size)| Same as INT but Full name
SMALLINT(size)| -32,768 to 32,767
MEDIUMINT(size)| -83,88,608 to 83,88,607
BIGINT(size)| -92,23,37,20,36,85,47,75,808 to 92,23,37,20,36,85,47,75,807
BOOL or BOOLEAN| 0 or 1
FLOAT(p)| Deciaml Value
DOUBLE(size,d)| size number of Digit before point and d is number of digit after point
DECIMAL(size,d) or DEC(size,d)| size max 60 and d max 30

## DATE DataType
NAME|RANGE
---|---
DATA | 1000-01-01 to 9999-12-31 "YY-MM-DD"
DATETIME(fsp) | YY-MM-DD HH : MM : SS
TIMESTAMP(fsp) |  same as DATETIME mostly use for OLD dates
TIME(fsp) | HH : MM : SS
YEAR | any 4 DIGIT Year ex : 1999

## INSERT Row In to TABLE

-         INSERT INTO <Table Name>(Field_1,Field_2,Field_3 )
          VALUE(val_1,val_2,val_3)
## INSERT Multiple Row in Table
-         INSERT INTO <Table_NAME>(Field_1,Field_2,Field_3)
            VALUES(val_1,val_2,val_3)
            ,(val_1,val_2,val_3)
            ,(val_1,val_2,val_3),.....;

      
## UPDATE
-      UPDATE <Table_Name> SET <Field_Name>,<Field_Name>,... WHERE <Condition>


## DELETE 
-      DELETE FROM <Table_Name> WHERE <Condition>;


## ALTER
-     Add New Field or Column in a Table
-     ALTER TABLE <Table_Name> ADD <Field_name> DataType;
-     Changing Data Type Of a Column
-     ALTER TABLE <Table_Name> MODIFY <Field_Name> DataType;
-     Change Column Name
-     ALTER TABLE <Table_Name> CHANGE <Field_Name> <New_Name> dataType;
-     Add Keys and Constraints to a Column
-     Changing Column Position
-     Delete Column
-     ALTER TABLE <Table_Name> DROP COLUMN <Field_Name>;
-     Renaming Tables
-     ALTER TABLE <Table_Name> RENAME <New_Table_Name>

## Constraints
   Use with Fields 
   NAME | USAGE
   ---|---
   NOT NULL| Feild Must Have a Value NOT Empty
   UNIQUE| Feild Have Unique value
   DEFUALT| Set Default Value ex:DEFUALT(Value) if we provide any value then it overwrite
   CHECK| Make Conditions on Value at Insert ex:CHECK(age >= 18)
-         CREATE TABLE exmple(
            id INT(20) UNIQUE,
            name VARCHAR(255) NOT NULL,
            age INT(100) CHECK(age >= 18) 
         );

## SELECT and WHERE In MYSQL
### SELECT Every Field
   -         SELECT * FROM <Table_Name>;
              SELECT * FROM <Table_Name> WHERE <Condition>;
### SELECT Specific Fields
   -          SELECT Feild_1,Feild_2,.... FROM <Table_Name> WHERE <Condition>;
     

### AND , OR , NOT 
-         SELECT * FROM <Table_Name> WHERE <Condition>  AND <Condition>;
-         SELECT * FROM <Table_Name> WHERE  <Conditon> OR <Condition>;
-         SELECT * FROM <Table_Name> WHERE <Condition> NOT <Condition>;
  
## IN
   - Used as Check is in value
   -          SELECT * FROM <Table_Name> WHERE <Field Name> IN(val_1,val_2,.....);
   -      EX : SELECT * FROM example WHERE age IN(10,20,40,18);
   -     Return Value when age Field contain above 10,20,40,18


##  BETWEEN
   Used as Check in Range Like Between 18 and 40 
   So this will make range 18 to 40
   -       SELECT * FROM <Table_name> WHERE <Field_Name> BETWEEN val_1 AND val_2;

## LIKE
      - SELECT * FROM <Table_Name> WHERE <Field_Name> LIKE "Expression"
Expression| Usage
---|---
'a%'|Start With 'a'
'%a'|End With 'a'
'%am%'| Have 'am' in any position
'a%m'|Start with 'a' and end with 'm'
'_a%'|'a' in the Second Position
'__a%'| 'a' in Third Position
'_oy'|'o' in the second and 'y' in the third position

## Reguler Expression
      - SELECT * FROM <Table_Name> WHERE <Field Name> REGEXP <Expression> 
Expression | Example | Usage 
|---|---|---
^ | '^ra' | Beginning of String
$ | 'an$' | End Of String
[...] | '[rms]' | Any Character listed between the square bracket
^[....]|'^[rms]' | Beginning With Any Character Listed Between the Square Brackets
[a-z]|'[a-h]e' | Match With in The Range

- p1|p2|p3| >  'p1|p2|p3'  >| Matches Any Of The Patterns p1,p2,p3 (use '|' between two or more expression)


## ORDER BY 
      -    Get the Data with in Order Form Ascending or descending
      -    ASC : By Defualt  Ascending Order
      -    DESC : Descending Order
      -    SELECT * FROM <Table_Name> WHERE  OREDER BY <Field_NameS> ASC|DESC
## DISTINCT
      - Get The Only Unique Data
      - SELECT DISTINCT <Field_Name> FROM <Table_Name>

## IS NULL or NOT NULL
      -    Give Null Data in table
      -  * WHERE <Field_Name> IS NULL
      
      - NOT NULL return only data that are not null
## LIMIT and OFFSET
      -   SET Limit of OutPut
      -    WHERE <condition> LIMIT <Any Number>

      -  Starting Point Of OutPut
      -   WHERE <Condition> LIMIT <OFFSET>,<LIMIT>


## Aggregate Functions
      -   SELECT <Function> FROM <Table_Name>

      
Function List | Usage
---|---
COUNT(<Field_Name>)| Total Number Of data in that Field
MAX(<Field_Name>)| Give The Max Value Of that Field
MIN(<Field_Name>)| Give The MIN value Of that Field
SUM(<Fied_Name>) | Give the Total of all value of that Field

## ROLLBACK  & COMMIT
-       RollBack : To Undo ALL Previous Query (Work on  INSERT , UPDATE , DELETE)
-       COMMIT : Is use To Store Privous all Query So That Can not RollBack
-       Syntax : ROLLBACK; , COMMIT;

# __Primary Key and Foreign Key
## Primary Key
-       Primary Key always have Unique Value
-       Cannot Be NULL
-       Only One Primary Key Allow in One Table
### At The Time Of Tabel Create
-       CREATE TABLE <Table_Name>(
         UUID INT(20),
          Name VARCHAR(30),
          Age INT(100),
          City VARCHAR(100),
          PRIMARY KEY UUID <- (Field To assing Primary Key),
           )
### With ALTER 
-       ALTER TABLE <Table_Name> ADD PRIMARY KEY (UUID) <- (<Field To Assign Primary Key>);

# FOREIGN KEY 
-     Mostly Used To Connect Tables Together
### At the Time Of Table Creation
-       CREATE TABLE <Table_Name>(
         UUID INT(20),
          Name VARCHAR(30),
          Age INT(100),
          City VARCHAR(100) NOT NULL,
          PRIMARY KEY UUID <- (Field To assing Primary Key),
          FOREIGN KEY(City) REFERENCES CITYNAME <- <Table_Name Of References> (Cid) <- (Field Of References Table)
           );
    
### With ALTER
-     ALTER TABLE <Table_Name> ADD FOREa 1`IGN KEY (City) REFERENCES CITYNAME (Cid);

# TYPE OF JOIN Used With FOREIGN KEY
## INNER JOIN
-      Return Comman data Of Different Tables
-      INNER JOIN Is Default So We Can Remove 'INNER' In Below Query 
-      SELECT * FROM <Table_Name> INNER JOIN <Table2_Name>
       ON <Table_name>.<Field_Name> = <Table2_Name>.<Field_Name>;

## LEFT JOIN AND RIGHT JOIN
-      LEFT > Only Return Data of Table 1
-      RIGHT > Only Return Data Of Table 2
-      Just Replace The 'LEFT' To 'RIGHT' For Right Join
-      SELECT * FROM <Table1_Name>  LEFT JOIN <Table2_Name> ON <Table1_Name>.<Field_Name> = <Table2_Name>.<Field_Name>;
## CROSS JOIN
-     Make A Combination of one Row of table one to all Rows Of Second Table
-     Ex : IF Table one contain 5 rows and Second table
      Contain 3 Rows Then Total of All Output will Be 5*3 = 15
-     SELECT * FROM <Table1_Name> CROSS JOIN <Table2_Name>;

## JOIN Multiple Table
-     Combine Multiple Table using multiple JOIN Statement
-     SELECT * FROM <Table1>
       INNER JOIN <Table2> ON <Table1>.<Field_Name> = <Table2>.<Field_Name>
       INNER JOIN <Table3> ON <Table1>.<Field_Name> = <Table3>.<Field_Name>

## GROUP BY 
-     GROUP BY is used in conjunction with SELECT and Aggregate Fun. to Group rows together by common colummn value
-     SELECT * FROM <Table1> WHERE Condition GROUP BY <Field NameS>;

## GROUP BY  with HAVING
-      used TO Check Condition On Group By
-      SELECT * FROM <Table_Name> GROUP BY <Field_NameS> HAVING Condition;

# Sub Query Or Nasted Query
-     SELECT * FROM <Table_Name> WHERE = (SELECT * FROM <Table_Name> WHERE Conditon)

## EXISTS and NOT EXISTS
-     EXISTS : if any one recode is found then it will run parent Command or Quety
-     NOT EXISTS : if no recode is found then it will run parent Command or Query
-     SELECT <Field_NameS> FROM <Table_Name> WHERE EXISTS (SELECT * FROM <Table> and Conditions>)

## UNION and UNION ALL
-     UNION ALL : Give Combine all Give Table into one table with Duplicate Recodes
-     UNION : With No Duplicate
-     Conditions : Each Table Should Have Same Number Of <Fields>
                   All Field have Same Data Types
                    ORDER of Table Field also be same
  
# IF 
-     To make condition as if
-     SELECT * IF (Condition, TRUE Result , FALSE Result) AS <Name for new Field >
       FROM <Table_Name>;
       
# CASE
-      Multiple Conditions with CASE
-      SELECT * CASE
                WHEN Condition THEN Result1
                WHEN Condition2 THEN Result2
                WHEN Condition3 THEN Result3
                .......
                ELSE result <Name Of new Fields>
       END Result Or  <name of new Field>
       FROM <Table_Name>;

## Arithmetic Functions 
-     We Can also usage -,+,/,*,%,etc 
Functions | Usage
---|---
ABS()| Absolute Value
PI()| give 3.141593
ROUND()| Rounded Value >EX: ROUND(4.3)=4;   > ROUND(4.8)=5;
CEIL()| Give Larger of given Point Number EX: >CEIL(4.3)= 5;    >CEIL(4.8)=5;
FLOOR()| Give Smaller of given point number Ex:  >FlOOR(4.9) = 4; >FLOOR(4.3) = 4;
SQRT()| Square Root 
POW(base,Exp)| base is number Exp is Exponent
RAND()| Give Random Number
SIGN()| Give sign of Number like number is -ne or +po  if Number is greather then 0 then return 1  , if number is 0 then 0 , if number is less then 0 then -1 


#  [String Functions](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html)
#  [Date Functions](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)


