**1. Degrees of Data Abstraction:** **Data abstraction** refers to the process of hiding complex implementation details from users and presenting them with a simplified, higher-level view of the data.  It's about managing complexity in database systems.
* **Degrees (Levels):**  The **Three-Schema Architecture**:

    * **a) Physical Level (Lowest Level):** Describes *how* the data is actually stored in the computer's physical storage (e.g., hard disks).
        * **Details:**  Focuses on storage structures, file organization (e.g., B-trees, hash indexes), data types in terms of bytes and blocks, record formats, data compression and encryption techniques, and physical storage locations.
        * **Abstraction Level:** Lowest level of abstraction. Very technical and concerned with efficiency and storage details.
        * **Example:** "Table `Customers` is stored as a heap file on disk block addresses 1000-2000.  The `CustomerID` is a 4-byte integer and indexed using a B+ tree."

    * **b) Logical Level (Conceptual/Internal Level):** Describes *what* data is stored in the database and the relationships between the data. It's concerned with the data structure and organization, but *not* the physical storage details.
        * **Details:**  Uses schemas to define tables, attributes, data types (like integer, string), relationships between tables (using foreign keys), constraints, and data integrity rules.  It's often represented using a Data Definition Language (DDL).
        * **Abstraction Level:**  Intermediate level. Hides the physical storage complexity but shows the overall structure.
        * **Example:** "The `Customers` table has attributes: `CustomerID` (integer, primary key), `Name` (varchar), `Address` (varchar), and `Order` table has `OrderID`, `CustomerID` (foreign key referencing Customers), `OrderDate`, `TotalAmount`."  This level doesn't say *how* these tables are stored physically.

    * **c) View Level (External Level) (Highest Level):** Provides different views of the database to different users or application programs. Each view shows only the data relevant to a particular user or application, hiding the rest of the database.
        * **Details:**  Views are defined using SQL queries that select and present specific data from the logical level.  They can simplify the database for users, provide security by limiting access to certain data, and customize the data presentation.
        * **Abstraction Level:** Highest level of abstraction.  Simplifies the database for individual users or applications.
        * **Example:** "A view called `CustomerOrdersView` might show only `CustomerID`, `Name` from `Customers` and `OrderID`, `OrderDate` from `Orders` for users in the Sales department. Another view for the Billing department might show different data."

**2. Differences between Software Independence and Hardware Independence**

* **Concept of Data Independence:** Data independence is the ability to modify the schema at one level *without* affecting the schema at the next higher level. This is a crucial goal in database design as it allows for flexibility and reduces the maintenance burden.

* **Software Independence (Logical Data Independence):** The capacity to change the **logical schema** (e.g., adding new attributes, changing relationships, reorganizing tables) *without* requiring changes to **application programs** that use the database.
    * **How it's achieved:** The logical level is separated from the external (view) level. Views act as a buffer.  If you change the underlying logical structure, as long as the views remain the same (or can be redefined to still provide the same data), applications using those views will continue to work without modification.
    * **Example:**  You decide to normalize your `Customers` table by splitting the `Address` attribute into `Street`, `City`, `State`, and `ZipCode`. This is a change at the logical level.  If application programs access customer data through views that are redefined to reflect this change (e.g., the view reconstructs the full address from the new attributes), the applications won't need to be rewritten.

* **Hardware Independence (Physical Data Independence):** The capacity to change the **physical schema** (e.g., changing storage structures, file organization, using different storage devices) *without* requiring changes to the **logical schema** (and therefore, without affecting application programs).
    * **How it's achieved:** The physical level is separated from the logical level.  The DBMS handles the mapping between the logical and physical levels.  You can change the way data is physically stored as long as the logical schema remains consistent.
    * **Example:** You decide to move the database from one type of hard drive to a faster, newer type, or you decide to implement data compression to save space. These are physical level changes.  As long as the logical schema (tables, attributes, relationships) remains the same, application programs that access the database through the logical schema will not be affected.

**Key Differences Summarized:**

| Feature           | Software Independence (Logical)        | Hardware Independence (Physical)       |
|-------------------|-----------------------------------------|------------------------------------------|
| **Level of Change** | Logical Schema Changes                 | Physical Schema Changes                  |
| **Impacted Level** | Application Programs (via External Views) | Logical Schema (and indirectly Applications) |
| **Type of Change**  | Structure of data, relationships        | Storage implementation, hardware         |
| **Goal**          | Flexibility in data organization        | Flexibility in storage and performance   |

**3. Briefly explain each of the following:**

**a) Conceptual Model:** (also often called an **Entity-Relationship Model or ER Model**) is a high-level, abstract representation of the data requirements of an organization or a system. It focuses on *what* data needs to be stored, the entities (things) in the system, and the relationships between these entities. It's independent of any specific database management system or physical implementation.
* **Purpose:**
    * Understand and document the data requirements from a business perspective.
    * Communicate data requirements to stakeholders (users, developers, managers).
    * Serve as a blueprint for the logical and physical database design.
* **Representation:** Often depicted using ER diagrams.
* **Key Components:** Entities, attributes, relationships, and constraints.
* **Example:**  For a university system, a conceptual model would identify entities like `Student`, `Course`, `Professor`, `Department`, and relationships like "Student *enrolls in* Course", "Professor *teaches* Course", "Department *offers* Course". It would also specify attributes for each entity (e.g., `Student` entity might have attributes: `StudentID`, `Name`, `Major`).

**b) External Model:** (or **view model**) represents a specific user's or application program's perspective of the database. It's a subset of the overall database that is relevant to a particular user or group of users. There can be multiple external models for a single database.
* **Purpose:**
    * Simplify the database for individual users by showing only relevant data.
    * Provide security by restricting access to sensitive data.
    * Customize data presentation and format for different applications.
* **Representation:** Defined using views in SQL.
* **Relationship to other levels:** Derived from the logical model.
* **Example:**  In a bank database, an external model for a teller might show only customer account details, transaction history, and deposit/withdrawal functionalities. An external model for a loan officer might show different data related to loan applications, credit scores, etc.

**c) Internal Model**:** (also known as the **logical model** or **implementation model**) is a representation of the database as seen by the DBMS. It describes *how* the data is logically structured and organized within the database system. It's concerned with the data structures and relationships, but it's still independent of the physical storage details.
* **Purpose:**
    * Translate the conceptual model into a format understandable by the chosen DBMS.
    * Define the data structures (tables, indexes), data types, relationships, and constraints that will be implemented in the database.
* **Representation:**  Often described using a schema in the data definition language (DDL) of a specific DBMS (e.g., SQL DDL).
* **Relationship to other levels:**  Derived from the conceptual model and serves as a basis for the physical model.
* **Example:**  The internal model for the university system might specify tables like `Students`, `Courses`, `Professors`, `Departments` with specific column data types (e.g., `StudentID` as INT, `Name` as VARCHAR), primary keys, foreign keys to enforce relationships, and constraints like "StudentID must be unique".

**d) Physical Model:** is the lowest level of abstraction. It describes *how* the data is physically stored on storage media. It deals with storage structures, file organization, indexing techniques, data allocation, and other physical storage details.
* **Purpose:**
    * Optimize storage efficiency and data access performance.
    * Specify physical implementation details that are specific to the hardware and operating system environment.
* **Representation:**  Often described using physical storage specifications, file organization methods (e.g., heap files, indexed files), indexing techniques (e.g., B-trees, hash indexes), and data compression methods.
* **Relationship to other levels:**  Derived from the internal model.
* **Example:**  The physical model for the `Students` table might specify that it's stored as a clustered index file on the `StudentID` attribute, using B+ tree indexing, with data pages of 4KB size, and stored on disk partition `/data/db/`.

**e) Attribute Domain:** defines the set of permissible values that an attribute can take. It specifies the data type, format, and any constraints on the attribute's values.
* **Purpose:**
    * Ensure data integrity by restricting attribute values to valid entries.
    * Define the range of possible values for an attribute.
* **Examples:**
    * For the attribute `Age`, the domain might be "positive integers between 0 and 120".
    * For the attribute `Gender`, the domain might be "the set {'Male', 'Female', 'Other'}".
    * For the attribute `Email`, the domain might be "strings that conform to the email address format and are no longer than 255 characters".
* **Importance:** Domains are crucial for data validation and maintaining data quality.

**f) Composite Identifier:** (or **composite key**) is a primary key that consists of *two or more attributes* combined together to uniquely identify each entity instance.  A single attribute alone is not sufficient to uniquely identify an entity.
* **When to use:** When no single attribute can uniquely identify entities, but a combination of attributes can.
* **Example:**
    * In a table `OrderItems`, you might have attributes `OrderID` and `ProductID`.  Neither `OrderID` nor `ProductID` alone uniquely identifies an item in the `OrderItems` table (because an order can have multiple items, and a product can be in multiple orders). However, the combination of `(OrderID, ProductID)` *will* uniquely identify each item within an order. So, `(OrderID, ProductID)` could be a composite identifier for `OrderItems`.

**g) Differentiate between Composite identifier and Composite attribute**

* **Composite Identifier (Key):**
    * **Purpose:**  Uniquely identifies entity instances.
    * **Composition:** Made up of *multiple attributes* that, together, act as a primary key.
    * **Function:**  Primarily for identification and indexing.
    * **Example:** `(OrderID, ProductID)` in `OrderItems`.

* **Composite Attribute:**
    * **Purpose:**  Represents a single, logical attribute that is further divided into *component attributes*. It describes a single characteristic but in a structured way.
    * **Composition:** Made up of *sub-attributes* that together form a larger attribute.
    * **Function:** For organizing and structuring attribute information; often for better data representation and querying.
    * **Example:** `Address` attribute could be composite, composed of sub-attributes like `Street`, `City`, `State`, `ZipCode`.  `Name` attribute could be composite, with `FirstName`, `LastName`, `MiddleName`.

**h) Simple attribute**:** (or **atomic attribute**) is an attribute that cannot be further subdivided or decomposed into smaller components. It's a single, indivisible piece of information.
* **Characteristics:**
    * Atomic – cannot be broken down.
    * Holds a single value for each entity instance.
* **Examples:** `Age`, `Salary`, `ProductID`, `Color`, `CustomerID`.  These are basic units of data.

**i) Derived attribute:** is an attribute whose value can be calculated or derived from the values of other attributes (either in the same entity or related entities).  Derived attributes are typically *not* stored in the database directly but are computed when needed.
* **Characteristics:**
    * Calculated from other attributes.
    * Not physically stored (usually, to avoid redundancy and maintain consistency).
    * Value can change when the attributes it's derived from change.
* **Examples:**
    * `Age` can be derived from `DateOfBirth`.
    * `TotalPrice` can be derived from `UnitPrice` and `Quantity`.
    * `EmployeeTenure` can be derived from `HireDate` and `CurrentDate`.
* **Advantages:**  Reduces data redundancy, ensures consistency (because it's always calculated based on the source data).
* **Disadvantages:**  Computation overhead when accessed (though often negligible).

**j) Cardinality:** specifies the *number* of instances of one entity that can be related to the number of instances of another entity. It defines the constraints on relationships.
* **Types of Cardinality:**
    * **One-to-One (1:1):**  One instance of entity A is related to at most one instance of entity B, and vice-versa. (Example: One person can have at most one passport, and one passport belongs to at most one person).
    * **One-to-Many (1:N) or Many-to-One (N:1):**  One instance of entity A can be related to *many* instances of entity B, but one instance of entity B is related to at most *one* instance of entity A. (Example: One customer can place *many* orders, but one order is placed by *only one* customer).
    * **Many-to-Many (M:N):**  Many instances of entity A can be related to *many* instances of entity B, and vice-versa. (Example: One student can enroll in *many* courses, and one course can be taken by *many* students).
* **Representation in ER Diagrams:** Often depicted using notations like 1, N, M, or symbols like crows feet near the relationship lines.

**k) Existence dependence:** is a situation where the existence of an entity instance *depends* on the existence of another entity instance.  This is a key characteristic of **weak entities**.
* **Relationship to Weak Entities:** Weak entities are *existence-dependent* on their **owner entity** (also called the identifying entity).  A weak entity cannot exist without being related to a specific instance of its owner entity.
* **Example:** Consider `Employee` and `Dependent`. A `Dependent` (like a child or spouse) typically *cannot exist in the database* if the associated `Employee` does not exist.  The existence of a `Dependent` is dependent on the existence of an `Employee`.  Here, `Dependent` would likely be a weak entity and `Employee` would be its owner entity.

**4. When is an entity referred to as being a strong entity?**

A **strong entity** (also called an **independent entity** or **regular entity**) is an entity that:
    * **Has its own primary key:** It possesses one or more attributes that uniquely identify each instance of the entity *without* relying on any other entity.
    * **Existence-independent:** Its existence is *not dependent* on the existence of any other entity. It can exist independently.
* **Characteristics:**
    * Possesses a primary key.
    * Can exist on its own.
    * Represented by a single rectangle in ER diagrams (typically).
* **Examples:** `Customer`, `Product`, `Employee`, `Department`, `Course`.  These entities can exist in the database regardless of whether other related entities exist. For instance, a `Department` can exist even if there are no `Employees` currently assigned to it.

**5. Weak Relationship**

A **weak relationship** is a relationship that connects a **weak entity** to its **owner entity**. It's the relationship through which the weak entity is *identified* and its existence is dependent.
* **Characteristics:**
    * Connects a weak entity to its owner entity.
    * Often called an **identifying relationship** because it helps to partially identify the weak entity instances (in combination with the owner entity's key).
    * Represented by a double line in ER diagrams (sometimes, depending on the notation).
* **Example:** The relationship between `Employee` and `Dependent` (where `Dependent` is weak and `Employee` is strong) is a weak relationship.  It might be named something like "HAS-DEPENDENT" or "COVERS".

**6. Strong Relationship**

A **strong relationship** is a relationship between two or more **strong entities**.  The entities involved in a strong relationship can exist independently of each other.
* **Characteristics:**
    * Connects strong entities.
    * Entities involved have their own primary keys and independent existence.
    * Represented by a single line in ER diagrams (typically).
* **Examples:**
    * The relationship "ENROLLS-IN" between `Student` and `Course` is a strong relationship (assuming both are strong entities).  A `Student` can exist even if they are not enrolled in any `Course`, and a `Course` can exist even if no `Students` are currently enrolled.
    * "WORKS-IN" relationship between `Employee` and `Department` (if both are strong entities).

**7. State 2 conditions that an entity must meet before it can be referred to as weak entity**

An entity must meet these two primary conditions to be considered a **weak entity**:

1. **Existence Dependence:** The entity's existence is dependent on another entity, called the **owner entity** or **identifying entity**.  A weak entity instance cannot exist if the related owner entity instance does not exist.

2. **Lack of its own Primary Key (in isolation):**  A weak entity does not have a primary key of its own in the context of the database schema *as a whole*.  Instead, it is typically identified *relative to* its owner entity. It often uses a combination of:
    * **Partial Key (Discriminator):** One or more attributes within the weak entity itself that can uniquely identify instances *within the context of a specific owner entity*.
    * **Primary Key of the Owner Entity:** The primary key of the owner entity is included as part of the weak entity's identifier.

   **In essence, the "primary key" of a weak entity is often a composite key formed by the primary key of its owner entity and its own partial key.**

**8. Entity degree:** refers to the *number of relationships* in which an entity participates. It's about how many relationships an entity is connected to in an ER diagram.

* **Types of Entity Degree (based on relationship count):**

    * **Unary Degree (Degree 1):**  The entity participates in *one* relationship. This is often a **recursive relationship**, where an entity is related to itself.
        * **Example:**  An `Employee` entity might have a "SUPERVISES" relationship with itself (one employee supervises another).

    * **Binary Degree (Degree 2):** The entity participates in *two* relationships.  This is the most common case where an entity is related to two other (possibly different) entities.
        * **Example:** A `Student` entity might participate in "ENROLLS-IN" (with `Course`) and "LIVES-IN" (with `Dormitory`).

    * **Ternary Degree (Degree 3):** The entity participates in *three* relationships.
        * **Example:**  Consider entities `Supplier`, `Part`, and `Project`. A ternary relationship might be "SUPPLIES" relating all three: `Supplier` supplies `Part` to `Project`.  The `Part` entity here has a ternary degree in this context.

    * **N-ary Degree (Degree N):**  The entity participates in *N* relationships (where N is any number).  While ternary is sometimes encountered, degrees higher than ternary are less common and can often be decomposed into binary relationships for simplicity in database design.

**Key Takeaway for Exams:** Understand that entity degree is about counting relationships connected to an entity. Know the basic types (unary, binary, ternary) and be able to identify them in ER diagrams.
