#  The Real Estate Office Database Project

This project is a simple SQL-based database system built to manage the operations of a real estate office. It includes structured tables and relationships to store and organize information about branches, flats, managers, and workers.

---

##  Project Structure

The project consists of four main tables:

### 1. Branches Table
Stores data about the real estate office branches.

| Column        | Description                 |
|---------------|-----------------------------|
| `B_ID`        | Branch ID (Primary Key)     |
| `B_Name`      | Branch Name                 |
| `Government`  | Governorate name            |
| `City`        | City name                   |
| `M_ID`        | Manager ID (Foreign Key)    |
| `Manger_Name` | Name of the branch manager  |

---

### 2. Flats Table
Contains information about the flats available for sale.

| Column      | Description                  |
|-------------|------------------------------|
| `f_ID`      | Flat ID (Primary Key)        |
| `Block_ID`  | Block number                 |
| `Address`   | Flat address                 |
| `Floor`     | Floor number                 |
| `Area`      | Area/governorate             |
| `Price`     | Price of the flat            |
| `B_ID`      | Branch ID (Foreign Key)      |

---

### 3. Managers Table
Contains personal and job data about each manager.

| Column        | Description                  |
|---------------|------------------------------|
| `M_ID`        | Manager ID (Primary Key)     |
| `Manger_Name` | Manager full name            |
| `Address`     | Manager address              |
| `Salary`      | Monthly salary               |
| `B_ID`        | Branch ID (Foreign Key)      |

---

### 4. Workers Table
Stores information about workers in all branches.

| Column        | Description                  |
|---------------|------------------------------|
| `ID`          | Worker ID (Primary Key)      |
| `B_ID`        | Branch ID (Foreign Key)      |
| `FName`       | First Name                   |
| `LName`       | Last Name                    |
| `Address`     | Address                      |
| `Salary`      | Salary                       |
| `M_ID`        | Manager ID (Foreign Key)     |
| `Manger_Name` | Manager’s name               |

---

##  Relationships

All tables are related using foreign keys to maintain relational integrity:
- Branches are linked to managers.
- Flats are linked to branches.
- Workers are linked to both branches and their managers.

All required `PRIMARY KEY` and `INDEXES` were added using SQL `ALTER TABLE` statements.

---

##  Example Queries

Here are some example SQL queries used in the project:

- **Select flats cheaper than 150,000:**
  ```sql
  SELECT * FROM flats WHERE Price < 150000;
