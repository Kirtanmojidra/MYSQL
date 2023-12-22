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
           )
    
### With ALTER
-     ALTER TABLE <Table_Name> ADD FOREa 1`IGN KEY (City) REFERENCES CITYNAME (Cid);

# TYPE OF JOIN
## INNER JOIN
## LEFT JOIN
## RIGHT JOIN
## CROSS JOIN
