# Relational Database Normalization (1NF–3NF)

This project demonstrates the step-by-step logical design and normalization of a relational database system for a hotel booking domain. 

Starting from an unnormalized relation (**UNF**) containing multi-valued attributes and redundancy, the schema is decomposed systematically through **First Normal Form (1NF)**, **Second Normal Form (2NF)**, and **Third Normal Form (3NF)** to eliminate partial functional dependencies, transitive dependencies, and data modification anomalies.



## Normalization Step-by-Step 

| Stage | Rule Applied | Resolved Issues & Decompositions |
| :--- | :--- | :--- |
| **UNF $\to$ 1NF** | **Atomicity & Row Uniqueness** | Resolved multi-valued attributes in cells (`NUMER_POKOJU`, `KLIMATYZACJA`). Decomposed into `REZERWACJE` and `REZERWACJE_POKOJE` to enforce scalar values and define a composite primary key. |
| **1NF $\to$ 2NF** | **Full Functional Dependency** | Eliminated partial key dependencies where room features (`LOZKA_1OS`, `LOZKA_2OS`, `KLIMATYZACJA`, `PIETRO`) depended only on a subset of the composite key (`NUMER_POKOJU`). Isolated room attributes into a dedicated `POKOJE` table. |
| **2NF $\to$ 3NF** | **Transitive Dependency Removal** | Removed non-key dependencies across relations: <br>• Extracted customer details (`NAZWISKO` depending on `ID_KLIENTA`) into `KLIENCI`. <br>• Extracted room configurations (`LOZKA`, `KLIMATYZACJA` depending on `TYP_POKOJU`) into `TYPY_POKOI`. |


## Project Structure
*  SQL script - `skrypt.txt`
*  Documentation detailing the theoretical normalization steps - `normalizacja.pdf`
*  Step-by-step tabular data transformation - `normalizacja.xlsx`
*  Entity-Relationship Diagram - `diagram.png`

## Authors
* Magdalena Kieler
* Wioletta Sudoł
