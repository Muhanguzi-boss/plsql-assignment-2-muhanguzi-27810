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
screenshot
<img width="834" height="349" alt="image" src="https://github.com/user-attachments/assets/8770bf43-f79b-4c51-9328-99472f9f98be" />

- 
- `02_pdb_creation.png` – PDB creation command and success
Screenshot
<img width="840" height="499" alt="image" src="https://github.com/user-attachments/assets/755a53f3-58ac-4414-af36-03b5c1219e89" />

- 
- `03_pdb_open.png` – PDB opened and state saved
Screenshot
<img width="904" height="276" alt="image" src="https://github.com/user-attachments/assets/453a0f99-26eb-45cb-bb3b-279aad160760" />

- 
- `04_show_pdbs.png` – Verification showing PDB in READ WRITE mode
Screenshot
<img width="1001" height="638" alt="image" src="https://github.com/user-attachments/assets/1beb4464-09c7-4e80-a713-2387c687c7a3" />

- 

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




