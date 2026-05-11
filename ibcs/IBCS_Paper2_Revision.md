# IB Computer Science SL — Paper 2 Revision
### All Options: A · B · C · D

---

> **How to use this file:** Every sub-topic follows the same three-part structure:
> **Gist** → big idea | **Key line-items** → facts to know cold | **Examples** → exam-style illustrations.
> A Quick Reference section (command terms · formulas · glossary) closes the file.

---

# OPTION A: DATABASES

*Core idea: How data is stored, structured, and queried.*

---

## A1 — Database Concepts

### A1.1 Data vs Information

**Gist:** Data is raw, unprocessed facts with no context; information is data that has been processed, organised, or given meaning so that it is useful to a decision-maker. The distinction matters in databases because a database stores data, but the queries and reports it produces deliver information.

**Key line-items:**
- **Data** — raw facts, figures, or symbols (e.g., `42`, `"Smith"`, `2024-03-15`)
- **Information** — data processed into a meaningful, contextual form (e.g., "Smith's order placed on 15 March 2024 totals £42")
- Processing steps: collecting → organising → structuring → presenting
- Quality of information depends on: accuracy, completeness, timeliness, relevance
- **Metadata** — data about data (e.g., field names, data types, creation date of a record)

**Examples:**
- `85` is data; "Amit scored 85% in Paper 2" is information.
- A temperature sensor outputs `23.4` (data); a weather app shows "Currently 23°C, feels warm" (information).
- Exam question style: *"Distinguish between data and information, using an example from a student database."*

---

### A1.2 Flat-file vs Relational Databases

**Gist:** A flat-file database stores everything in a single table (like a spreadsheet), leading to data redundancy and update anomalies. A relational database splits data into multiple linked tables, eliminating redundancy and making maintenance far more efficient. Understanding why flat-files fail motivates the entire design of relational systems.

**Key line-items:**
- **Flat-file database** — single table; all data in one place
  - Advantages: simple, easy to create, no specialist software needed
  - Disadvantages: data redundancy (same data repeated), update anomalies, insertion anomalies, deletion anomalies
- **Relational database** — multiple tables linked by keys
  - Advantages: no/minimal redundancy, easier updates, data integrity, supports complex queries
  - Disadvantages: more complex to design, requires DBMS software
- **DBMS (Database Management System)** — software layer managing storage, access, and security (e.g., MySQL, PostgreSQL, Oracle)
- **Redundancy** — the same piece of data stored in more than one place
- **Anomalies (from redundancy):**
  - *Update anomaly* — changing a value in one row but forgetting others
  - *Insertion anomaly* — cannot add data without unrelated mandatory fields
  - *Deletion anomaly* — deleting one row loses unrelated data

**Examples:**
- Flat-file Orders table: every row repeats the customer's name and address → if the address changes, dozens of rows need updating (update anomaly).
- Relational fix: `Customers` table + `Orders` table linked by `CustomerID` — address stored once.
- Exam question style: *"Explain one disadvantage of using a flat-file database to store this data."*

---

## A2 — Relational Databases

### A2.1 Tables, Records, Fields

**Gist:** The foundational vocabulary of a relational database. A table (relation) holds data about one entity type; each row (record/tuple) is one instance; each column (field/attribute) is one characteristic. Knowing this vocabulary precisely is essential for describing and designing schemas in exams.

**Key line-items:**
- **Table (relation)** — a 2D structure holding data about one entity; has rows and columns
- **Record (row / tuple)** — one instance/entry in a table (e.g., one student)
- **Field (column / attribute)** — one characteristic of the entity (e.g., StudentName)
- **Domain** — the set of permitted values for a field (e.g., integer, date, text up to 50 chars)
- **Degree** — number of fields (columns) in a table
- **Cardinality** — number of records (rows) in a table
- **Null** — a field value that is absent or unknown (not the same as zero or empty string)

**Examples:**
- Table `Students(StudentID, Name, DateOfBirth, Grade)` has degree 4.
- One row `(1001, "Ana", "2007-04-10", 11)` is one record.
- Exam question style: *"Using the table above, state the number of records and fields."*

---

### A2.2 Primary Keys & Foreign Keys

**Gist:** Keys are the mechanism that makes a relational database relational. A primary key uniquely identifies each record in its own table; a foreign key in one table references the primary key of another, creating the link between tables. Without keys, joins are impossible and data integrity cannot be enforced.

**Key line-items:**
- **Primary key (PK)** — field (or combination of fields) that uniquely identifies every record; must be unique and NOT NULL
- **Composite primary key** — PK made of two or more fields (used in junction/linking tables)
- **Foreign key (FK)** — field in one table that references the PK of another table
- **Referential integrity** — rule that a FK value must either match an existing PK value or be NULL
- **Candidate key** — any field that could serve as a PK (unique + not null)
- **Natural key** — a real-world identifier used as PK (e.g., ISBN, NI number)
- **Surrogate key** — an artificial PK with no real-world meaning (e.g., auto-increment ID)

**Examples:**
- `Students(StudentID [PK], Name, Grade)` — StudentID is the PK.
- `Enrolments(StudentID [FK], CourseID [FK], EnrolDate)` — composite PK = (StudentID, CourseID).
- Deleting a student whose StudentID appears in `Enrolments` would violate referential integrity.
- Exam question style: *"Identify the primary key and foreign key(s) in the schema shown."*

---

### A2.3 Relationships: 1–1, 1–Many, Many–Many

**Gist:** Relationships describe how records in one table are associated with records in another. Understanding cardinality is critical for both ER modelling and correct schema design — a many-to-many relationship always requires a junction table to be implemented in a relational database.

**Key line-items:**
- **One-to-one (1:1)** — one record in Table A links to exactly one record in Table B
  - Rare; used to split a table for security or performance
  - Example: `Person` ↔ `Passport`
- **One-to-many (1:N)** — one record in A links to many records in B; most common relationship
  - FK goes in the "many" side
  - Example: `Customer` (1) → `Orders` (many)
- **Many-to-many (M:N)** — many records in A link to many records in B
  - Cannot be directly implemented; requires a **junction/linking table** with two FKs
  - Example: `Students` ↔ `Courses` via `Enrolments(StudentID, CourseID)`
- In an ER diagram: crow's-foot or min-max notation indicates cardinality

**Examples:**
- Library system: `Member` (1) → `Loans` (many) → `Book` (many-to-one back); Members and Books are M:N, resolved by `Loans` junction table.
- School: one `Teacher` teaches many `Classes`; each `Class` has one teacher → 1:N.
- Exam question style: *"Describe the relationship between Students and Courses. Explain how this relationship is implemented in a relational database."*

---

## A3 — Database Design

### A3.1 Entity-Relationship (ER) Models

**Gist:** An ER diagram is the blueprint for a relational database. It shows entities (things to store data about), their attributes, and the relationships between them, including cardinality. Drawing or interpreting ER diagrams is a core exam skill.

**Key line-items:**
- **Entity** — a distinct "thing" about which data is stored; becomes a table
- **Attribute** — a property of an entity; becomes a field
- **Relationship** — an association between entities; shown as a labelled line
- **ER notation symbols:**
  - Rectangle = entity
  - Ellipse = attribute
  - Diamond = relationship
  - Line annotations = cardinality (1, N, M, or crow's-foot)
- Steps to draw ER diagram: identify entities → identify attributes → identify relationships → determine cardinality → resolve M:N
- An entity's PK is typically underlined in the diagram

**Examples:**
- Hospital ER: `Patient` — has-many — `Appointment` — involves — `Doctor`; `Patient` ↔ `Doctor` is M:N, resolved by `Appointment`.
- Exam question style: *"Draw an ER diagram for a booking system with Customers, Rooms, and Bookings."*

---

### A3.2 Normalization (1NF, 2NF, 3NF)

**Gist:** Normalization is a systematic process of restructuring a database to reduce redundancy and improve data integrity. Each normal form removes a specific type of dependency. The IB expects you to recognise violations and know how to fix them up to 3NF.

**Key line-items:**
- **First Normal Form (1NF):**
  - Every cell contains one and only one atomic value (no lists/arrays in a cell)
  - Each column has a unique name
  - Order of rows does not matter
  - Fix: split multi-valued cells into separate rows or separate tables
- **Second Normal Form (2NF):**
  - Must already be in 1NF
  - No **partial dependency** — every non-key attribute must depend on the *whole* primary key (relevant only when PK is composite)
  - Fix: move partially dependent attributes to a separate table
- **Third Normal Form (3NF):**
  - Must already be in 2NF
  - No **transitive dependency** — no non-key attribute depends on another non-key attribute
  - Fix: move transitively dependent attributes to a separate table
- **Functional dependency** — A → B means "knowing A determines B"
- Fully normalised schema = less redundancy, fewer anomalies, easier maintenance

**Examples:**
- 1NF violation: `PhoneNumbers = "07123, 07456"` → split into separate rows.
- 2NF violation: `OrderDetails(OrderID, ProductID, ProductName, Qty)` — `ProductName` depends only on `ProductID` (partial) → move to `Products` table.
- 3NF violation: `Employee(EmpID, DeptID, DeptName)` — `DeptName` depends on `DeptID`, not `EmpID` (transitive) → move to `Departments` table.
- Exam question style: *"The table below is not in 2NF. Identify the partial dependency and show the tables after normalisation."*

---

## A4 — SQL (Structured Query Language)

### A4.1 SELECT — Querying Data

**Gist:** `SELECT` is the most important SQL command for exams. It retrieves data from one or more tables, and can filter, sort, and join results. Mastering the clause order and `JOIN` syntax is essential.

**Key line-items:**
- **Basic syntax:**
  ```sql
  SELECT column1, column2
  FROM table_name
  WHERE condition
  ORDER BY column ASC|DESC;
  ```
- `SELECT *` — retrieve all columns
- `WHERE` — filter rows; uses `=`, `<>`, `<`, `>`, `<=`, `>=`, `LIKE`, `IN`, `BETWEEN`, `AND`, `OR`, `NOT`
- `ORDER BY` — sort results; default is ASC (ascending)
- `DISTINCT` — remove duplicate rows from results
- `LIKE` with wildcards: `%` = any sequence of characters; `_` = exactly one character
- **Aggregate functions:** `COUNT()`, `SUM()`, `AVG()`, `MAX()`, `MIN()`
- `GROUP BY` — group rows for aggregate functions
- `HAVING` — filter groups (like WHERE but for aggregates)
- **JOIN syntax:**
  ```sql
  SELECT a.col, b.col
  FROM TableA a
  JOIN TableB b ON a.pk = b.fk;
  ```
- `INNER JOIN` — only matching rows from both tables
- `LEFT JOIN` — all rows from left table, matched rows from right (NULLs where no match)

**Examples:**
```sql
-- All students in Grade 11, alphabetically
SELECT Name, Grade
FROM Students
WHERE Grade = 11
ORDER BY Name ASC;

-- Count of orders per customer
SELECT CustomerID, COUNT(*) AS OrderCount
FROM Orders
GROUP BY CustomerID
HAVING COUNT(*) > 5;

-- Join: student name with their enrolled course names
SELECT s.Name, c.CourseName
FROM Students s
JOIN Enrolments e ON s.StudentID = e.StudentID
JOIN Courses c ON e.CourseID = c.CourseID;
```

---

### A4.2 INSERT, UPDATE, DELETE

**Gist:** These three DML commands modify data in a database. Exams often ask you to write or trace these statements, and to understand the risk of missing a `WHERE` clause in `UPDATE` and `DELETE`.

**Key line-items:**
- **INSERT:**
  ```sql
  INSERT INTO table_name (col1, col2, col3)
  VALUES (val1, val2, val3);
  ```
  - Column list can be omitted if supplying all values in order
- **UPDATE:**
  ```sql
  UPDATE table_name
  SET col1 = newVal1, col2 = newVal2
  WHERE condition;
  ```
  - **Without `WHERE`**, every row is updated — a common, dangerous mistake
- **DELETE:**
  ```sql
  DELETE FROM table_name
  WHERE condition;
  ```
  - **Without `WHERE`**, every row is deleted (table is emptied but structure remains)
  - `DROP TABLE` removes the table entirely; `DELETE` only removes rows

**Examples:**
```sql
-- Add a new student
INSERT INTO Students (StudentID, Name, Grade)
VALUES (1042, 'Priya', 11);

-- Update a student's grade
UPDATE Students
SET Grade = 12
WHERE StudentID = 1042;

-- Remove a student record
DELETE FROM Students
WHERE StudentID = 1042;
```
- Exam question style: *"Write an SQL statement to update the price of product 'P005' to 29.99."*

---

## A5 — Data Integrity & Security

### A5.1 Validation & Verification

**Gist:** Validation checks that data conforms to expected rules before it is accepted into the system; verification checks that data has been entered accurately (comparing input against the original source). Both reduce the risk of incorrect data corrupting the database.

**Key line-items:**
- **Validation** — automated check that data is of the right type, range, or format
  - *Type check* — ensures data is the correct data type (e.g., integer, date)
  - *Range check* — value falls within an acceptable range (e.g., mark between 0 and 100)
  - *Length check* — string not too long or too short (e.g., password ≥ 8 chars)
  - *Presence check* — field cannot be left empty / NULL
  - *Format check* — matches a pattern (e.g., email must contain @)
  - *Check digit* — calculated digit appended to verify code accuracy (e.g., ISBN-13, barcode)
  - *Lookup / referential check* — value must exist in a reference table
- **Verification** — human or procedural check that transcribed data matches the original
  - *Double entry* — data typed twice; system flags any discrepancy
  - *Proof-reading* — human reviews printed output against source document
- Validation ≠ Verification: validation catches wrong-format data; verification catches transcription errors

**Examples:**
- Entering age = -5 fails a range check.
- Entering a date "31/02/2024" fails a format/calendar check.
- A user types their email twice on a form (double-entry verification).
- Exam question style: *"Describe two validation checks that could be applied to the 'Date of Birth' field."*

---

### A5.2 Access Control

**Gist:** Access control is the set of mechanisms that restrict who can see or modify data in a database. It is the primary tool for maintaining confidentiality and data integrity, and is especially important when a DBMS is shared by multiple users with different roles.

**Key line-items:**
- **Authentication** — verifying the identity of a user (e.g., username + password, biometrics, 2FA)
- **Authorisation** — determining what an authenticated user is allowed to do
- **User privileges/permissions:** `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `CREATE`, `DROP` — granted per user or role
- SQL `GRANT` and `REVOKE` commands control permissions:
  ```sql
  GRANT SELECT ON Students TO 'teacher_user';
  REVOKE DELETE ON Students FROM 'teacher_user';
  ```
- **Role-based access control (RBAC)** — permissions assigned to roles (e.g., Admin, Teacher, Student); users inherit role permissions
- **Views** — virtual tables that restrict which rows/columns a user can see
- **Encryption** — data at rest or in transit encrypted to prevent unauthorised reading
- **Audit logs** — record all database actions for accountability

**Examples:**
- A school DBMS: `Student` role can SELECT their own record; `Teacher` can SELECT all; `Admin` can INSERT/UPDATE/DELETE.
- A view `StudentPublicView` shows only Name and Grade, hiding DateOfBirth and contact details.
- Exam question style: *"Explain two methods a database administrator could use to protect student data."*

---
---

# OPTION B: MODELLING & SIMULATION

*Core idea: Using computational models to represent real-world systems.*

---

## B1 — Principles of Modelling

### B1.1 Abstraction

**Gist:** Abstraction is the process of simplifying a complex real-world system by including only the details relevant to the purpose of the model, and deliberately ignoring everything else. Without abstraction, a model would be as complex as reality itself — and therefore useless.

**Key line-items:**
- **Abstraction** — removing unnecessary detail to focus on what matters for the model's purpose
- Levels of abstraction: the further from reality, the more simplified the representation
- A model is always a simplification — no model is perfectly accurate
- **Purpose-driven abstraction** — what is omitted depends on what questions the model must answer
- Examples of abstracted elements: ignoring air resistance in a projectile model; treating all cars as identical particles in a traffic model
- Abstraction enables: faster computation, clearer analysis, generalisability

**Examples:**
- A weather model abstracts the atmosphere into a grid of cells with temperature, pressure, and humidity — it ignores individual molecules.
- A population model treats individuals as identical units — it ignores personal health histories.
- Exam question style: *"Explain how abstraction is used when creating a simulation of road traffic."*

---

### B1.2 Assumptions and Limitations

**Gist:** Every model rests on assumptions — simplifications accepted as true for the model to work. These assumptions are the source of the model's limitations. Identifying and evaluating assumptions is a key exam skill.

**Key line-items:**
- **Assumption** — a condition accepted as true to make the model workable (may not hold in reality)
- **Limitation** — a way in which the model's output may differ from reality, often caused by an assumption
- Common assumptions: constant rates (e.g., birth rate fixed), closed systems (no immigration), uniform behaviour (all individuals identical), linear relationships
- Evaluating a model = checking whether its assumptions are realistic
- **Sensitivity analysis** — testing how much the output changes when assumptions are varied
- More assumptions → simpler model → faster but less accurate → less realistic

**Examples:**
- A disease-spread model assumes every infected person infects exactly 3 others (constant R0) — reality varies by individual and environment.
- A traffic simulation assumes all drivers react in 0.5 s — real reaction times vary.
- Exam question style: *"State one assumption made in this simulation and explain how it limits the model's accuracy."*

---

## B2 — Types of Simulations

### B2.1 Discrete vs Continuous

**Gist:** This distinction describes how time and state are represented in the simulation. Discrete simulations change state at specific events or time steps; continuous simulations change state constantly according to differential equations. Choosing the right type depends on the system being modelled.

**Key line-items:**
- **Discrete simulation** — the system changes state at distinct time steps or events; between steps nothing happens
  - Time advances in fixed increments (e.g., day-by-day, tick-by-tick)
  - Easier to implement; sufficient for event-based systems
  - Example: queuing model (customer arrives = event), turn-based game, population per year
- **Continuous simulation** — state changes are instantaneous and ongoing; represented by continuous mathematical equations
  - Requires numerical integration (e.g., Euler method, Runge-Kutta)
  - More realistic for physical systems
  - Example: fluid flow, electrical circuits, projectile motion
- In practice, computers always discretise time (cannot truly be continuous); the step size determines accuracy

**Examples:**
- Daily COVID-19 case counts → discrete (reported once per day).
- Aircraft wing stress simulation → continuous (forces change every instant).
- Exam question style: *"Explain why a discrete simulation might be chosen to model customer queuing at a bank."*

---

### B2.2 Deterministic vs Stochastic

**Gist:** A deterministic simulation produces the same output every time given the same inputs — it has no randomness. A stochastic simulation includes random elements, so outputs vary between runs. Most real-world systems have randomness, making stochastic models more realistic but harder to analyse.

**Key line-items:**
- **Deterministic simulation** — same input → always same output; no randomness
  - Repeatable and predictable; easy to debug
  - Example: calculating the trajectory of a billiard ball given exact starting conditions
- **Stochastic simulation** — includes random variables; outputs differ between runs
  - Uses random number generators (RNG) with probability distributions
  - Multiple runs needed; results are averages or distributions
  - More realistic for human behaviour, biological systems, financial markets
  - **Monte Carlo method** — using repeated random sampling to estimate outcomes
- **Seed** — initial value for RNG; same seed → same sequence of "random" numbers (enables reproducibility)

**Examples:**
- Predicting the exact orbit of a planet = deterministic.
- Simulating 10,000 random customers visiting a shop to find the average queue length = stochastic (Monte Carlo).
- Exam question style: *"State one reason why a stochastic simulation is more appropriate than a deterministic simulation for modelling customer arrivals."*

---

## B3 — Developing Models

### B3.1 Variables & Parameters

**Gist:** Variables change as the simulation runs (they represent the state of the system); parameters are fixed values set before the simulation starts (they define the conditions). Understanding this distinction is essential for both designing and critiquing a model.

**Key line-items:**
- **Variable** — a quantity whose value changes during the simulation
  - *State variable* — describes the current state of the system (e.g., population size, temperature)
  - *Auxiliary variable* — derived from state variables for use in calculations
- **Parameter** — a fixed input value that defines the model's conditions; set before the run
  - Examples: birth rate, infection probability, speed limit, gravity constant
- **Initial conditions** — the starting values of all state variables at time = 0
- Changing parameters = exploring different scenarios ("what-if" analysis)
- **Time step (Δt)** — the increment of time between updates in a discrete model; smaller Δt → more accurate but slower

**Examples:**
- Population model: variable = current population N; parameters = birth rate r, carrying capacity K.
- Traffic simulation: variable = number of cars on road; parameters = speed limit, junction timing.
- Exam question style: *"Identify one variable and one parameter in the simulation described."*

---

### B3.2 Algorithms for Simulation

**Gist:** The core of any simulation is the algorithm — the step-by-step procedure that updates the system's state at each time step. Being able to trace or write pseudocode for simple simulation loops is an exam skill.

**Key line-items:**
- Typical simulation loop structure:
  1. Initialise variables and parameters
  2. Repeat until end condition:
     a. Calculate new state from current state and rules
     b. Record/output current state
     c. Advance time
  3. Analyse results
- **Euler method** (simple numerical integration): `new_value = old_value + rate × Δt`
- **Event-driven simulation** — advances to the next event rather than fixed time steps; more efficient for sparse events
- Random number generation for stochastic elements: `rand()` mapped to probability distributions
- **Validation** — comparing simulation output to real-world data to check if the model is correct
- **Verification** — checking the code implements the intended algorithm correctly

**Examples:**
- Population growth (Euler): `N_new = N + (birth_rate - death_rate) × N × Δt`
- Pseudocode for a simple infection spread simulation with random contact events.
- Exam question style: *"Trace the algorithm for the first three time steps of this population simulation."*

---

## B4 — Applications

### B4.1 Scientific Simulations

**Gist:** Simulations are used across science when real experiments are impossible, too dangerous, too expensive, or too slow. Knowing common application areas and why simulation is preferred over experimentation is an important exam point.

**Key line-items:**
- **Why simulate instead of experiment?**
  - Too dangerous (nuclear reactions, pandemic spread)
  - Too expensive (full-scale crash testing)
  - Too slow (geological processes, climate over decades)
  - Impossible to observe directly (subatomic particles, black holes)
  - Ethical constraints (human medical trials)
- **Weather modelling** — divides atmosphere into 3D grid cells; solves fluid dynamics equations; updated every few minutes
- **Traffic simulation** — models vehicle flow to optimise signal timing, detect congestion
- **Population models** — predicts growth, resource consumption, species interactions (predator-prey)
- **Epidemic models** — SIR model (Susceptible → Infected → Recovered); used to evaluate intervention strategies
- **Molecular dynamics** — simulates atomic interactions in drug discovery
- **Structural engineering** — finite element analysis of bridges, aircraft under load

**Examples:**
- The SIR epidemic model helped governments decide lockdown timing during COVID-19.
- NASA simulates spacecraft re-entry heating before physical testing.
- Exam question style: *"Describe two advantages of using a simulation rather than a physical experiment to model vehicle crash safety."*

---

## B5 — Evaluation

### B5.1 Accuracy vs Realism

**Gist:** A simulation can be accurate (outputs match reality) without being fully realistic (representing all real-world complexity), and vice versa. The trade-off between accuracy and computational cost is central to evaluating any model.

**Key line-items:**
- **Accuracy** — how closely the simulation's output matches observed real-world data
- **Realism** — how closely the model's internal mechanics reflect actual processes
- A highly abstracted model can still be accurate if its simplified rules produce the right outputs
- More complex model ≠ more accurate (over-fitting, incorrect assumptions)
- **Calibration** — adjusting parameters until the model's outputs match known historical data
- **Validation** — testing the calibrated model against new, unseen data
- Methods to evaluate: compare with historical data, expert review, sensitivity analysis
- Trade-off: more realism → more parameters → harder to calibrate → higher computational cost

**Examples:**
- A simple SIR model with constant R0 may match overall epidemic curve (accurate) but ignores age-stratification (not fully realistic).
- Exam question style: *"Evaluate the accuracy of this simulation by identifying two assumptions that may reduce its reliability."*

---

### B5.2 Ethical Implications

**Gist:** Simulations influence major decisions in healthcare, policy, finance, and engineering. When models are wrong or misused, the consequences can be severe. The IB expects awareness of ethical responsibilities around simulation.

**Key line-items:**
- **Ethical concerns:**
  - Over-reliance on model output without understanding its limitations
  - Models encode assumptions that may embed bias (e.g., demographic assumptions in health models)
  - Results can be selectively reported to support a pre-determined conclusion
  - Privacy: simulations may use personal data (medical records, movement data)
  - Decisions based on flawed models can harm populations (e.g., wrong epidemic response)
- **Transparency** — models used for public policy should be open and peer-reviewed
- **Reproducibility** — others should be able to replicate the simulation with the same parameters
- Informed consent issues when personal data is used to train/validate a model
- Environmental impact of running large-scale simulations (energy consumption)

**Examples:**
- Financial risk models that failed to predict the 2008 crash led to global economic harm — over-confidence in models without stress-testing edge cases.
- Exam question style: *"Discuss one ethical issue arising from using a simulation to make public health decisions."*

---
---

# OPTION C: WEB SCIENCE

*Core idea: How the web works and its societal impact.*

---

## C1 — Internet Fundamentals

### C1.1 TCP/IP and DNS

**Gist:** The internet runs on TCP/IP — a suite of protocols that break data into packets, route them across networks, and reassemble them at the destination. DNS is the internet's phone book, translating human-readable domain names into the IP addresses computers use to find each other.

**Key line-items:**
- **Protocol** — an agreed set of rules for communication between devices
- **TCP/IP (Transmission Control Protocol / Internet Protocol)** — the foundational protocol suite of the internet
  - **IP** — handles addressing and routing of packets; every device has a unique IP address
  - **TCP** — handles reliable, ordered delivery; breaks data into packets, acknowledges receipt, requests retransmission of lost packets
- **Packet** — a small chunk of data; contains header (source IP, destination IP, sequence number) + payload
- **Packet switching** — packets may travel different routes and are reassembled at destination; robust (no single point of failure)
- **IP address** — a numerical label identifying a device on a network
  - IPv4: 32-bit, e.g., `192.168.1.1` (approx. 4.3 billion addresses — now exhausted)
  - IPv6: 128-bit, e.g., `2001:0db8::1` (vastly more addresses)
- **DNS (Domain Name System)** — translates domain names (e.g., `www.ibo.org`) into IP addresses
  - DNS server hierarchy: root → TLD (.org, .com) → authoritative server
  - **DNS lookup process:** browser checks cache → queries local DNS resolver → resolver queries root/TLD → returns IP
- **Port** — a number identifying a specific process/service on a host (e.g., HTTP = 80, HTTPS = 443, FTP = 21)
- **URL (Uniform Resource Locator)** — full address of a web resource: `https://www.example.com/page`

**Examples:**
- Typing `www.ibo.org` in a browser triggers a DNS lookup → IP returned → TCP connection on port 443 → data transferred in packets.
- Exam question style: *"Outline the role of DNS in accessing a web page."*

---

### C1.2 Client-Server Model

**Gist:** The web is built on the client-server model: clients (browsers) request resources, and servers respond with the requested content. Understanding request-response cycles, HTTP methods, and the role of each party is foundational to Web Science.

**Key line-items:**
- **Client** — the device or application requesting a service (e.g., web browser, mobile app)
- **Server** — the device or application providing the service (e.g., web server, database server)
- **HTTP (HyperText Transfer Protocol)** — the application-layer protocol for web communication
- **HTTPS** — HTTP secured with TLS/SSL encryption; protects data in transit
- **HTTP methods:**
  - `GET` — request data from server (e.g., load a web page)
  - `POST` — send data to server (e.g., submit a form, login credentials)
  - `PUT` — update existing resource
  - `DELETE` — remove a resource
- **HTTP status codes:** 200 OK, 301 Redirect, 404 Not Found, 500 Internal Server Error
- **Request-response cycle:**
  1. Client sends HTTP request (method, URL, headers)
  2. Server processes request
  3. Server returns HTTP response (status code, headers, body)
- **Web server software** — e.g., Apache, Nginx
- **Distributed systems** — multiple servers share load (load balancing, CDNs)

**Examples:**
- Browser sends `GET /index.html HTTP/1.1` → server responds `200 OK` + HTML content.
- Login form data sent via `POST` (not `GET`) to hide credentials from the URL.
- Exam question style: *"Describe the client-server interaction when a user submits a search query."*

---

## C2 — Web Technologies

### C2.1 HTML and CSS Basics

**Gist:** HTML (HyperText Markup Language) provides the structure and content of web pages; CSS (Cascading Style Sheets) controls their visual presentation. Together they form the foundation of every webpage. The IB expects basic literacy: tag identification, attribute use, and the CSS box model.

**Key line-items:**
- **HTML** — a markup language using tags to define structure
  - Tags: `<html>`, `<head>`, `<title>`, `<body>`, `<h1>`–`<h6>`, `<p>`, `<a>`, `<img>`, `<ul>`, `<ol>`, `<li>`, `<table>`, `<form>`, `<input>`
  - **Attribute** — extra information within a tag: `href`, `src`, `alt`, `id`, `class`
  - HTML is not a programming language — it has no logic, no loops
- **CSS** — rules that style HTML elements; format: `selector { property: value; }`
  - **Selectors:** element (`p`), class (`.menu`), ID (`#header`)
  - Key properties: `color`, `background-color`, `font-size`, `margin`, `padding`, `border`, `display`, `position`
  - **Box model:** every element = content + padding + border + margin
  - CSS can be inline, internal (`<style>`), or external (linked `.css` file)
- **Separation of concerns** — HTML for structure, CSS for style, JavaScript for behaviour

**Examples:**
```html
<a href="https://www.ibo.org" target="_blank">Visit IBO</a>
<img src="logo.png" alt="School logo" width="200">
```
```css
h1 { font-family: Arial; color: #333; font-size: 24pt; }
.container { max-width: 800px; margin: auto; }
```
- Exam question style: *"Write HTML to create a hyperlink that opens in a new tab."*

---

### C2.2 Dynamic vs Static Web Pages

**Gist:** Static pages deliver the same content to every user every time; dynamic pages are generated on the fly, tailoring content to the user, their data, or the time of request. Understanding this distinction explains why most modern websites use server-side or client-side scripting.

**Key line-items:**
- **Static web page** — fixed HTML file on a server; same content for every visitor; fast, simple, no server processing
  - Suitable for: brochure sites, documentation, landing pages
- **Dynamic web page** — content generated at request time; varies by user, session, or data
  - **Server-side generation** — server runs a script (e.g., PHP, Python, Node.js), queries a database, builds HTML, sends it to client
  - **Client-side generation** — JavaScript runs in the browser and updates the DOM after page load (e.g., React, Vue)
- **CGI (Common Gateway Interface)** — early standard for server-side scripts
- **Cookies** — small data files stored on client to persist session information (e.g., login state, shopping cart)
- **Session** — server-side state tracking for a user during a visit
- **AJAX (Asynchronous JavaScript and XML)** — allows partial page updates without full reload (used in Google Maps, social feeds)

**Examples:**
- A school homepage with opening hours = static.
- A personalised newsfeed that shows different content per user = dynamic (server queries user preferences database).
- Exam question style: *"Explain the difference between a static and a dynamic web page, using the context of an online shopping website."*

---

## C3 — Search Engines

### C3.1 Indexing and Ranking Algorithms

**Gist:** Search engines work in three stages: crawling (discovering pages), indexing (storing and cataloguing content), and ranking (determining which results to show first). The ranking algorithm — notably Google's PageRank — is the commercially critical part.

**Key line-items:**
- **Web crawler (spider/bot)** — automated program that follows hyperlinks to discover and download web pages
- **Indexing** — processing crawled pages and storing them in a searchable index (a giant inverted index: word → list of pages containing it)
- **Inverted index** — maps every word to the documents containing it, enabling fast keyword lookups
- **PageRank** — Google's original algorithm: a page's importance is based on the number and quality of pages linking to it (inbound links = votes)
- **Ranking factors:**
  - Keyword relevance (does the page contain the search terms?)
  - PageRank / authority (how many quality sites link to it?)
  - Freshness (how recently was it updated?)
  - User engagement signals (click-through rate, time on site)
  - Personalisation (user's location, history)
- **SEO (Search Engine Optimisation)** — techniques to improve a page's ranking
  - White-hat: quality content, meta tags, backlinks
  - Black-hat: keyword stuffing, link farms (penalised)
- **Meta tags** — HTML tags providing information to search engines: `<meta name="description" content="...">`, `<meta name="keywords" content="...">`

**Examples:**
- Searching "IB CS revision" → crawler has indexed relevant pages → inverted index finds all pages with those terms → PageRank + keyword relevance determines order.
- Exam question style: *"Explain how a search engine uses a web crawler and an index to respond to a search query."*

---

## C4 — Social & Ethical Issues

### C4.1 Privacy and Security

**Gist:** The web collects enormous amounts of personal data, creating significant privacy risks. Security threats — from hacking to phishing — are constant. The IB expects awareness of both the risks and the technical/legal measures to address them.

**Key line-items:**
- **Privacy issues:**
  - Data harvesting by websites (cookies, tracking pixels, browser fingerprinting)
  - Third-party cookies track users across multiple sites
  - Personal data stored without user awareness
  - Data breaches expose personal information
  - GDPR (EU General Data Protection Regulation) — legal framework requiring explicit consent, right to erasure
- **Security threats:**
  - **Phishing** — fake emails/sites that trick users into revealing credentials
  - **Man-in-the-middle attack** — attacker intercepts communication between client and server
  - **SQL injection** — malicious SQL inserted into a form field to manipulate the database
  - **Cross-site scripting (XSS)** — injecting malicious scripts into web pages viewed by other users
  - **DDoS (Distributed Denial of Service)** — flooding a server with requests to make it unavailable
- **Countermeasures:**
  - HTTPS / TLS encryption
  - Firewalls and intrusion detection systems
  - Input validation and parameterised queries (prevent SQL injection)
  - Two-factor authentication (2FA)
  - Regular security audits and patches
- **Anonymity vs accountability** — online anonymity protects free speech but enables harmful behaviour

**Examples:**
- SQL injection: entering `' OR '1'='1` in a login field could bypass authentication if queries are not parameterised.
- Exam question style: *"Describe two security measures a website could use to protect user data."*

---

### C4.2 Digital Divide

**Gist:** The digital divide is the gap between those who have reliable access to digital technology and the internet, and those who do not. It exists within and between countries, and has significant social, economic, and educational consequences.

**Key line-items:**
- **Digital divide** — inequality in access to digital technology and the internet
- **Dimensions:**
  - *Global divide* — between developed and developing nations
  - *Social divide* — within a country (urban vs rural, wealthy vs poor, young vs old)
  - *Gender divide* — women and girls disproportionately lacking access in some regions
- **Causes:** cost of devices and connectivity, lack of infrastructure, language barriers (most web content is in English), lack of digital literacy
- **Consequences:** educational disadvantage, limited economic opportunities, reduced access to healthcare information, political exclusion
- **Bridging the divide:** government investment in infrastructure, low-cost devices (e.g., Raspberry Pi), community Wi-Fi, digital literacy programmes
- **Second-level divide** — even among those with internet access, quality of use varies (consuming vs creating; entertainment vs education)

**Examples:**
- Remote rural communities in developing countries may have no fibre broadband, limiting students' access to online learning.
- Exam question style: *"Discuss the impact of the digital divide on educational opportunities."*

---

## C5 — Web Trends

### C5.1 Social Media and Big Data

**Gist:** Social media platforms generate vast quantities of user-generated data, contributing to the "big data" phenomenon. Understanding what big data is, why it matters, and its social and ethical implications is essential for this section.

**Key line-items:**
- **Social media** — platforms enabling users to create, share, and interact with content (e.g., Instagram, Twitter/X, YouTube, TikTok)
- **User-generated content (UGC)** — content created by users rather than organisations
- **Big data** — datasets too large or complex for traditional processing tools; characterised by the **3 Vs:**
  - *Volume* — enormous quantities of data
  - *Velocity* — data generated and processed at high speed (real-time streams)
  - *Variety* — many types: structured (databases), semi-structured (JSON), unstructured (text, images, video)
- **Data mining** — discovering patterns and insights in large datasets
- **Machine learning** — algorithms trained on big data to make predictions (e.g., recommendation engines)
- **Personalisation** — using data to tailor content (ads, news, search results) to individual users
- **Filter bubble** — algorithmic curation showing only content aligned with existing views → reinforces bias
- **Monetisation of data** — user data sold to advertisers; "if the product is free, you are the product"
- **Data sovereignty** — questions about who owns and controls personal data

**Examples:**
- Facebook analyses user likes/shares to target advertising with high precision.
- Netflix uses viewing data (big data) and ML to generate personalised recommendations.
- Exam question style: *"Explain two ethical concerns raised by the use of big data by social media companies."*

---
---

# OPTION D: OBJECT-ORIENTED PROGRAMMING (OOP)

*Core idea: Designing software using classes and objects.*

---

## D1 — Basic OOP Concepts

### D1.1 Classes and Objects

**Gist:** A class is a blueprint or template defining a category of things — its characteristics (attributes) and behaviours (methods). An object is a specific instance created from that blueprint. The OOP paradigm organises code around these real-world abstractions, making large programs easier to design, maintain, and reuse.

**Key line-items:**
- **Class** — a user-defined type; defines the structure and behaviour shared by all objects of that type
- **Object (instance)** — a concrete realisation of a class in memory; has its own values for the class attributes
- **Instantiation** — the act of creating an object from a class using a constructor
- **Constructor** — a special method called when an object is created; initialises attributes (`__init__` in Python, `ClassName()` in Java)
- **Attribute (instance variable / field)** — data belonging to an object (e.g., `name`, `age`)
- **Method** — a function defined inside a class; operates on the object's data
- **`this` / `self`** — keyword referring to the current object instance within a class definition
- **State** — the current values of an object's attributes
- **Behaviour** — what an object can do (its methods)

**Examples:**
```java
// Class definition
public class Dog {
    String name;
    String breed;

    public Dog(String name, String breed) {
        this.name = name;
        this.breed = breed;
    }

    public void bark() {
        System.out.println(name + " says: Woof!");
    }
}

// Creating objects
Dog d1 = new Dog("Rex", "Labrador");
Dog d2 = new Dog("Fido", "Poodle");
d1.bark(); // Rex says: Woof!
```
- Exam question style: *"Define the terms 'class' and 'object', and give one example of each from the context of a library system."*

---

### D1.2 Attributes and Methods

**Gist:** Attributes store what an object knows (its state); methods define what an object can do (its behaviour). Understanding the difference, and being able to identify and write both in code, is a foundational OOP exam skill.

**Key line-items:**
- **Instance attribute** — unique to each object; created in the constructor
- **Class attribute (static field)** — shared by all objects of the class; declared with `static` in Java
- **Method** — a function in a class; takes `(this/self)` as implicit first parameter
- **`void` method** — returns nothing; performs an action (e.g., `print()`)
- **Value-returning method** — returns a value of a specified type
- **Method signature** — method name + parameter list; must be unique in the class (in Java, overloading uses same name with different signatures)
- **Calling a method:** `object.methodName(arguments)`

**Examples:**
```java
public class BankAccount {
    private double balance;          // instance attribute

    public void deposit(double amount) {   // void method
        balance += amount;
    }

    public double getBalance() {     // value-returning method
        return balance;
    }
}
```
- Exam question style: *"Identify two attributes and one method for a class representing a Product in an e-commerce system."*

---

## D2 — Encapsulation

### D2.1 Access Modifiers

**Gist:** Encapsulation is the OOP principle of bundling data (attributes) and the methods that operate on them into a single unit (the class), while restricting direct external access. Access modifiers enforce this hiding, protecting the object's internal state from unintended modification.

**Key line-items:**
- **Encapsulation** — hiding internal state; exposing only what is necessary through a controlled interface
- **Access modifiers (Java):**
  - `private` — accessible only within the same class (recommended for attributes)
  - `public` — accessible from anywhere
  - `protected` — accessible within the class and its subclasses
  - *(default/package-private)* — accessible within the same package
- **Information hiding** — the principle that internal implementation details should not be visible outside the class
- Benefits of encapsulation: protects data integrity, reduces coupling, allows internal changes without breaking external code

**Examples:**
- `private double balance;` in `BankAccount` prevents other classes from directly setting `balance = -999;`.
- Exam question style: *"Explain why it is good practice to declare attributes as `private` in a class."*

---

### D2.2 Getters and Setters

**Gist:** Getters (accessors) and setters (mutators) are public methods that provide controlled, indirect access to private attributes. They allow validation logic to be inserted (e.g., rejecting a negative age), maintaining data integrity while preserving the interface.

**Key line-items:**
- **Getter (accessor)** — a method that returns the value of a private attribute; named `getAttributeName()` by convention
- **Setter (mutator)** — a method that sets the value of a private attribute, often including validation; named `setAttributeName(value)`
- Using getters/setters instead of `public` attributes enables:
  - Input validation inside the setter
  - Read-only attributes (getter with no setter)
  - Changing internal representation without changing the external interface
- In Python: `@property` decorator for getters; `@attribute.setter` for setters

**Examples:**
```java
public class Student {
    private int age;

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age > 0 && age < 120) {
            this.age = age;
        }
    }
}
```
- Exam question style: *"Write a getter and setter for the `price` attribute of a `Product` class, ensuring the price cannot be set to a negative value."*

---

## D3 — Inheritance

### D3.1 Superclass and Subclass

**Gist:** Inheritance allows a new class (subclass) to acquire the attributes and methods of an existing class (superclass), extending or specialising its behaviour. It is the mechanism for code reuse and the "is-a" relationship in OOP.

**Key line-items:**
- **Superclass (parent class / base class)** — the class being extended
- **Subclass (child class / derived class)** — the class that inherits from the superclass
- **Syntax (Java):** `class Dog extends Animal { ... }`
- The subclass inherits all `public` and `protected` members of the superclass
- The subclass can add new attributes and methods
- The subclass can **override** superclass methods (provide its own implementation)
- **`super` keyword** — calls the superclass constructor or method from within the subclass
- **`extends`** (Java) / `:` (C++) / inheriting from a class (Python: `class Dog(Animal):`)
- **Single vs multiple inheritance:** Java supports only single inheritance (one superclass); interfaces provide a workaround

**Examples:**
```java
class Animal {
    String name;
    public void eat() { System.out.println(name + " eats."); }
}

class Dog extends Animal {
    public void bark() { System.out.println(name + " barks."); }
}

Dog d = new Dog();
d.name = "Rex";
d.eat();  // inherited from Animal
d.bark(); // defined in Dog
```
- Exam question style: *"Draw a class hierarchy for a vehicle management system. Explain what is inherited by the `ElectricCar` class."*

---

### D3.2 Code Reuse

**Gist:** Inheritance's primary practical benefit is code reuse — writing a method once in a superclass and having it automatically available in all subclasses. This reduces duplication, centralises bug fixes, and makes systems easier to extend.

**Key line-items:**
- Reuse: change `eat()` in `Animal` and all subclasses get the update automatically
- **DRY principle** — Don't Repeat Yourself; inheritance is one tool for achieving this
- Alternative to inheritance for reuse: **composition** (an object *has-a* relationship; one class contains an instance of another)
- **"is-a" test** — use inheritance if "SubclassObject is-a SuperclassObject" is true (e.g., Dog is-a Animal ✓)
- **"has-a" test** — use composition if "Object has-a Thing" (e.g., Car has-a Engine; don't inherit from Engine)
- Inheritance can be overused — deep hierarchies become difficult to maintain

**Examples:**
- `BankAccount` superclass has `deposit()` and `withdraw()`; `SavingsAccount` and `CurrentAccount` subclasses inherit these and add their own specific methods.
- Exam question style: *"Explain how inheritance promotes code reuse in the context of the class hierarchy shown."*

---

## D4 — Polymorphism

### D4.1 Method Overriding

**Gist:** Method overriding allows a subclass to provide its own implementation of a method already defined in the superclass. At runtime, the correct version of the method is called based on the actual type of the object — this is dynamic (runtime) polymorphism. It makes code flexible and extensible.

**Key line-items:**
- **Method overriding** — subclass defines a method with the same name, return type, and parameters as the superclass method
- **`@Override` annotation** (Java) — optional but good practice; compiler checks the override is valid
- **Dynamic dispatch / runtime polymorphism** — at runtime, Java calls the most derived version of the method based on the actual object type, not the variable type
- A superclass reference can point to a subclass object:
  `Animal a = new Dog();` → `a.makeSound()` calls Dog's version
- **Abstract method** — declared in superclass with no body; forces all subclasses to override it
  `public abstract void makeSound();`
- **Abstract class** — cannot be instantiated; exists only to be subclassed; may have both abstract and concrete methods

**Examples:**
```java
class Animal {
    public void makeSound() { System.out.println("..."); }
}

class Dog extends Animal {
    @Override
    public void makeSound() { System.out.println("Woof!"); }
}

class Cat extends Animal {
    @Override
    public void makeSound() { System.out.println("Meow!"); }
}

Animal a = new Dog();
a.makeSound(); // prints "Woof!" — runtime polymorphism
```
- Exam question style: *"Explain how polymorphism is demonstrated in the code above. State the output of each method call."*

---

### D4.2 Method Overloading

**Gist:** Method overloading allows multiple methods with the same name in the same class, as long as they have different parameter lists (different number or types of parameters). This is compile-time (static) polymorphism. It lets a class provide multiple convenient ways to call the same logical operation.

**Key line-items:**
- **Method overloading** — same method name, different parameter signature (number, type, or order of parameters); return type alone is NOT sufficient to distinguish overloads
- Resolved at **compile time** (unlike overriding, which is resolved at runtime)
- **Constructor overloading** — a class can have multiple constructors with different parameter lists
- **Key distinction:**
  - Overloading = same class, different signatures → compile-time polymorphism
  - Overriding = subclass, same signature → runtime polymorphism

**Examples:**
```java
public class Calculator {
    public int add(int a, int b) { return a + b; }
    public double add(double a, double b) { return a + b; }
    public int add(int a, int b, int c) { return a + b + c; }
}
// All three are valid — different signatures
```
- Exam question style: *"Distinguish between method overloading and method overriding."*

---

## D5 — Program Design

### D5.1 UML Diagrams

**Gist:** UML (Unified Modelling Language) is the standard notation for visualising OOP designs. The IB focuses on class diagrams, which show classes, their attributes, methods, and the relationships between them. Being able to read and draw class diagrams is a testable skill.

**Key line-items:**
- **UML Class diagram box:** three sections — class name (top) | attributes (middle) | methods (bottom)
- **Visibility symbols:**
  - `+` = public
  - `-` = private
  - `#` = protected
- **Attribute format:** `- attributeName : dataType`
- **Method format:** `+ methodName(paramName: dataType) : returnType`
- **Relationships shown in UML:**
  - *Association* — solid line; objects are related
  - *Inheritance (generalisation)* — solid line with open arrowhead pointing to superclass
  - *Dependency* — dashed line with open arrow
  - *Aggregation* — open diamond (has-a, loosely)
  - *Composition* — filled diamond (has-a, strongly — part cannot exist without whole)
- **Multiplicity** — annotated on lines: `1`, `0..*`, `1..*`

**Examples:**
```
+------------------+
|     Student      |
+------------------+
| - studentID: int |
| - name: String   |
+------------------+
| + getID(): int   |
| + getName(): Str |
+------------------+
        |
  inheritance
        |
+------------------+
|  GradStudent     |
+------------------+
| - thesis: String |
+------------------+
| + submit(): void |
+------------------+
```
- Exam question style: *"Draw a UML class diagram for a `Shape` superclass and `Circle`, `Rectangle` subclasses. Include at least two attributes and two methods in each."*

---

### D5.2 Class Relationships

**Gist:** Beyond inheritance, classes relate to each other through association, aggregation, and composition. Choosing the right relationship type reflects the real-world connection between concepts and has practical implications for how objects are created and destroyed.

**Key line-items:**
- **Association** — "uses" relationship; one class uses another (loosely); both can exist independently (e.g., `Teacher` teaches `Course`)
- **Aggregation** — "has-a" (weak); the contained object can exist independently (e.g., `Department` has `Employee`s; employees exist without the department)
- **Composition** — "has-a" (strong); the contained object cannot exist without the container (e.g., `House` has `Rooms`; rooms cannot exist without the house)
- **Inheritance** — "is-a" relationship (e.g., `Dog` is-an `Animal`)
- **Dependency** — one class temporarily uses another (e.g., method receives an object as a parameter)
- Correct use of relationships improves design clarity and avoids inappropriate coupling

**Examples:**
- `Library` *aggregates* `Book` objects — books can exist in different libraries.
- `Order` *composes* `OrderLine` objects — an order line makes no sense outside an order.
- Exam question style: *"Explain the difference between aggregation and composition, using a suitable example."*

---

## D6 — Programming Practice

### D6.1 Writing and Debugging Code

**Gist:** The D option is the most code-heavy — exams include writing, tracing, and debugging Java (or pseudocode) programs. Knowing common patterns, error types, and debugging strategies is essential for full marks.

**Key line-items:**
- **Syntax error** — code violates language grammar rules; detected by compiler (e.g., missing semicolon, mismatched brackets)
- **Logic error** — code compiles and runs but produces wrong output; requires testing and tracing to find
- **Runtime error (exception)** — error that occurs during execution (e.g., `NullPointerException`, `ArrayIndexOutOfBoundsException`, division by zero)
- **Debugging strategies:**
  - Print statements to trace variable values
  - Rubber duck debugging — explain the code aloud
  - Using an IDE debugger with breakpoints
  - Test with boundary values and edge cases
- **Testing types:**
  - *White-box testing* — tester has access to source code; tests internal logic paths
  - *Black-box testing* — tester only knows inputs/outputs; tests against requirements
  - *Boundary testing* — testing at the limits of valid input ranges
- **Exception handling (Java):**
  ```java
  try {
      // risky code
  } catch (ExceptionType e) {
      // handle error
  } finally {
      // always runs
  }
  ```

**Examples:**
- Boundary test for `setAge()`: test ages -1 (invalid), 0 (boundary), 1 (valid), 119 (valid), 120 (boundary), 121 (invalid).
- `NullPointerException` occurs when calling a method on an object reference that is `null`.
- Exam question style: *"Identify the error in the following code and explain how it would manifest at runtime."*

---

### D6.2 Tracing Algorithms

**Gist:** Tracing (dry-running) an algorithm means manually executing code step-by-step, recording the state of all variables at each step, and determining the output. Exams frequently include trace tables. Speed and accuracy matter.

**Key line-items:**
- **Trace table** — a table with one column per variable (and sometimes one for output); one row per step or iteration
- Read code line by line; update the trace table for each assignment, condition, and output statement
- Watch for: loop counter changes, condition evaluations, method call returns, object state changes
- Common patterns to recognise:
  - **Linear search** — iterate through list checking each element
  - **Bubble sort** — nested loops swapping adjacent elements
  - **Recursive calls** — track call stack
  - **Accumulator pattern** — summing or counting with a running total
- Always note the final output and any return values

**Examples:**
Trace `factorial(3)`:
```
factorial(3): returns 3 × factorial(2)
  factorial(2): returns 2 × factorial(1)
    factorial(1): returns 1
  → factorial(2) = 2
→ factorial(3) = 6
```
Trace table for `sum = 0; for i in 1..3: sum += i`:

| i | sum |
|---|-----|
| — | 0   |
| 1 | 1   |
| 2 | 3   |
| 3 | 6   |

- Exam question style: *"Trace the following algorithm for the input array [5, 3, 8, 1] and complete the trace table."*

---
---

# QUICK REFERENCE

---

## Command Terms Table

| Term | What it demands |
|------|----------------|
| **State** | Give a specific fact with no explanation; one or two words or a phrase |
| **Define** | Give the precise formal meaning of a term |
| **Outline** | Give a brief account of the main points; more than State but less than Describe |
| **Describe** | Give a detailed account of a process, feature, or system |
| **Explain** | Give reasons or causes; show how or why something works |
| **Construct** | Build or draw something following rules (e.g., write SQL, draw ER diagram) |
| **Analyse** | Break something into parts; examine each part critically |
| **Evaluate** | Assess strengths and weaknesses; reach a judgement |
| **Suggest** | Propose an answer knowing there may be other valid answers |
| **Justify** | Give reasons to support a claim or decision |

---

## Key Formulas & Rules

| Context | Formula / Rule |
|---------|---------------|
| Euler method (simulation) | `new_value = old_value + rate × Δt` |
| Population growth (simple) | `N_new = N + r × N × Δt` (where r = net growth rate) |
| Normalisation test | 1NF → 2NF: remove partial dependencies; 2NF → 3NF: remove transitive dependencies |
| PageRank (concept) | PR(A) ∝ Σ (PR of pages linking to A / outbound links of those pages) |
| Big Data 3 Vs | Volume · Velocity · Variety |
| URL structure | `protocol://domain:port/path?query#fragment` |

---

## Must-Know Definitions Glossary

| Term | One-line definition |
|------|-------------------|
| **Data** | Raw, unprocessed facts with no context |
| **Information** | Data that has been processed into a meaningful, contextual form |
| **Flat-file database** | A single-table database with no links between tables |
| **Relational database** | A database using multiple linked tables to minimise redundancy |
| **Primary key** | A field that uniquely identifies every record in its table |
| **Foreign key** | A field that references the primary key of another table |
| **Referential integrity** | Rule ensuring every foreign key value matches an existing primary key |
| **1NF** | All cells contain atomic values; no repeating groups |
| **2NF** | 1NF + no partial dependencies on the primary key |
| **3NF** | 2NF + no transitive dependencies between non-key attributes |
| **SQL** | Structured Query Language — used to query and manipulate relational databases |
| **JOIN** | SQL clause combining rows from two tables based on a related column |
| **Validation** | Automated check that input data meets defined rules |
| **Verification** | Check that data has been entered accurately against the source |
| **Abstraction** | Simplifying a system by removing irrelevant details |
| **Assumption** | A condition accepted as true to make a model workable |
| **Discrete simulation** | State changes at specific time steps or events |
| **Continuous simulation** | State changes are ongoing and described by continuous equations |
| **Deterministic** | Same input always produces same output; no randomness |
| **Stochastic** | Contains random elements; outputs vary between runs |
| **Monte Carlo method** | Using repeated random sampling to estimate outcomes |
| **TCP/IP** | Protocol suite governing internet data transmission |
| **DNS** | System that translates domain names to IP addresses |
| **HTTP** | Protocol for communication between web clients and servers |
| **Static web page** | Fixed HTML page delivering the same content to all visitors |
| **Dynamic web page** | Page generated on the fly, varying by user or data |
| **Web crawler** | Automated bot that follows links to index web pages |
| **PageRank** | Algorithm ranking pages by the quality and quantity of inbound links |
| **Digital divide** | The gap between those with and without reliable access to digital technology |
| **Filter bubble** | Algorithmic reinforcement of existing beliefs through personalised content |
| **Big data** | Extremely large datasets characterised by Volume, Velocity, and Variety |
| **Class** | A blueprint defining attributes and methods shared by all objects of a type |
| **Object** | A specific instance of a class with its own attribute values |
| **Encapsulation** | Bundling data and methods in a class and hiding internal state |
| **Inheritance** | A subclass acquiring attributes and methods from a superclass |
| **Polymorphism** | The ability of different objects to respond to the same method call differently |
| **Method overriding** | A subclass providing its own implementation of a superclass method |
| **Method overloading** | Multiple methods with the same name but different parameter lists in one class |
| **UML class diagram** | A visual diagram showing classes, attributes, methods, and relationships |
| **Abstraction (OOP)** | Exposing only essential features of a class, hiding implementation details |
| **Composition** | A strong has-a relationship where the part cannot exist without the whole |
| **Aggregation** | A weak has-a relationship where the part can exist independently |

---

*Good luck, Amit. You've got this.*
