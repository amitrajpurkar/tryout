# IB Computer Science SL — Paper 2 Mindmaps
### One map per option · Print on separate pages · Black and white safe

> **Printing tip:** Open this file in VS Code (Mermaid Preview extension), Obsidian, or paste each diagram into [mermaid.live](https://mermaid.live), then print each map on its own A4 page using your browser's **File → Print** with "Background graphics" OFF. All diagrams use greyscale only.

---
---

## Option A — Databases

```mermaid
mindmap
  root((Option A
Databases))
    A1(A1 Database Concepts)
      A1a(Data vs Information)
        A1a1[Data: raw unprocessed facts]
        A1a2[Information: processed with context]
        A1a3[Metadata: data about data]
        A1a4[Quality: accurate complete timely relevant]
      A1b(Flat-file vs Relational)
        A1b1[Flat-file: single table]
        A1b2[Redundancy: data repeated]
        A1b3[Update anomaly: inconsistent change]
        A1b4[Insert anomaly: missing mandatory fields]
        A1b5[Delete anomaly: unintended data loss]
        A1b6[Relational: multiple linked tables]
        A1b7[DBMS: manages storage access security]
    A2(A2 Relational Databases)
      A2a(Tables Records Fields)
        A2a1[Table: data about one entity type]
        A2a2[Record: one row, one instance]
        A2a3[Field: one column, one attribute]
        A2a4[Domain: permitted values for a field]
        A2a5[Degree: number of fields]
        A2a6[Cardinality: number of records]
        A2a7[Null: absent or unknown value]
      A2b(Primary and Foreign Keys)
        A2b1[PK: unique and NOT NULL]
        A2b2[Composite PK: two or more fields]
        A2b3[FK: references another tables PK]
        A2b4[Referential integrity: FK must match PK]
        A2b5[Surrogate key: auto-increment artificial ID]
      A2c(Relationships)
        A2c1[1-to-1: rare, e.g. Person-Passport]
        A2c2[1-to-many: FK on many side]
        A2c3[Many-to-many: needs junction table]
        A2c4[Junction table holds two FKs]
    A3(A3 Database Design)
      A3a(Entity-Relationship Models)
        A3a1[Entity: rectangle, becomes a table]
        A3a2[Attribute: ellipse, becomes a field]
        A3a3[Relationship: diamond on connecting line]
        A3a4[Cardinality: 1 N M or crow-foot notation]
        A3a5[PK attribute underlined in diagram]
      A3b(Normalization)
        A3b1[1NF: atomic values, no lists in a cell]
        A3b2[2NF: remove partial dependencies on PK]
        A3b3[3NF: remove transitive dependencies]
        A3b4[Functional dependency: A determines B]
        A3b5[Goal: reduce redundancy and anomalies]
    A4(A4 SQL)
      A4a(SELECT)
        A4a1[SELECT col FROM table WHERE cond]
        A4a2[ORDER BY col ASC or DESC]
        A4a3[DISTINCT removes duplicate rows]
        A4a4[LIKE with percent and underscore wildcards]
        A4a5[COUNT SUM AVG MAX MIN aggregates]
        A4a6[GROUP BY with HAVING for aggregates]
        A4a7[INNER JOIN on matching rows only]
        A4a8[LEFT JOIN: all left plus matched right]
      A4b(Modifying Data)
        A4b1[INSERT INTO table col VALUES val]
        A4b2[UPDATE table SET col WHERE cond]
        A4b3[DELETE FROM table WHERE cond]
        A4b4[No WHERE on UPDATE or DELETE: all rows affected]
        A4b5[DROP TABLE removes structure entirely]
    A5(A5 Integrity and Security)
      A5a(Validation)
        A5a1[Type check: correct data type]
        A5a2[Range check: value within limits]
        A5a3[Length check: string not too long or short]
        A5a4[Presence check: field cannot be empty]
        A5a5[Format check: matches pattern e.g. email]
        A5a6[Check digit: e.g. ISBN barcode]
      A5b(Verification)
        A5b1[Double entry: type twice flag discrepancy]
        A5b2[Proofreading: compare output to source]
        A5b3[Validation catches wrong format]
        A5b4[Verification catches transcription error]
      A5c(Access Control)
        A5c1[Authentication: verify identity]
        A5c2[Authorisation: what user may do]
        A5c3[GRANT and REVOKE SQL privileges]
        A5c4[RBAC: roles inherit permissions]
        A5c5[Views: restrict visible rows and columns]
        A5c6[Encryption at rest and in transit]
        A5c7[Audit logs record all actions]
```

---
---

## Option B — Modelling and Simulation

```mermaid
mindmap
  root((Option B
Modelling and
Simulation))
    B1(B1 Principles of Modelling)
      B1a(Abstraction)
        B1a1[Remove irrelevant detail]
        B1a2[Keep only what model needs]
        B1a3[Purpose-driven simplification]
        B1a4[No model is perfectly accurate]
        B1a5[Enables faster computation]
        B1a6[Example: treat cars as particles]
      B1b(Assumptions and Limitations)
        B1b1[Assumption: condition accepted as true]
        B1b2[Limitation: where model diverges from reality]
        B1b3[Common: constant rates, closed systems]
        B1b4[Common: uniform behaviour, linearity]
        B1b5[Sensitivity analysis: vary assumptions]
        B1b6[More assumptions means simpler but less accurate]
    B2(B2 Types of Simulation)
      B2a(Discrete vs Continuous)
        B2a1[Discrete: state changes at fixed steps or events]
        B2a2[Discrete examples: daily cases, queue arrivals]
        B2a3[Continuous: state changes at every instant]
        B2a4[Continuous: described by equations]
        B2a5[Continuous examples: fluid flow, projectile]
        B2a6[Computers always discretise: step size matters]
      B2b(Deterministic vs Stochastic)
        B2b1[Deterministic: same input always same output]
        B2b2[Deterministic: no randomness, repeatable]
        B2b3[Stochastic: includes random variables]
        B2b4[Stochastic: run many times, get distribution]
        B2b5[Monte Carlo: repeated random sampling]
        B2b6[Seed: controls RNG for reproducibility]
    B3(B3 Developing Models)
      B3a(Variables and Parameters)
        B3a1[Variable: changes during the simulation run]
        B3a2[State variable: describes system state]
        B3a3[Parameter: fixed before the run starts]
        B3a4[Initial conditions: values at time zero]
        B3a5[Time step delta-t: smaller means more accurate]
        B3a6[Changing parameters enables what-if analysis]
      B3b(Simulation Algorithms)
        B3b1[Initialise variables and parameters]
        B3b2[Loop: calculate new state from current]
        B3b3[Record output at each step]
        B3b4[Advance time then repeat]
        B3b5[Euler method: new = old + rate times dt]
        B3b6[Event-driven: jump to next event]
        B3b7[Validation: does output match real data?]
        B3b8[Verification: does code match algorithm?]
    B4(B4 Applications)
      B4a(Why Simulate Instead of Experiment)
        B4a1[Too dangerous: nuclear, pandemic spread]
        B4a2[Too expensive: full-scale crash testing]
        B4a3[Too slow: climate over decades]
        B4a4[Ethically impossible: human medical trials]
        B4a5[Impossible to observe: subatomic particles]
      B4b(Real-World Examples)
        B4b1[Weather: 3D grid, fluid dynamics equations]
        B4b2[Traffic: optimise signal timing, detect congestion]
        B4b3[Epidemic SIR model: Susceptible Infected Recovered]
        B4b4[Population: predator-prey, resource consumption]
        B4b5[Structural: finite element analysis of bridges]
    B5(B5 Evaluation)
      B5a(Accuracy vs Realism)
        B5a1[Accuracy: output matches observed real data]
        B5a2[Realism: internal mechanics mirror reality]
        B5a3[Simple model can be accurate if rules correct]
        B5a4[More complexity does not always mean better]
        B5a5[Calibration: adjust params to match history]
        B5a6[Validation: test on new unseen data]
      B5b(Ethical Implications)
        B5b1[Over-reliance without understanding limits]
        B5b2[Assumptions can embed demographic bias]
        B5b3[Results selectively reported]
        B5b4[Privacy: personal data used to train model]
        B5b5[Transparency: public models must be open]
        B5b6[Reproducibility: others must replicate]
```

---
---

## Option C — Web Science

```mermaid
mindmap
  root((Option C
Web Science))
    C1(C1 Internet Fundamentals)
      C1a(TCP/IP and DNS)
        C1a1[Protocol: agreed rules for communication]
        C1a2[IP: addressing and routing of packets]
        C1a3[TCP: reliable ordered packet delivery]
        C1a4[Packet: header plus payload]
        C1a5[Packet switching: resilient multiple routes]
        C1a6[IPv4: 32-bit e.g. 192.168.1.1]
        C1a7[IPv6: 128-bit, far more addresses]
        C1a8[DNS: domain name to IP address]
        C1a9[DNS hierarchy: root then TLD then authoritative]
        C1a10[Port: HTTP 80, HTTPS 443, FTP 21]
      C1b(Client-Server Model)
        C1b1[Client: requests service e.g. browser]
        C1b2[Server: provides service e.g. web server]
        C1b3[HTTP: application-layer web protocol]
        C1b4[HTTPS: HTTP plus TLS encryption]
        C1b5[GET: fetch data from server]
        C1b6[POST: send data to server]
        C1b7[PUT: update existing resource]
        C1b8[DELETE: remove a resource]
        C1b9[200 OK, 301 Redirect, 404 Not Found, 500 Error]
        C1b10[Request then response cycle]
    C2(C2 Web Technologies)
      C2a(HTML and CSS)
        C2a1[HTML: markup language for structure]
        C2a2[Tags: h1 p a img table form input]
        C2a3[Attribute: extra info e.g. href src alt]
        C2a4[HTML is not a programming language]
        C2a5[CSS: rules for visual presentation]
        C2a6[Selector then property then value]
        C2a7[Selectors: element class hash-ID]
        C2a8[Box model: content padding border margin]
        C2a9[Separation: HTML structure CSS style JS behaviour]
      C2b(Static vs Dynamic Web Pages)
        C2b1[Static: fixed HTML same for all visitors]
        C2b2[Static: fast, simple, no server processing]
        C2b3[Dynamic: generated per request]
        C2b4[Server-side: PHP Python Node queries DB]
        C2b5[Client-side: JavaScript updates DOM in browser]
        C2b6[AJAX: partial page update without full reload]
        C2b7[Cookie: small file on client for session state]
        C2b8[Session: server-side state tracking per visit]
    C3(C3 Search Engines)
      C3a(Crawling and Indexing)
        C3a1[Web crawler: follows links to discover pages]
        C3a2[Inverted index: word mapped to pages containing it]
        C3a3[Indexing: processing and storing crawled content]
      C3b(Ranking Algorithms)
        C3b1[PageRank: inbound links act as votes]
        C3b2[Quality of linking page also weighted]
        C3b3[Ranking factors: keyword relevance]
        C3b4[Ranking factors: authority and PageRank]
        C3b5[Ranking factors: freshness and engagement]
        C3b6[Personalisation: location and search history]
        C3b7[SEO white-hat: quality content meta-tags backlinks]
        C3b8[SEO black-hat: keyword stuffing link farms]
    C4(C4 Social and Ethical Issues)
      C4a(Privacy and Security)
        C4a1[Cookies and cross-site tracking]
        C4a2[Browser fingerprinting]
        C4a3[Data breaches expose personal info]
        C4a4[GDPR: consent, right to erasure]
        C4a5[Phishing: fake sites steal credentials]
        C4a6[Man-in-the-middle: intercepts communication]
        C4a7[SQL injection: malicious SQL in form field]
        C4a8[XSS: malicious scripts in viewed pages]
        C4a9[DDoS: flood server to make unavailable]
        C4a10[Countermeasures: HTTPS firewalls 2FA parameterised queries]
      C4b(Digital Divide)
        C4b1[Global: developed vs developing nations]
        C4b2[Social: urban vs rural, wealthy vs poor]
        C4b3[Gender divide in access]
        C4b4[Causes: cost, no infrastructure, language]
        C4b5[Causes: lack of digital literacy]
        C4b6[Consequences: education, economy, politics]
        C4b7[Bridging: investment, low-cost devices, literacy programs]
        C4b8[Second-level divide: quality of use varies]
    C5(C5 Web Trends)
      C5a(Social Media and Big Data)
        C5a1[Social media: user-generated content]
        C5a2[Big data: Volume Velocity Variety]
        C5a3[Volume: enormous quantity of data]
        C5a4[Velocity: generated and processed at high speed]
        C5a5[Variety: structured semi-structured unstructured]
        C5a6[Data mining: discovering patterns]
        C5a7[Machine learning: predictions from big data]
        C5a8[Filter bubble: algorithm reinforces existing views]
        C5a9[Monetisation: user data sold to advertisers]
        C5a10[Data sovereignty: who owns personal data]
```

---
---

## Option D — Object-Oriented Programming

```mermaid
mindmap
  root((Option D
OOP))
    D1(D1 Basic OOP Concepts)
      D1a(Classes and Objects)
        D1a1[Class: blueprint defining attributes and methods]
        D1a2[Object: a specific instance in memory]
        D1a3[Instantiation: creating an object from a class]
        D1a4[Constructor: initialises object on creation]
        D1a5[this or self: refers to current instance]
        D1a6[State: current values of attributes]
        D1a7[Behaviour: what the object can do]
      D1b(Attributes and Methods)
        D1b1[Instance attribute: unique value per object]
        D1b2[Class attribute: shared static across all objects]
        D1b3[void method: performs action returns nothing]
        D1b4[Value-returning method: returns a result]
        D1b5[Method signature: name plus parameter list]
        D1b6[Call: object dot methodName arguments]
    D2(D2 Encapsulation)
      D2a(Access Modifiers)
        D2a1[private: accessible within class only]
        D2a2[public: accessible from anywhere]
        D2a3[protected: class and its subclasses]
        D2a4[Information hiding: hide internal state]
        D2a5[Reduces coupling between classes]
        D2a6[Allows internal changes without breaking interface]
      D2b(Getters and Setters)
        D2b1[Getter accessor: returns private attribute]
        D2b2[Named getAttributeName by convention]
        D2b3[Setter mutator: sets value with validation]
        D2b4[Named setAttributeName by convention]
        D2b5[Getter only: creates read-only attribute]
        D2b6[Validation logic kept inside setter]
    D3(D3 Inheritance)
      D3a(Superclass and Subclass)
        D3a1[Superclass: parent base class being extended]
        D3a2[Subclass: child derived class that inherits]
        D3a3[Java syntax: class Dog extends Animal]
        D3a4[Inherits all public and protected members]
        D3a5[Can add new attributes and methods]
        D3a6[Can override superclass methods]
        D3a7[super: calls parent constructor or method]
        D3a8[Java: single inheritance only]
      D3b(Code Reuse)
        D3b1[DRY: Do Not Repeat Yourself]
        D3b2[Fix in superclass updates all subclasses]
        D3b3[is-a test: Dog is-an Animal - use inheritance]
        D3b4[has-a test: Car has-an Engine - use composition]
        D3b5[Deep hierarchies become hard to maintain]
    D4(D4 Polymorphism)
      D4a(Method Overriding)
        D4a1[Same name return type and params as superclass]
        D4a2[Different body in the subclass]
        D4a3[Override annotation: compiler verifies]
        D4a4[Dynamic dispatch: runtime picks correct version]
        D4a5[Animal a = new Dog - calls Dogs method]
        D4a6[Abstract method: no body, forces override]
        D4a7[Abstract class: cannot be instantiated]
      D4b(Method Overloading)
        D4b1[Same method name, different parameter list]
        D4b2[Different number or type of parameters]
        D4b3[Return type alone is NOT enough to distinguish]
        D4b4[Resolved at compile time: static polymorphism]
        D4b5[Constructor overloading: multiple constructors]
        D4b6[Overloading vs Overriding: same class vs subclass]
    D5(D5 Program Design)
      D5a(UML Class Diagrams)
        D5a1[Three-part box: name, attributes, methods]
        D5a2[Plus sign: public visibility]
        D5a3[Minus sign: private visibility]
        D5a4[Hash sign: protected visibility]
        D5a5[Attribute format: minus name colon DataType]
        D5a6[Method format: plus name params colon ReturnType]
        D5a7[Inheritance: solid line, open arrowhead to parent]
        D5a8[Multiplicity: 1, 0..star, 1..star on lines]
      D5b(Class Relationships)
        D5b1[Association: uses, both can exist independently]
        D5b2[Aggregation: weak has-a, part exists without whole]
        D5b3[Composition: strong has-a, part needs whole]
        D5b4[Aggregation: open diamond symbol]
        D5b5[Composition: filled diamond symbol]
        D5b6[Dependency: temporary use as method parameter]
    D6(D6 Programming Practice)
      D6a(Errors and Debugging)
        D6a1[Syntax error: violates grammar, caught by compiler]
        D6a2[Logic error: wrong output, found by testing]
        D6a3[Runtime exception: occurs during execution]
        D6a4[NullPointerException: method called on null]
        D6a5[ArrayIndexOutOfBoundsException: bad index]
        D6a6[try catch finally: exception handling]
        D6a7[White-box testing: tester has source code]
        D6a8[Black-box testing: tester knows only inputs and outputs]
        D6a9[Boundary testing: test at limits of valid range]
      D6b(Tracing Algorithms)
        D6b1[Trace table: one column per variable]
        D6b2[One row per step or loop iteration]
        D6b3[Track loop counters and condition results]
        D6b4[Note every assignment and output statement]
        D6b5[For recursion: track the call stack]
        D6b6[Always record final output and return values]
```

---

## Reading the Maps

**How to use these four maps:**

- **Spot gaps** — any leaf node that draws a blank → go back to `IBCS_Paper2_Revision.md` for that sub-topic.
- **Self-quiz** — cover the outer nodes; try to recall them from the topic labels alone.
- **Last-minute sweep** — read every leaf node once before walking into the exam hall.

**Printing (black and white):**

| Step | Action |
|------|--------|
| 1 | Open this file in [mermaid.live](https://mermaid.live) — paste one diagram at a time |
| 2 | Click **Actions → PNG** to download each map as an image |
| 3 | Print each PNG on its own A4 sheet, landscape orientation for best fit |
| 4 | Alternatively, open in Obsidian or VS Code (Mermaid Preview extension) and print directly |

All node labels use plain text only — no special characters that would break Mermaid parsing.

**Editors that render Mermaid natively:**

| Editor | How |
|--------|-----|
| VS Code | Install *Mermaid Preview* extension |
| Obsidian | Built-in — enable in Settings → Core Plugins |
| GitHub / GitLab | Auto-renders in `.md` files in any repo |
| mermaid.live | Paste and preview instantly — best for printing |
| Typora | Built-in rendering |
