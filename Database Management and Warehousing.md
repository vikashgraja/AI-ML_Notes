# Database Management and Warehousing

### ER-Model (Entity-Relationship Model)
- **Definition:** A conceptual framework used to describe the structure of a database.
- **Components:**
  - **Entities:** Objects or things in the real world (e.g., Student, Course).
  - **Attributes:** Properties of entities (e.g., StudentID, Name).
  - **Relationships:** Associations between entities (e.g., EnrollsIn).

### Relational Model
- **Definition:** A way to structure and query data using relations (tables).
- **Components:**
  - **Relations (Tables):** Consists of tuples (rows) and attributes (columns).
  - **Schema:** Defines the structure of a table (e.g., table name, column names, and data types).

**Relational Algebra:**
- **Operations:** Selection, projection, union, set difference, Cartesian product, and rename.
  ```sql
  SELECT column1, column2 FROM table WHERE condition;
  ```

**Tuple Calculus:**
- **Definition:** A non-procedural query language that uses logical formulas to describe the desired result.
- **Example:** `{t | t ∈ R ∧ P(t)}`, where `t` is a tuple, `R` is a relation, and `P(t)` is a predicate.

**SQL (Structured Query Language):**
- **Components:**
  - **DDL (Data Definition Language):** Defines the database schema.
    ```sql
    CREATE TABLE Students (StudentID INT, Name VARCHAR(50));
    ```
  - **DML (Data Manipulation Language):** Manages data within schema objects.
    ```sql
    INSERT INTO Students (StudentID, Name) VALUES (1, 'Alice');
    ```
  - **DCL (Data Control Language):** Controls access to data.
    ```sql
    GRANT SELECT ON Students TO user;
    ```
  - **TCL (Transaction Control Language):** Manages transactions in the database.
    ```sql
    COMMIT;
    ```

**Integrity Constraints:**
- **Definition:** Rules to ensure the accuracy and consistency of data.
  - **Types:** Primary key, foreign key, unique, not null, check.
  ```sql
  ALTER TABLE Students ADD CONSTRAINT PK_Student PRIMARY KEY (StudentID);
  ```

### Normal Form
- **Definition:** Guidelines to reduce redundancy and improve data integrity.
- **Forms:**
  - **1NF (First Normal Form):** No repeating groups.
  - **2NF (Second Normal Form):** 1NF + no partial dependency.
  - **3NF (Third Normal Form):** 2NF + no transitive dependency.
  - **BCNF (Boyce-Codd Normal Form):** A stricter version of 3NF.

### File Organization
- **Definition:** The way data is stored in a file.
- **Types:** Heap file, sorted file, hash file, clustered file.

### Indexing
- **Definition:** A data structure that improves the speed of data retrieval.
- **Types:** Primary index, secondary index, clustered index, non-clustered index.
  ```sql
  CREATE INDEX idx_name ON Students(Name);
  ```

### Data Types
- **Common Types:** INT, VARCHAR, DATE, BOOLEAN, FLOAT, etc.

### Data Transformation
**Normalization:**
- **Definition:** Process of organizing data to reduce redundancy.
  ```sql
  CREATE TABLE Orders (OrderID INT, OrderDate DATE);
  CREATE TABLE OrderItems (OrderItemID INT, OrderID INT, ProductID INT, Quantity INT);
  ```

**Discretization:**
- **Definition:** Process of converting continuous data into discrete buckets.
  ```python
  bins = pd.cut(df['Age'], bins=[0, 18, 35, 50, 65, 100], labels=['Child', 'Young Adult', 'Adult', 'Middle Age', 'Senior'])
  ```

**Sampling:**
- **Definition:** Selecting a subset of data for analysis.
  ```python
  sample = df.sample(n=100)
  ```

**Compression:**
- **Definition:** Reducing the size of data.
  - **Methods:** Lossless compression, lossy compression.

### Data Warehouse Modelling
**Schema for Multidimensional Data Models:**
- **Star Schema:** Central fact table connected to dimension tables.
- **Snowflake Schema:** Dimension tables normalized into multiple related tables.
- **Fact Constellation:** Multiple fact tables sharing dimension tables.

**Concept Hierarchies:**
- **Definition:** Organizes data in a hierarchical structure.
  - **Example:** Country → State → City.

**Measures: Categorization and Computations:**
- **Definition:** Quantitative data that can be analyzed.
- **Types:**
  - **Distributive:** Aggregation functions (e.g., SUM, COUNT).
  - **Algebraic:** Functions that can be computed using distributive measures (e.g., AVERAGE).
  - **Holistic:** Complex functions (e.g., MEDIAN).
