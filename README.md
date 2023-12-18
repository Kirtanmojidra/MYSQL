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

## INSERT Data IN to TABLE

-         INSERT INTO <Table Name>(Field_1,Field_2,Field_3 )
          VALUE(val_1,val_2,val_3)






