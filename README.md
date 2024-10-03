Task1: this query was for creating the pluggable database plsql_class2024db with the user je_plsqlauca to access that pluggable database.

CREATE PLUGGABLE DATABASE plsql_class2024db
ADMIN USER je_plsqlauca IDENTIFIED BY Lukatoni123
 FILE_NAME_CONVERT = ('E:\ORACLE\ORADATA\ORCL21\pdbseed\', 'E:\ORACLE\ORADATA\ORCL21\plsql_class2024db\')

 Task2: this as the same as the task 1  for creating a pluggable database
  CREATE PLUGGABLE DATABASE je_to_delete_pdb
  2  ADMIN USER je_plsqlauca IDENTIFIED BY Lukatoni123
  3  FILE_NAME_CONVERT = ('E:\ORACLE\ORADATA\ORCL21\', 'E:\ORACLE\ORADATA\ORCL21\plsql_class2024db\');

 -- to delete a PDB you have to closing , i used this query:
 ALTER PLUGGABLE DATABASE JE_TO_DELETE_PDB CLOSE IMMEDIATE;

 -- and then after i unplug it
ALTER PLUGGABLE DATABASE JE_TO_DELETE_PDB UNPLUG INTO 'E:\oracle\app\HP\homes\OraDB21Home1\rdbms\log\JE_TO_DELETE_PDB.XML';

and drop the PDB For deleting
DROP PLUGGABLE DATABASE JE_TO_DELETE_PDB INCLUDING DATAFILES;
