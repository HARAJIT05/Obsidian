## Module 2: Relational Model Concepts

### 1. [[Relational Database Integrity]]
Relational database integrity ensures that data is accurate and consistent. It is a set of rules that constrains the data values that can be inserted, updated, or deleted in a database, thereby maintaining the overall validity of the data.

### 2. [[Types of Database Integrity]]
The four main types of database integrity are:
- **[[Domain Integrity]]**: Ensures that all values in a column are from a predefined domain of valid values.
- **[[Entity Integrity]]**: Guarantees that every table has a primary key, and that the primary key value is not null.
- **[[Referential Integrity]]**: Maintains consistency between related tables using foreign keys, preventing orphaned records.
- **[[User-defined Integrity]]**: Enforces business rules that are specific to the application and not covered by the other integrity types.

### 3. [[Domain Integrity]]
Domain integrity ensures all values in a column are from a predefined set of valid values. For example, in a 'Gender' column, the domain might be restricted to 'Male', 'Female', or 'Other', preventing invalid entries.

### 4. [[Entity Integrity]]
Entity integrity, enforced by the primary key, ensures that each row in a table is uniquely identifiable. It prohibits null values in the primary key column, guaranteeing that no record is without a unique identifier, which is crucial for data retrieval.

### 5. [[Referential Integrity]]
Referential integrity preserves the relationship between tables when they are linked using foreign keys. It ensures that a foreign key value in one table always refers to a valid, existing primary key in another table, preventing inconsistencies.

### 6. [[User-defined Integrity]]
User-defined integrity allows for the enforcement of specific business rules that do not fall into the other integrity categories. For example, a rule could be that an employee's salary cannot exceed that of their manager.

### 7. [[Keys in a Database]]
Keys are fundamental in a database for uniquely identifying records and establishing relationships between tables. They are a set of one or more attributes that can uniquely identify a tuple (row) in a relation (table).

### 8. [[Key Types]]
- **[[Primary Key]]**: A unique identifier for each record in a table. It cannot have null values.
- **[[Candidate Key]]**: An attribute or set of attributes that can uniquely identify a tuple. A table can have multiple candidate keys.
- **[[Super Key]]**: A set of attributes that can uniquely identify a tuple. A superkey may have additional attributes that are not necessary for unique identification.
- **[[Alternate Key]]**: A candidate key that is not selected as the primary key.
- **[[Foreign Key]]**: A key used to link two tables together. It is a field (or collection of fields) in one table that refers to the Primary Key in another table.

### 9. [[Data Redundancy]]
Data redundancy is the repetition of the same data in multiple places within a database. While it can sometimes be used to improve performance, uncontrolled redundancy leads to several problems, including data inconsistency and increased storage costs.

### 10. [[Problems with Redundancy]]
- **[[Insertion Anomaly]]**: Occurs when certain attributes cannot be inserted into the database without the presence of other attributes. For example, you cannot add a new course unless you also add a student to it.
- **[[Update Anomaly]]**: Results from data redundancy. If a piece of data is stored in multiple places, any update to it must be made in all of its locations. Failure to do so results in data inconsistency.
- **[[Deletion Anomaly]]**: Happens when the deletion of a set of data inadvertently causes the loss of other, unrelated data. For example, deleting a student might also delete the only record of a particular course.

### 11. [[Dependencies]]
- **[[Single-valued Dependency]]**: A single-valued dependency occurs when an attribute's value is determined by another attribute's value. For example, if 'Student ID' determines 'Student Name', then 'Student Name' has a single-valued dependency on 'Student ID'.
- **[[Multi-valued Functional Dependency]]**: A multi-valued functional dependency exists when an attribute's value can determine a set of values for another attribute. For example, a 'Professor' can teach multiple 'Courses', so 'Courses' has a multi-valued dependency on 'Professor'.

### 12. [[Normalization]]
Normalization is the process of organizing the columns and tables of a relational database to minimize data redundancy. Its main objectives are to reduce redundant data, improve data integrity, and avoid the anomalies (insertion, update, deletion).

### 13. [[Normalization Forms]]
- **[[First Normal Form (1NF)]]**: The rule for 1NF is that the domain of each attribute must contain only atomic (indivisible) values, and the value of each attribute must contain only a single value from that domain.
- **[[Second Normal Form (2NF)]]**: For a table to be in 2NF, it must first be in 1NF. Additionally, all non-key attributes must be fully functionally dependent on the primary key. This eliminates partial dependencies.
- **[[Third Normal Form (3NF)]]**: A table is in 3NF if it is in 2NF and no non-key attribute is transitively dependent on the primary key. This means that all attributes depend only on the primary key, not on other non-key attributes.
- **[[Boyce-Codd Normal Form (BCNF)]]**: BCNF is a stricter version of 3NF. A table is in BCNF if, for every non-trivial functional dependency X -> Y, X is a superkey. This handles certain anomalies not addressed by 3NF.
- **[[Fourth Normal Form (4NF)]]**: 4NF is designed to eliminate non-trivial multi-valued dependencies. A table is in 4NF if it is in BCNF and has no multi-valued dependencies, thus reducing redundancy in N-ary relationships.

### 14. [[Decomposition Properties]]
- **[[Attribute Preservation]]**: In database decomposition, attribute preservation ensures that all attributes from the original table are included in the decomposed tables. This means no information is lost during the normalization process.
- **[[Lossless Join Decomposition]]**: A lossless join decomposition is a decomposition of a table into multiple tables such that when the new tables are joined back together, the result is identical to the original table. This is crucial to ensure data is not lost.
- **[[Dependency Preservation]]**: Dependency preservation ensures that all the original functional dependencies of a table are still enforceable after decomposition. This is important for maintaining data integrity and efficiency without needing to join tables to check dependencies.
