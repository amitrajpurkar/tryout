# IB CS SL — Paper 1 Mind Maps (One Per Topic)

> Source: `IBCS_lastminute_revision.md`  
> Each topic has its own diagram for readability. Open in VS Code (Mermaid Preview), Obsidian, Typora, or GitHub to render.

---

## Topic 1 — System Fundamentals

```mermaid
mindmap
  root((Topic 1
    System
    Fundamentals))

    ST1_1(1.1 Systems in
      Organisations)
      LC[Lifecycle PADIEM
        Plan · Analyse · Design
        Implement · Evaluate · Maintain]
      FS[Feasibility TELOS
        Technical · Economic
        Legal · Operational · Schedule]
      SH[Stakeholders
        users · managers
        clients · developers]
      REQ[Requirements
        Functional = what it does
        Non-functional = how well]
      CS[Changeover Strategies
        Direct = fast high risk
        Parallel = safe expensive
        Pilot = one location first
        Phased = module by module]
      LEG[Legacy Systems
        hard to maintain
        security risks
        costly to replace]

    ST1_2(1.2 System Design)
      DFD[DFD Symbols
        Rectangle = external entity
        Circle = process
        Open rect = data store
        Arrow = data flow]
      VAL[Validation vs Verification
        Validation = reasonable range
        Verification = entered correctly]
      VTYPE[Validation Types
        Range · Type · Presence
        Length · Format · Check digit]
      ERR[Data Entry Errors
        Transcription = mistyped
        Transposition = chars swapped]

    ST1_3(1.3 Human Interaction)
      USAB[Usability
        learnability · efficiency
        memorability · satisfaction]
      ACC[Accessibility
        screen readers
        keyboard navigation
        high contrast modes]
      DOC[User Documentation
        manuals · FAQs
        tooltips · tutorials · wizards]
      TRN[Training Methods
        Self-instruction e-learning
        Formal classroom
        On-the-job mentoring]

    ST1_4(1.4 Types of Systems)
      TPS[TPS
        routine daily transactions
        ATM · POS terminal]
      MIS[MIS
        reports for managers
        sales · inventory dashboards]
      DSS[DSS
        complex decisions
        what-if analysis]
      EXP[Expert System
        Knowledge base = facts and rules
        Inference engine = applies rules
        User interface · Explanation facility]
      PROC[Processing Types
        Real-time = immediate response
        Batch = scheduled bulk runs
        Online = always available]
```

---

## Topic 2 — Computer Organisation

```mermaid
mindmap
  root((Topic 2
    Computer
    Organisation))

    ST2_1(2.1 CPU Architecture)
      VON[Von Neumann
        single shared memory
        instructions processed sequentially]
      CPU[CPU Components]
        ALU[ALU
          arithmetic and logic
          AND OR NOT comparisons]
        CU[Control Unit
          fetch · decode · coordinate]
        REGS[Registers
          MAR = memory address
          MDR = memory data
          PC = next instruction
          IR = current instruction
          ACC = ALU result]
        CACHE[Cache
          L1 L2 L3 levels
          fast · between CPU and RAM]
      FEC[Fetch-Execute Cycle
        Fetch = PC to MAR to MDR to IR
        Decode = CU reads IR
        Execute = ALU or CU acts
        PC auto-incremented]
      PERF[Performance Factors
        Clock speed GHz
        Number of cores
        Cache size
        Bus width · Word size]

    ST2_2(2.2 Memory)
      RAM[RAM
        volatile · lost on power off
        read-write · active programs]
      ROM[ROM
        non-volatile · survives power off
        read-only · firmware BIOS]
      HIER[Memory Hierarchy
        Registers fastest smallest
        Cache
        RAM
        Secondary Storage slowest largest]
      VIRT[Virtual Memory
        HDD used as RAM overflow
        involves paging
        much slower than RAM]

    ST2_3(2.3 Secondary Storage)
      HDD[HDD Magnetic
        spinning platters + read-write head
        cheap · large capacity · slow]
      SSD[SSD Flash
        NAND flash · no moving parts
        fast · durable · expensive per GB]
      OPT[Optical
        CD DVD Blu-ray
        laser reads pits and lands
        portable · fragile · limited size]

    ST2_4(2.4 Operating Systems)
      FUNC[OS Functions
        Memory management
        Process scheduling
        File management
        Device drivers
        Security and access control]
      OTYPES[OS Types
        Single-user desktop
        Multi-user server
        RTOS guaranteed response time
        Embedded minimal dedicated]
      DEAD[Deadlock
        two processes wait for each other
        neither can proceed]
      SPOOL[Spooling
        jobs queued for slow device
        CPU freed to do other work
        e.g. print queue]

    ST2_5(2.5 Software)
      STYPE[Software Types
        System = manages hardware
        Application = for end users
        Utility = maintains system]
      COMP[Compiled vs Interpreted
        Compiled = all at once · faster
        Interpreted = line by line · portable]
      OPEN[Open Source vs Proprietary
        Open = free visible customisable
        Proprietary = paid hidden vendor support]

    ST2_6(2.6 Data Representation)
      NUM[Number Systems
        Binary base 2
        Denary base 10
        Hex base 16 using A-F]
      TWOS[Twos Complement
        invert all bits then add 1
        MSB = 1 means negative]
      UNITS[Storage Units
        8 bits = 1 byte
        1024 bytes = 1 KB
        1024 KB = 1 MB · 1024 MB = 1 GB]
      COL[Colour
        RGB = 8 bits per channel
        16-bit = 65536 colours
        24-bit = 16.7M true colour
        32-bit = colour plus alpha]
      TEXT[Text Encoding
        ASCII = 7-bit 128 characters
        Unicode = all world languages
        UTF-8 UTF-16 UTF-32]
      AV[Sound and Images
        Sound = sample rate x bit depth
        Bitmap = pixel by pixel raster
        Vector = mathematical paths scales]
```

---

## Topic 3 — Networks

```mermaid
mindmap
  root((Topic 3
    Networks))

    ST3_1(3.1 Types and
      Topologies)
      NTYPE[Network Types
        LAN = local building or campus
        WAN = wide geographic area
        WLAN = wireless LAN via Wi-Fi
        PAN = personal Bluetooth]
      BUS[Bus Topology
        all share one cable
        simple and cheap
        cable failure = whole network down]
      STAR[Star Topology
        all connect to central switch
        most common in practice
        switch = single point of failure]
      RING[Ring Topology
        devices in a circle
        one break disrupts all]
      MESH[Mesh Topology
        every device to every other
        highly redundant · very expensive]

    ST3_2(3.2 Network Hardware)
      ROUTER[Router
        directs data between networks
        uses IP addresses
        connects LAN to internet]
      SWITCH[Switch
        connects devices within LAN
        uses MAC addresses
        sends only to intended device]
      HUB[Hub
        sends to all devices
        obsolete · inefficient]
      WAP[Wireless Access Point
        connects wireless to wired network
        IEEE 802.11 Wi-Fi standard]
      NIC[NIC
        hardware network interface
        unique MAC address per device]
      MODEM[Modem
        converts digital to analogue
        needed for DSL cable internet]

    ST3_3(3.3 Protocols and
      Transmission)
      PROTO[Key Protocols
        IP = routing and addressing
        TCP = reliable ordered delivery
        UDP = fast no guarantee
        HTTP = web pages
        HTTPS = encrypted HTTP
        FTP = file transfer
        SMTP = send email
        DNS = name to IP address
        DHCP = auto assign IP]
      TCPUDP[TCP vs UDP
        TCP = handshake guaranteed ordered
        UDP = connectionless faster
        TCP for web email files
        UDP for streaming gaming DNS]
      PKT[Packet Switching
        data split into packets
        packets travel independently
        reassembled at destination
        efficient and resilient]
      ADDR[Addressing
        IPv4 = 32-bit 4.3B addresses
        IPv6 = 128-bit unlimited
        MAC = 48-bit hardware address]
      BW[Bandwidth vs Latency
        Bandwidth = max data rate bps
        Latency = delay before arrival]

    ST3_4(3.4 Network Security)
      MALWARE[Malware Types
        Virus = attaches to files
        Worm = self-replicates network
        Trojan = disguised backdoor
        Ransomware = encrypt and demand
        Spyware = silent data collection]
      ATTACK[Attack Types
        Phishing = fake emails and sites
        DoS = flood server with requests
        DDoS = botnet coordinated flood
        Man-in-middle = intercept comms
        SQL injection = malicious SQL
        Brute force = try all passwords]
      DEFENCE[Defences
        Firewall = filter traffic by rules
        Encryption = scramble data
        Antivirus = detect and remove
        VPN = encrypted tunnel
        Patching = fix vulnerabilities
        Least privilege access control]
      ENCR[Encryption
        Symmetric = one shared key
        Asymmetric = public plus private key
        HTTPS uses both]
      AUTH[Authentication
        Know = password PIN
        Have = token smart card
        Are = biometrics fingerprint
        MFA = two or more factors]

    ST3_5(3.5 Internet and WWW)
      DIFF[Internet vs WWW
        Internet = global physical network
        WWW = service on internet via HTTP]
      DNS[DNS
        translates domain to IP address
        hierarchical distributed database
        resolver root TLD authoritative]
      LOAD[How a Page Loads
        DNS resolves domain to IP
        HTTP GET sent to server
        server returns HTML CSS JS
        browser parses and renders]
      CLOUD[Cloud Computing
        data and apps on remote servers
        accessible from anywhere
        scalable on demand
        privacy concerns and cost]
```

---

## Topic 4 — Computational Thinking, Problem-Solving & Programming

```mermaid
mindmap
  root((Topic 4
    Computational
    Thinking))

    ST4_1(4.1 to 4.3
      Foundations)
      DECOMP[Decomposition
        break problem into sub-problems
        divide and conquer approach]
      PATT[Pattern Recognition
        find similarities and trends
        reuse existing solutions]
      ABSTR[Abstraction
        remove unnecessary detail
        focus on essentials only
        e.g. maps classes functions]
      LOGIC[Thinking Logically
        conditions and Boolean logic
        AND · OR · NOT]
      AHEAD[Thinking Ahead
        identify inputs and outputs
        define pre-conditions
        plan for edge cases]
      PSEUDO[Pseudocode IB Syntax
        assignment · output · input
        if else end if
        loop from to end loop
        loop while · loop until
        div = integer division
        mod = remainder
        procedure vs function]

    ST4_2(4.4 and 4.5
      Searching and Sorting)
      LINEAR[Linear Search
        check each element one by one
        works on any order of data
        time complexity O of n]
      BINARY[Binary Search
        halves search space each step
        pre-condition = data must be sorted
        time complexity O of log n]
      SCOMP[Search Comparison
        linear = no sort needed slower
        binary = sorted required faster]
      BUBBLE[Bubble Sort
        compare and swap adjacent pairs
        largest bubbles to end each pass
        O of n squared · n-1 passes]
      SELECT[Selection Sort
        find minimum swap to front
        O of n squared]
      TRACE[Bubble Trace 5 3 8 1
        Pass 1 = 3 5 1 8
        Pass 2 = 3 1 5 8
        Pass 3 = 1 3 5 8 sorted]

    ST4_3(4.6 and 4.7
      Sub-programs and Arrays)
      PROC[Procedure
        named block of code
        no return value]
      FUNC[Function
        named block of code
        returns a value]
      WHY[Why Sub-programs
        code reuse · modular
        easier to debug and test
        team collaboration]
      SCOPE[Scope
        local = inside sub-program only
        global = everywhere avoid it]
      ARR[Arrays
        fixed-size · same type · indexed
        find max · sum · average · count]
      ARR2D[2D Arrays
        grid accessed by row and col
        nested loops to traverse]

    ST4_4(4.8 OOP)
      CORE[Core Terms
        Class = blueprint template
        Object = instance of class
        Attribute = data property
        Method = behaviour function
        Constructor = initialises object]
      ENCAP[Encapsulation
        bundle data and methods
        hide internal state
        public private protected]
      INHER[Inheritance
        subclass from superclass
        acquires attributes and methods
        promotes code reuse]
      POLY[Polymorphism
        same method name
        different behaviour per class]
      ABST[Abstraction
        hide complexity
        expose only necessary interface]
      UML[UML Class Diagram
        plus = public · minus = private
        hollow arrow = inheritance
        child points to parent]

    ST4_5(4.9 to 4.12
      Data Structures)
      RECUR[Recursion
        Base case = stops recursion
        Recursive case = calls itself
        must always reach base case
        call stack · risk of overflow]
      FACT[Factorial Example
        factorial 0 = 1 base case
        factorial n = n x factorial n-1]
      STACK[Stack LIFO
        push = add to top
        pop = remove from top
        uses = undo · function calls]
      QUEUE[Queue FIFO
        enqueue = add to back
        dequeue = remove from front
        uses = print spool · scheduling]
      LL[Linked List
        node = data plus pointer to next
        dynamic size vs fixed array
        fast insert slow random access]
      BST[Binary Search Tree
        left child less than parent
        right child greater than parent
        O log n search on balanced tree]
      TRAV[Tree Traversals
        In-order = Left Root Right = sorted
        Pre-order = Root Left Right = copy
        Post-order = Left Right Root = delete]
```

---

## Reading the Maps

Each diagram above covers one Paper 1 topic in full. Nodes use these shapes:

- **`(( ))`** — topic root (circle)
- **`( )`** — sub-topic heading (rounded rectangle)
- **`[ ]`** — concept/fact node (rectangle)

| Diagram | Topic | Sub-topics covered |
|---|---|---|
| **Map 1** | System Fundamentals | 1.1 – 1.4 |
| **Map 2** | Computer Organisation | 2.1 – 2.6 |
| **Map 3** | Networks | 3.1 – 3.5 |
| **Map 4** | Computational Thinking | 4.1 – 4.12 |

> **Rendering:** VS Code with *Mermaid Preview* extension · Obsidian (native) · Typora · GitHub markdown preview · The HTML file (`IBCS_Paper1_Revision.html`) renders all four maps via Mermaid.js in any browser.
