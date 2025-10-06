# Oracle Database Assignment II - PDB Management & OEM Configuration

## Report Summary
This assignment covers creating a permanent PDB for my coursework, demonstrating PDB deletion, and setting up Oracle Enterprise Manager.

---

## Student Information
**Name:** Muhanguzi Boss  
**Student ID:** 27810  
**Course:** INSY 8311 - Database Development with PL/SQL  
**Instructor:** Eric Maniraguha  
**Submission Date:** October 6, 2025  

---

## Assignment Overview
This assignment demonstrates proficiency in Oracle 21c Multi-tenant Architecture by:

- Creating a permanent Pluggable Database (PDB) for coursework  
- Demonstrating PDB lifecycle management through creation and deletion  
- Configuring and accessing Oracle Enterprise Manager (OEM)
---

## Task 1: Main PDB Creation

### Objective
Create a permanent pluggable database for storing coursework.

**PDB Details:**

- **PDB Name:** mu_pdb_27810  
- **Admin User:** mu_pdb_27810  
- **Status:** READ WRITE (Auto-open enabled)

### Task 1 Evidence
- `01_database_connection.png` – Connected as SYSDBA  
- `02_pdb_creation.png` – PDB creation command and success  
- `03_pdb_open.png` – PDB opened and state saved  
- `04_show_pdbs.png` – Verification showing PDB in READ WRITE mode  

#### Database Connection
Connected as SYSDBA

#### PDB Creation
PDB creation command and success

#### PDB Open
PDB opened and state saved

#### Show PDBs
Verification showing PDB in READ WRITE mode

---

## Task 2: PDB Lifecycle Management

### Objective
Demonstrate PDB creation and deletion process.

**Temporary PDB Details:**

- **PDB Name:** to_delete_pdb_27810  
- **Lifecycle:** Created → Opened → Closed → Dropped with datafiles

### Task 2 Evidence
- `05_delete_pdb_creation.png` – Temporary PDB created  
- `06_pdb_deleted.png` – PDB permanently deleted and verified  

#### Temp PDB Created
Temporary PDB created

#### PDB Deleted
PDB permanently deleted and verified

---


## Key SQL Commands

### Task 1 - Main PDB
```sql
CREATE PLUGGABLE DATABASE MU_PDB_27810
  ADMIN USER mu_pdb_27810 IDENTIFIED BY 1234
  FILE_NAME_CONVERT = ('pdbseed', 'mu_pdb_27810');

ALTER PLUGGABLE DATABASE MU_PDB_27810 OPEN;
ALTER PLUGGABLE DATABASE MU_PDB_27810 SAVE STATE;
```
### Task 2 - Temporary PDB
```sql
CREATE PLUGGABLE DATABASE TO_DELETE_PDB_27810
  ADMIN USER to_delete_pdb_27810 IDENTIFIED BY YourSecurePassword
  FILE_NAME_CONVERT = ('pdbseed', 'to_delete_pdb_27810');

ALTER PLUGGABLE DATABASE TO_DELETE_PDB_27810 CLOSE IMMEDIATE;
DROP PLUGGABLE DATABASE TO_DELETE_PDB_27810 INCLUDING DATAFILES;
```




