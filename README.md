Oracle Pluggable Database (PDB) Management - Assignment II

Course GROUP: I
Student Name: IZERE DIVIN
Student ID: 28979


Overview

This repository contains the documentation and evidence for Individual Assignment II, which covers practical administration of Oracle's Multitenant Architecture. The assignment required creating a pluggable database with an associated user, creating and dropping a temporary pluggable database, configuring Oracle Enterprise Manager, and documenting the process in a professional and reproducible way.


Task 1: Create a New Pluggable Database

A new pluggable database named di_pdb_28979 was created from the root container using the CREATE PLUGGABLE DATABASE statement, with file locations mapped from the seed PDB through FILE_NAME_CONVERT. The database was opened using ALTER PLUGGABLE DATABASE OPEN, and the session was switched into it using ALTER SESSION SET CONTAINER. A dedicated user, divin_plsqlauca_28979, was then created inside this PDB for use in future coursework.

Commands used:

CREATE PLUGGABLE DATABASE di_pdb_28979
  ADMIN USER admin IDENTIFIED BY Auca123
  FILE_NAME_CONVERT = ('C:\app\divin\oradata\XE\pdbseed', 'C:\MY_PDB');

ALTER PLUGGABLE DATABASE di_pdb_28979 OPEN;

ALTER SESSION SET CONTAINER = di_pdb_28979;

CREATE USER divin_plsqlauca_28979 IDENTIFIED BY Auca123;


Task 2: Create and Delete a Pluggable Database

A temporary pluggable database named di_to_delete_pdb_28979 was created using the same method as Task 1. Its existence was verified, after which the session was returned to the root container and the database was permanently removed using DROP PLUGGABLE DATABASE INCLUDING DATAFILES. A final query confirmed the database no longer existed.

Commands used:

CREATE PLUGGABLE DATABASE di_to_delete_pdb_28979
  ADMIN USER admin IDENTIFIED BY Auca123
  FILE_NAME_CONVERT = ('C:\app\divin\oradata\XE\pdbseed', 'C:\New_PDB');

ALTER SESSION SET CONTAINER = CDB$ROOT;

DROP PLUGGABLE DATABASE di_to_delete_pdb_28979 INCLUDING DATAFILES;


Task 3: Oracle Enterprise Manager

Oracle Enterprise Manager was accessed and configured to reflect the current database environment. The dashboard was verified to show the completed pluggable database tasks along with the student username.


Task 4: Documentation and Reporting

This README, together with the accompanying screenshots, documents each step carried out during the assignment, in line with the required reporting standard.
