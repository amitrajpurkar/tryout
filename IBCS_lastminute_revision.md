# IB Computer Science SL — Last Minute Revision
### Paper 1 · Topics 1–4

> **Paper 1:** 1h 30min · 45 marks · 40% of final grade  
> Command terms: *State, Define, Identify, Outline, Describe, Explain, Construct, Analyse, Evaluate, Suggest, Justify*

---

# TOPIC 1 — System Fundamentals

---

## 1.1 Systems in Organisations

**Gist:** This sub-topic is about how and why organisations adopt new computer systems — from the moment a need is identified through to maintaining the system after deployment. The key theme is *managing change* responsibly: identifying stakeholders, gathering requirements, and handling the risks of transitioning from an old system to a new one.

**Key line-items:**
- **System lifecycle (PADIEM):** Planning → Analysis → Design → Implementation → Evaluation → Maintenance
- **Feasibility study (TELOS):** Technical · Economic · Legal · Operational · Schedule — determines if a project *should* proceed
- **Stakeholders:** anyone with a stake in the system — users, managers, clients, developers, shareholders; each has different needs and concerns
- **Functional requirements** = *what* the system does (e.g., "user can search a database")
- **Non-functional requirements** = *how well* it performs (speed, security, reliability, usability, portability)
- **Data collection methods** for requirements gathering: interviews, questionnaires, observation, analysing existing documents
- **Changeover strategies:**
  - *Direct* – old system replaced all at once; fast and cheap but high risk
  - *Parallel* – both systems run simultaneously; safe but expensive and labour-intensive
  - *Pilot* – new system trialled in one location first; limits risk but slows rollout
  - *Phased* – system introduced module by module; manageable but slow and may cause compatibility issues
- **Legacy systems** – old systems still in operation; problems: hard to maintain, security vulnerabilities, incompatibility, but replacement is costly
- **Data migration** – moving data from old to new system; risks: format mismatch, data corruption, data loss

**Examples:**
- A hospital switching from paper records to an electronic patient management system would use *parallel changeover* to ensure no patient data is lost during transition
- A school adding an online enrolment module while the rest of the system remains the same = *phased* changeover
- A payroll system calculates salaries every two weeks (batch processing) — a *functional* requirement; it must do this within 2 hours of the pay cycle end — a *non-functional* (performance) requirement

---

## 1.2 System Design Basics

**Gist:** Once requirements are known, the system must be *designed*. This covers the tools used to represent how data flows through a system, how to ensure that data entering the system is correct, and the difference between checking data is reasonable versus checking it was typed correctly.

**Key line-items:**
- **Data Flow Diagram (DFD):** models how data moves through a system
  - Rectangle = external entity (person/system outside)
  - Circle/oval = process (transforms data)
  - Open rectangle = data store (database, file)
  - Arrow = data flow (labelled with what data is moving)
- **Data dictionary** – describes each data item: name, type, length, validation rules, example value
- **Validation** – checking data is *reasonable/within expected range* (automated by the system)
- **Verification** – checking data was *entered correctly* (involves human checking or double-entry)
- **Validation types:**
  - *Range check* – value within min–max (e.g., age 0–120)
  - *Type check* – correct data type (e.g., numbers only in a phone field)
  - *Presence check* – field is not left empty
  - *Length check* – string is the correct length (e.g., password ≥ 8 characters)
  - *Format check* – matches a pattern (e.g., email contains @ and .)
  - *Check digit* – mathematical self-checking number (e.g., ISBN, barcode last digit)
- **Human data entry errors:**
  - *Transcription* – mistyping a value (e.g., typing 5 instead of 6)
  - *Transposition* – swapping characters (e.g., 12 → 21)

**Examples:**
- A form for entering a student's date of birth: *range check* (year between 1900–2026), *format check* (DD/MM/YYYY), *presence check* (field cannot be empty)
- Double-entry of a new password (type it twice) = *verification*, not validation
- A barcode scanner using a check digit = *validation* — the system itself detects if the barcode was misread

---

## 1.3 Human Interaction with the System

**Gist:** A system is only as good as its usability. This sub-topic focuses on *how people interact* with systems — the quality of the interface, how users are trained, and how documentation supports ongoing use. It also covers accessibility: designing systems that work for everyone, including people with disabilities.

**Key line-items:**
- **Usability factors:** learnability, efficiency, memorability, error rate, user satisfaction
- **User documentation types:** user manuals, online help/FAQs, tooltips, tutorials, wizards, quick-start guides
- **Training methods:**
  - *Self-instruction* – manuals, e-learning modules, video tutorials
  - *Formal training* – classroom instruction, workshops
  - *On-the-job* – mentoring, shadowing a colleague
- **Accessibility** – designing for users with disabilities (e.g., screen readers for visually impaired, keyboard-only navigation, high-contrast colour schemes, captioning for audio)
- **Ergonomics** – designing hardware/software to fit human physical use safely and comfortably (e.g., adjustable monitors, keyboard layout)
- **GUI vs CLI:**
  - *GUI* – graphical; icons, mouse; easier for non-technical users
  - *CLI* – text commands; harder to learn; faster and more powerful for experienced users

**Examples:**
- A screen reader converting text to audio = accessibility feature for visually impaired users
- A new employee is shown the system by an experienced colleague for a week = *on-the-job training*
- An online banking system with tooltips explaining each field = *embedded user documentation*

---

## 1.4 Different Types of Systems

**Gist:** Not all computer systems work the same way. This sub-topic classifies systems by *purpose* (TPS, MIS, DSS, Expert Systems) and by *processing type* (real-time, batch, online). Understanding the differences — and when each is appropriate — is a frequent exam focus.

**Key line-items:**
- **Types of information systems:**
  - *TPS (Transaction Processing System)* – handles routine daily transactions; immediate, repetitive (e.g., ATM withdrawals, point-of-sale)
  - *MIS (Management Information System)* – processes raw data into useful reports for managers (e.g., weekly sales summary)
  - *DSS (Decision Support System)* – interactive tools that help with complex, non-routine decisions; often uses models and "what-if" analysis
  - *Expert System* – mimics a human expert using a knowledge base and inference engine (e.g., medical diagnosis, fault-finding)
- **Expert system components:**
  1. *Knowledge base* – facts and IF-THEN rules about the domain
  2. *Inference engine* – applies rules to facts to reach conclusions
  3. *User interface* – allows the user to ask questions
  4. *Explanation facility* – explains *why* a conclusion was reached
- **Processing types:**
  - *Real-time* – processes input immediately and responds at once (e.g., autopilot, ATM, air traffic control); required where delays are dangerous or unacceptable
  - *Batch* – data collected over a period then processed all at once at a scheduled time (e.g., payroll, bank statements, utility bills); no immediate response needed
  - *Online* – continuously available, interactive, but not necessarily instantaneous (e.g., web search, online shopping)

**Examples:**
- An ATM dispenses cash instantly → *real-time* TPS
- A bank generates monthly statements overnight → *batch* processing
- A doctor's diagnosis support tool uses IF symptoms THEN suggest condition rules → *expert system*
- A manager views a dashboard of this month's sales vs last month → *MIS*
- A supermarket forecasting stock orders using historical data and promotions → *DSS*

---

# TOPIC 2 — Computer Organisation

---

## 2.1 Computer Architecture

**Gist:** The CPU is the brain of the computer. This sub-topic explains *what the CPU is made of*, *how it processes instructions* (the fetch-execute cycle), and *what factors make it faster or slower*. Understanding the role of each register and the path data takes through the processor is essential.

**Key line-items:**
- **Von Neumann architecture** – CPU fetches and executes instructions stored in memory; single shared memory for data and instructions; instructions processed sequentially
- **CPU components:**
  - *ALU (Arithmetic Logic Unit)* – performs arithmetic (+, −, ×, ÷) and logical operations (AND, OR, NOT, comparisons)
  - *CU (Control Unit)* – directs and coordinates all CPU activity; fetches, decodes, and controls execution of instructions
  - *MAR (Memory Address Register)* – holds the address in memory that is being accessed
  - *MDR/MBR (Memory Data Register)* – holds data being read from or written to memory
  - *PC (Program Counter)* – holds address of the *next* instruction to fetch; auto-incremented after each fetch
  - *IR (Instruction Register)* – holds the *current* instruction being decoded and executed
  - *Accumulator* – holds intermediate results from ALU operations
  - *Cache* – small, ultra-fast memory between CPU and RAM; stores recently/frequently accessed data to reduce RAM access time
- **Fetch-Execute Cycle (FEC):**
  1. *Fetch* – PC → MAR; memory[MAR] → MDR; MDR → IR; PC incremented
  2. *Decode* – CU interprets the instruction in IR
  3. *Execute* – ALU performs operation, or CU controls data movement
  4. Repeat
- **CPU performance factors:**
  - *Clock speed* (GHz) – cycles per second; more cycles = more instructions processed per second
  - *Number of cores* – each core is an independent processor; more cores = true parallel execution
  - *Cache size* – larger cache reduces frequency of slow RAM accesses
  - *Bus width* – number of bits transferred at once across the bus; wider = more data per transfer
  - *Word size* – bits processed in one CPU operation; larger word = more data per instruction

**Examples:**
- A 3.2 GHz CPU completes 3.2 billion clock cycles per second
- A quad-core processor can run 4 threads simultaneously, useful for video rendering
- When a program accesses the same array repeatedly, cache stores those values to avoid fetching from RAM each time
- PC holds address 1000 → fetched → IR holds "ADD R1, R2" → PC becomes 1001

---

## 2.2 Memory

**Gist:** Computers use different types of memory with different characteristics: speed, volatility, and cost. The *memory hierarchy* explains why multiple types coexist — the fastest memory is smallest and most expensive, while the slowest is cheapest and largest. Knowing what each type is used for and why is key.

**Key line-items:**
- **RAM (Random Access Memory)** – volatile (lost on power off); read/write; holds the OS, running applications, and active data; directly accessible by CPU
- **ROM (Read-Only Memory)** – non-volatile; stores firmware/BIOS; contents set at manufacture; cannot normally be overwritten
- **Memory hierarchy (fastest → slowest, smallest → largest capacity):**
  ```
  Registers → Cache → RAM → Secondary storage (HDD/SSD)
  ```
- **Virtual memory** – section of secondary storage used as overflow RAM when physical RAM is full; much slower than RAM; involves *paging* (swapping pages in/out of RAM)
- **Cache** – stores copies of frequently accessed RAM data; reduces average memory access time; L1/L2/L3 levels (L1 fastest, closest to CPU core)

| Memory | Volatile? | Writable? | Speed | Typical use |
|---|---|---|---|---|
| Register | Yes | Yes | Fastest | Immediate CPU calculations |
| Cache | Yes | Yes | Very fast | Frequently used instructions/data |
| RAM | Yes | Yes | Fast | Active programs and data |
| ROM | No | No | Fast | Firmware/BIOS |
| SSD | No | Yes | Medium | Secondary storage |
| HDD | No | Yes | Slow | Secondary storage, bulk files |

**Examples:**
- When you power off a laptop and lose unsaved work → RAM is volatile
- BIOS (boot instructions) stored in ROM → non-volatile, present even after power loss
- A computer with 8GB RAM running many programs starts using virtual memory → performance slows significantly (disk access instead of RAM)

---

## 2.3 Secondary Storage

**Gist:** Secondary storage holds data *permanently*, even when the computer is off. Different storage technologies offer different trade-offs between speed, capacity, durability, and cost. You need to know the *physics* behind each type and when to recommend one over another.

**Key line-items:**
- **HDD (Hard Disk Drive)** – magnetic storage; spinning platters with read/write head; slow (mechanical movement); cheap per GB; large capacity; susceptible to physical damage
- **SSD (Solid State Drive)** – NAND flash memory (no moving parts); faster than HDD; more expensive per GB; lightweight; durable; silent; used in laptops and phones
- **Optical (CD/DVD/Blu-ray)** – data encoded as pits and lands on reflective disc; read by laser; portable and cheap per disc; fragile (scratches); limited capacity; declining use
- **USB flash drive** – flash memory in portable form; convenient; limited read/write cycles
- **Choosing storage — key considerations:** capacity needed, required access speed, portability, durability, cost per GB, whether access is sequential (tape/optical) or random (SSD/HDD)

**Examples:**
- A smartphone uses flash storage (SSD) → no moving parts, battery-efficient, survives drops
- A data centre backing up petabytes of rarely-accessed data → uses magnetic tape (sequential, cheap per GB)
- A video editor needing fast read/write of large files → uses SSD for the project drive
- Distributing software in the 1990s → CD-ROM; today → USB drive or download

---

## 2.4 Operating Systems

**Gist:** The operating system (OS) is the software layer between the hardware and the user's applications. Without it, applications could not run. The OS *manages all resources* — memory, processes, files, devices — and provides an interface for users and programs to interact with the hardware.

**Key line-items:**
- **OS core functions:**
  - *Memory management* – allocates RAM to processes; prevents one process accessing another's memory
  - *Process management / scheduling* – decides which process runs when; enables multitasking
  - *File management* – creates, reads, writes, deletes, and organises files and directories
  - *Device management* – uses drivers to communicate with hardware (keyboard, printer, etc.)
  - *User interface* – GUI (graphical: windows, icons) or CLI (text commands)
  - *Security and access control* – user authentication, permissions, encryption
- **Types of OS:**
  - *Single-user* – one user at a time (e.g., Windows on a personal PC)
  - *Multi-user* – many users simultaneously via time-sharing (e.g., Linux server)
  - *Real-time OS (RTOS)* – guarantees response within a strict time limit (e.g., aircraft control, medical devices)
  - *Embedded OS* – minimal OS inside a dedicated device (e.g., router, microwave, smart TV)
- **Scheduling** – the OS decides which process gets CPU time (methods: FIFO, round-robin, priority scheduling)
- **Deadlock** – two or more processes each waiting for a resource held by the other; neither can proceed; the system stalls
- **Spooling** – queuing jobs for a slower device (e.g., print queue); CPU sends jobs to the spooler and continues other tasks instead of waiting

**Examples:**
- Printing in the background while editing a document = spooling + OS process scheduling
- Process A holds the scanner, waits for the printer; Process B holds the printer, waits for the scanner → deadlock
- An air traffic control system must respond to pilot input within milliseconds → requires RTOS
- A washing machine controller runs a simple embedded OS with no user interface

---

## 2.5 Software Types

**Gist:** Software is classified by its purpose and by how it runs. Understanding the distinction between system, application, and utility software — and the difference between compiled and interpreted languages — underpins how programs are written, distributed, and run.

**Key line-items:**
- **System software** – manages hardware and provides platform for other software (OS, drivers, firmware)
- **Application software** – used directly by end-users to accomplish tasks (word processor, web browser, game, accounting software)
- **Utility software** – maintains and optimises the system (antivirus, disk defragmenter, backup tool, file compression)
- **Compiled language** – source code translated to machine code all at once *before* running; fast execution; platform-specific; errors found at compile time (e.g., C, C++, Java bytecode)
- **Interpreted language** – source code translated line-by-line *at runtime*; slower but portable; errors found at runtime (e.g., Python, JavaScript)
- **Open source vs proprietary:**

| | Open Source | Proprietary |
|---|---|---|
| Source code | Publicly available | Hidden |
| Cost | Usually free | Usually paid |
| Customisable | Yes | No |
| Support | Community-based | Vendor-provided |
| Examples | Linux, Firefox, Python | Windows, MS Office, macOS |

**Examples:**
- Microsoft Word = application software; Windows Defender (antivirus) = utility software; Windows OS = system software
- Python scripts run in an interpreter → easy to test interactively but slower than compiled C++
- Android is open-source (AOSP); iOS is proprietary
- A school choosing free LibreOffice instead of Microsoft Office to save licensing costs → open source advantage

---

## 2.6 Binary and Data Representation

**Gist:** All data inside a computer — numbers, text, images, audio, video — is stored and processed as binary (1s and 0s). This sub-topic covers *how* different types of data are encoded into binary and the trade-offs (quality vs file size) involved. Number base conversions and two's complement are regular Paper 1 calculation questions.

**Key line-items:**
- **Number systems:**

| System | Base | Digits | Used for |
|---|---|---|---|
| Binary | 2 | 0, 1 | All internal computer data |
| Denary | 10 | 0–9 | Human-readable numbers |
| Hexadecimal | 16 | 0–9, A–F | Compact binary representation (colours, memory addresses) |

- **8-bit positional values:** 128 · 64 · 32 · 16 · 8 · 4 · 2 · 1
- **Binary → Hex:** group bits in 4s from right; convert each group (A=10, B=11, C=12, D=13, E=14, F=15)
  - `1011 0010` → `B2`
- **Two's complement (negative numbers):** invert all bits, then add 1; MSB=1 means negative
  - −5 in 8-bit: 00000101 → invert → 11111010 → +1 → **11111011**
- **Storage units:** 1 byte = 8 bits · 1 KB = 1024 B · 1 MB = 1024 KB · 1 GB = 1024 MB · 1 TB = 1024 GB
- **Representing numbers:**
  - n bits → 2ⁿ possible values; maximum unsigned value = 2ⁿ − 1
- **Colour representation:**
  - *RGB* – each channel (R, G, B) = 8 bits (0–255)
  - *16-bit colour* → 2¹⁶ = 65,536 colours
  - *24-bit (True colour)* → 2²⁴ = 16,777,216 colours
  - *32-bit* = 24-bit colour + 8-bit alpha (transparency channel)
  - More bits per pixel → higher quality → larger file size
- **Text encoding:**
  - *ASCII* – 7-bit; 128 characters; English letters, digits, symbols only
  - *Unicode (UTF-8/16/32)* – up to 32 bits; covers all world languages, emoji, special symbols; backwards-compatible with ASCII
- **Sound (audio) representation:**
  - *Sampling* – measuring amplitude of sound wave at regular time intervals
  - *Sample rate* (Hz) – samples per second; higher = better quality, larger file (CD audio = 44,100 Hz)
  - *Bit depth* – bits per sample; more bits = more precise amplitude (CD audio = 16-bit)
  - File size = sample rate × bit depth × duration (sec) × channels ÷ 8 = **bytes**
- **Image representation:**
  - *Pixel* – smallest addressable element of an image; each stores a colour value
  - *Resolution* – total pixel dimensions (e.g., 1920 × 1080)
  - *Bitmap/raster* (BMP, JPG, PNG) – stored pixel by pixel; degrades when enlarged; file size = width × height × bit depth ÷ 8
  - *Vector* (SVG) – stored as mathematical paths; scales perfectly; used for logos and diagrams

**Examples:**
- A 16-bit integer for colour → 2¹⁶ = 65,536 different colours (classic IB exam question)
- 32-bit vs 16-bit colour: advantage = more colours, smoother gradients; disadvantage = larger file size / more memory required
- `math.floor(1234.5678 * 100) / 100` = `math.floor(123456.78) / 100` = `123400 / 100` = **1234.0** (IB sample question)
- A 3-minute stereo audio clip at 44,100 Hz and 16-bit depth: 44100 × 16 × 180 × 2 ÷ 8 = ~31.75 MB uncompressed
- "Hello" in ASCII: H=72, e=101, l=108, l=108, o=111

---

# TOPIC 3 — Networks

---

## 3.1 Network Types and Topologies

**Gist:** A network connects computers to share data and resources. The *type* of network depends on geographic scale and ownership; the *topology* describes the physical or logical layout of connections. Choosing the right topology involves balancing cost, reliability, and performance.

**Key line-items:**
- **Network types:**
  - *LAN (Local Area Network)* – single building or campus; privately owned; high speed (Gbps over Ethernet); e.g., school network
  - *WAN (Wide Area Network)* – large geographic area; uses public/leased links; lower speed than LAN; e.g., the internet
  - *WLAN (Wireless LAN)* – LAN using Wi-Fi (IEEE 802.11 standard); no cables; susceptible to interference
  - *PAN (Personal Area Network)* – very short range; personal devices; e.g., Bluetooth connecting phone to earbuds
- **Network topologies:**

| Topology | Layout | ✓ Key advantage | ✗ Key disadvantage |
|---|---|---|---|
| *Bus* | All on one cable | Simple, cheap | Cable failure brings down whole network |
| *Star* | All connect to central switch | One device failure isolated | Switch is single point of failure |
| *Ring* | Devices in a circle | Predictable performance (token passing) | One break disrupts entire ring |
| *Mesh* | Every device to every other | Highly redundant and reliable | Very expensive, complex cabling |

- In practice, most networks use **star topology** (Ethernet switches in offices/schools)

**Examples:**
- A school building with 200 computers all connected to a central switch → LAN with star topology
- The internet connecting millions of networks across continents → WAN
- A student's phone connected to Bluetooth headphones → PAN
- A hospital connecting buildings across a city using leased fibre lines → WAN

---

## 3.2 Network Hardware

**Gist:** Specific hardware devices are needed to build and operate networks. Each device has a specific role — some direct traffic, some convert signals, some enable wireless access. Knowing which device does what (especially router vs switch vs hub) is frequently tested.

**Key line-items:**
- **Router** – directs data *between* different networks using IP addresses; connects a LAN to the internet; uses routing tables to find best path
- **Switch** – connects devices *within* a LAN; sends data only to the intended device using MAC addresses (more efficient than hub)
- **Hub** – sends incoming data to *all* connected devices regardless of destination; creates collisions; largely obsolete, replaced by switches
- **Wireless Access Point (WAP)** – allows wireless devices to connect to a wired network via Wi-Fi
- **NIC (Network Interface Card)** – hardware in each device that provides the physical connection to a network; has a unique MAC address
- **Modem** – converts between digital data (computer) and analogue signals (phone line / cable); needed for DSL and cable internet connections
- **Firewall** – hardware or software that monitors and filters network traffic based on security rules; sits between LAN and internet

**Examples:**
- Home network: modem (ISP signal → digital) → router (assigns IP addresses, connects LAN to internet) → switch or WAP → devices
- A switch in a school network only sends a student's file to the teacher's computer, not all computers → efficient
- A hub in an old network sends every packet to every port → all devices process all traffic → slow and insecure

---

## 3.3 Protocols and Data Transmission

**Gist:** For devices to communicate reliably, they must follow agreed-upon rules called *protocols*. This sub-topic covers the major protocols of the internet, how data is broken into packets and routed across networks, and the difference between connection-based (TCP) and connectionless (UDP) communication.

**Key line-items:**
- **Protocol** – agreed set of rules governing communication between devices
- **Key protocols:**

| Protocol | Purpose |
|---|---|
| IP | Addressing and routing of packets across networks |
| TCP | Reliable, ordered, error-checked delivery; connection-based |
| UDP | Fast, connectionless; no delivery guarantee |
| HTTP | Transferring web pages |
| HTTPS | HTTP encrypted with SSL/TLS |
| FTP | File transfer between computers |
| SMTP | Sending email |
| POP3 / IMAP | Receiving/accessing email |
| DNS | Translates domain names → IP addresses |
| DHCP | Automatically assigns IP addresses to devices on a network |

- **TCP vs UDP:**
  - *TCP* – establishes connection (3-way handshake); ensures packets arrive in order; error-checks; used for web, email, file transfer
  - *UDP* – sends packets without establishing connection; no acknowledgement; faster; used for video/audio streaming, DNS, online gaming

- **Packet switching:**
  - Data broken into small *packets*; each contains a header (source/destination IP, packet number, TTL) + payload + trailer (checksum)
  - Packets may travel different routes through the network
  - Reassembled in correct order at destination
  - Advantage: efficient use of network links; resilient (packets rerouted if link fails)

- **IP addresses:**
  - *IPv4* – 32-bit dotted decimal (e.g., 192.168.0.1); ~4.3 billion addresses; running out
  - *IPv6* – 128-bit hex (e.g., 2001:0db8::1); essentially unlimited; created to replace IPv4
  - *MAC address* – unique 48-bit hardware address of a NIC (e.g., 00:1A:2B:3C:4D:5E); used within a LAN (switches); IP used between networks (routers)

- **Bandwidth** – maximum data transfer rate (bps); higher = more data per second  
- **Latency** – delay before data begins to arrive; affected by distance, congestion, routing

- **Transmission media:**
  - *Twisted pair copper* – common, cheap; used in Ethernet; limited distance
  - *Fibre optic* – light pulses; very high speed; immune to electromagnetic interference; expensive
  - *Wireless* – radio waves (Wi-Fi), microwave (point-to-point), satellite (high latency)

**Examples:**
- Streaming a Netflix film → UDP (some lost packets acceptable; low latency more important than perfect delivery)
- Downloading a software installer → TCP (every byte must arrive correctly)
- Typing google.com → DNS resolves it to 142.250.x.x → browser sends HTTP GET to that IP
- A packet from London to New York may travel: London → Paris → New York via Atlantic cable → destination

---

## 3.4 Network Security

**Gist:** As networks connect everything, they also expose systems to threats. This sub-topic covers the main *types of attacks*, the *security measures* that counter them, and the principles of encryption and authentication. Every organisation with a network must deal with these issues — and IB Paper 1 regularly asks about them.

**Key line-items:**
- **Malware types:**
  - *Virus* – attaches to legitimate files; spreads when the file is shared; can damage or delete data
  - *Worm* – self-replicates across networks *without user action*; consumes bandwidth
  - *Trojan* – disguised as legitimate software; secretly installs a backdoor for attackers
  - *Ransomware* – encrypts victim's files; demands payment (cryptocurrency) for the decryption key
  - *Spyware* – secretly monitors activity; collects passwords, keystrokes, personal data

- **Attack types:**
  - *Phishing* – fraudulent emails or fake websites that trick users into revealing passwords or financial details
  - *DoS (Denial of Service)* – floods a server with requests, making it unavailable to legitimate users
  - *DDoS* – DoS using a botnet (many compromised devices)
  - *Man-in-the-middle* – attacker intercepts and possibly alters communication between two parties
  - *SQL injection* – malicious SQL code inserted into a web form input to manipulate or extract from a database
  - *Brute force* – systematically tries every possible password until one works

- **Security measures:**

| Measure | How it helps |
|---|---|
| Firewall | Filters incoming/outgoing traffic based on rules; blocks suspicious connections |
| Encryption | Scrambles data; only authorised parties with the key can read it |
| Antivirus | Scans for and removes known malware signatures |
| VPN | Creates encrypted tunnel over public internet; secures remote access |
| Strong passwords / MFA | Reduces risk of unauthorised access |
| Software updates / patching | Fixes known vulnerabilities exploited by attackers |
| Access control (least privilege) | Users only access what is needed for their role |

- **Encryption types:**
  - *Symmetric* – one shared key for both encryption and decryption; fast; key distribution is the challenge
  - *Asymmetric (public key)* – public key encrypts; private key decrypts; used in HTTPS/TLS; no need to share the private key

- **Authentication factors:**
  - Something you *know* – password, PIN
  - Something you *have* – phone/token/smart card
  - Something you *are* – fingerprint, face, iris (biometrics)
  - *MFA* – requires two or more factors; significantly harder to compromise

**Examples:**
- An email appearing to be from a bank asking you to "verify your details" → phishing
- WannaCry (2017): ransomware that encrypted hospitals' files globally, demanding Bitcoin → disrupted NHS services
- HTTPS on websites uses asymmetric encryption to establish a session, then switches to symmetric for speed
- A company requiring a password + a text message code to log in = two-factor authentication (2FA)
- SQL injection: entering `' OR '1'='1` in a login form to bypass authentication by making the SQL query always true

---

## 3.5 The Internet and World Wide Web

**Gist:** Students often confuse the internet with the web — they are not the same. The internet is the global physical *infrastructure*; the web is a *service* running on top of it. This section covers how web pages are found and loaded, what DNS does, and the growing role of cloud computing.

**Key line-items:**
- **Internet** – the global network of interconnected physical networks (routers, cables, satellites)
- **World Wide Web (WWW)** – a collection of web pages and resources accessed via HTTP/HTTPS; just one of many services on the internet (others: email, FTP, VoIP)
- **URL structure:** `https://www.example.com/page?query=value` — protocol · domain · path · query
- **DNS (Domain Name System):**
  - Hierarchical, distributed database that maps domain names → IP addresses
  - Without DNS, users would need to memorise IP addresses
  - Lookup chain: browser cache → OS cache → DNS resolver → root server → TLD server → authoritative server → IP returned
- **How a web page loads (simplified):**
  1. User enters URL
  2. DNS resolves domain to IP address
  3. Browser sends HTTP GET request to web server at that IP
  4. Server returns HTML, CSS, JavaScript files
  5. Browser parses and renders the page
- **Web technologies:**
  - *HTML* – structure and content of a page
  - *CSS* – styling and layout
  - *JavaScript* – interactivity and dynamic content (runs in browser)
  - *Server-side scripting* (PHP, Python) – dynamic content generated on the server before sending HTML
- **Cloud computing** – storing data and running applications on remote servers accessed via the internet

| ✓ Cloud advantages | ✗ Cloud disadvantages |
|---|---|
| Access from any device/location | Requires internet connection |
| Scalable on demand | Privacy and data sovereignty concerns |
| No local hardware to maintain | Ongoing subscription costs |
| Automatic backups | Vendor lock-in; service outages |

**Examples:**
- Typing `bbc.co.uk` → DNS returns 151.101.x.x → browser fetches HTML from that server → page renders
- Google Docs = cloud application; data stored on Google servers, not locally
- Netflix CDN (Content Delivery Network) caches video on servers near users to reduce latency
- An organisation storing backups on AWS S3 = cloud storage

---

# TOPIC 4 — Computational Thinking, Problem-Solving and Programming

---

## 4.1 General Principles of Computational Thinking

**Gist:** Computational thinking is the *foundation* of problem-solving in computer science — it is how programmers think before writing a single line of code. The four pillars (decomposition, pattern recognition, abstraction, algorithm design) are a framework for approaching *any* complex problem, not just programming ones.

**Key line-items:**
- **Decomposition** – breaking a large, complex problem into smaller, more manageable sub-problems that can be solved independently; divide and conquer
- **Pattern recognition** – identifying similarities, trends, or repeated structures within or across problems; allows reuse of existing solutions
- **Abstraction** – stripping away irrelevant detail; focusing only on what matters for the current problem; creating simplified models
- **Algorithm design** – creating a precise, step-by-step, unambiguous set of instructions that solves the problem; can be expressed as pseudocode, flowchart, or natural language
- **These four steps are typically sequential:** decompose the problem → look for patterns → abstract away detail → design the algorithm

**Examples:**
- Building a school management system: *decompose* into student records, timetabling, attendance, reports; each module solved separately
- Sorting algorithms all share the *pattern* of comparing and rearranging elements → same thinking applies to bubble, selection, insertion sort
- A map is an *abstraction* of the real world — roads shown, building interiors removed
- Writing pseudocode before coding = algorithm design before implementation

---

## 4.2 Thinking Procedurally, Logically and Ahead

**Gist:** These three modes of thinking describe how a programmer approaches *designing* a solution. Procedural thinking is about sequence and order. Logical thinking is about conditions and decisions. Thinking ahead is about planning for inputs, outputs, and failure cases *before* writing code.

**Key line-items:**
- **Thinking procedurally:** identifying the correct *sequence* of steps; determining sub-tasks and their order; assigning tasks to appropriate components
- **Thinking logically:** identifying conditions that affect program flow; writing correct Boolean expressions; understanding AND, OR, NOT; tracing decision trees
- **Thinking ahead (concurrency / pre-conditions):**
  - Identifying inputs required and outputs produced
  - Defining *pre-conditions* – assumptions that must be true before an algorithm runs (e.g., "the list must not be empty", "N must be a positive integer")
  - Planning for edge cases (empty input, maximum values, invalid data)
  - Considering what happens if something goes wrong (error handling)
- **Boolean logic operators:**
  - AND – true only if *both* conditions are true
  - OR – true if *at least one* condition is true
  - NOT – inverts a Boolean value

**Examples:**
- Pre-condition for binary search: "the array must be sorted in ascending order"
- Pre-condition for factorial(N): "N must be a non-negative integer"
- Edge cases for a search algorithm: what if the array is empty? What if the target appears multiple times?
- `if age >= 18 AND hasID = true then allow_entry` → logical thinking with AND

---

## 4.3 Pseudocode and IB Syntax

**Gist:** IB Paper 1 uses a specific pseudocode style. You must be able to *read*, *trace*, and *write* pseudocode correctly. The syntax is not identical to any real programming language, so learning the IB conventions exactly is important.

**Key line-items:**

```
// Assignment
X = 5
NAME = "Alice"

// Output / Input
output X
output "Hello " + NAME
input AGE

// Conditional (if-else)
if score >= 50 then
    output "Pass"
else if score >= 40 then
    output "Near miss"
else
    output "Fail"
end if

// Count-controlled loop (inclusive on both ends)
loop I from 1 to 10
    output I
end loop

// While loop (pre-test)
loop while count < 5
    count = count + 1
end loop

// Until loop (post-test — runs at least once)
loop until found = true
    // search body
end loop

// Arrays (commonly 0-indexed in IB examples)
SCORES[0] = 85
output SCORES[2]

// 2D arrays
GRID[0][1] = 42

// Procedure (no return value)
procedure displayName(NAME)
    output "Name: " + NAME
end procedure

// Function (returns a value)
function cube(N)
    return N * N * N
end function

output cube(3)    // outputs 27
```

**Important IB pseudocode notes:**
- `div` = integer division (e.g., `7 div 2` = 3)
- `mod` = remainder (e.g., `7 mod 2` = 1)
- String operations: `LEN(S)`, `SUBSTR(S, start, length)`, `CONCAT(S1, S2)`
- Arrays are typically accessed with square brackets; check question for 0 or 1-based indexing

**Examples:**
- IB sample: `math.floor((n * 100) / 100)` with n = 1234.5678 → `math.floor(123456.78 / 100)` → `math.floor(1234.5678)` → **1234.0**
- Reading a trace table: follow variable values step by step through each iteration

---

## 4.4 Searching Algorithms

**Gist:** Searching is one of the most fundamental operations in computing. The two algorithms you must know are *linear search* (works on any data) and *binary search* (faster, but requires sorted data). You need to be able to write both in pseudocode, trace them on an example, and compare their efficiency.

**Key line-items:**
- **Linear search:**
  - Checks each element one at a time, from first to last
  - Works on *unsorted or sorted* data
  - Time complexity: **O(n)** — in worst case, checks all n elements
  
```
found = false
loop I from 0 to N-1
    if ARRAY[I] = target then
        output I
        found = true
    end if
end loop
if found = false then
    output "Not found"
end if
```

- **Binary search:**
  - Compares target to *middle* element; discards half the remaining elements each step
  - Only works on *sorted* data — this is a pre-condition
  - Time complexity: **O(log n)** — far fewer comparisons than linear for large arrays

```
low = 0
high = N - 1
found = false
loop while low <= high and found = false
    mid = (low + high) div 2
    if ARRAY[mid] = target then
        output mid
        found = true
    else if ARRAY[mid] < target then
        low = mid + 1
    else
        high = mid - 1
    end if
end loop
```

- **Comparison:**

| | Linear Search | Binary Search |
|---|---|---|
| Pre-condition | None | Array must be sorted |
| Time complexity | O(n) | O(log n) |
| Best for | Small / unsorted data | Large sorted datasets |

**Examples:**
- Binary search on [2, 5, 8, 12, 16, 23, 38, 56] for target 23:
  - mid = index 3 → value 12; 23 > 12 → low = 4
  - mid = index 5 → value 23; found! → 3 comparisons total
- Linear search on same array would check 2, 5, 8, 12, 16, 23 → 6 comparisons

---

## 4.5 Sorting Algorithms

**Gist:** Sorting is a prerequisite for binary search and is fundamental to organising data. The IB requires you to know *bubble sort* in detail (write it, trace it, evaluate it) and understand *selection sort* at a conceptual level. Both are O(n²) — inefficient for large data but simple to implement and understand.

**Key line-items:**
- **Bubble sort:**
  - Repeatedly compare adjacent elements; swap if out of order
  - After each *pass*, the largest unsorted element is in its correct position at the end
  - Requires n−1 passes for n elements; inner loop shrinks with each pass
  - Time complexity: **O(n²)**

```
loop I from 0 to N-2
    loop J from 0 to N-2-I
        if ARRAY[J] > ARRAY[J+1] then
            temp = ARRAY[J]
            ARRAY[J] = ARRAY[J+1]
            ARRAY[J+1] = temp
        end if
    end loop
end loop
```

- **Selection sort:**
  - Find the *minimum* element in the unsorted portion
  - Swap it into the next position at the front
  - Repeat; unsorted portion shrinks by one each pass
  - Time complexity: **O(n²)** — similar to bubble sort but fewer swaps

- **Evaluating sorts:**
  - Both are fine for small datasets (< a few hundred elements)
  - For large datasets, use faster algorithms like *merge sort* (O(n log n)) — not required in detail at SL

**Examples:**
- Trace bubble sort on [5, 3, 8, 1]:
  - Pass 1: 5↔3 → [3,5,8,1] · 5<8 · 8↔1 → **[3,5,1,8]**
  - Pass 2: 3<5 · 5↔1 → **[3,1,5,8]**
  - Pass 3: 3↔1 → **[1,3,5,8]** ✓

---

## 4.6 Sub-programs

**Gist:** Sub-programs (procedures and functions) are the building blocks of modular programming. They allow you to write a block of code once and reuse it many times. This is one of the key principles of good software design — and every IB paper includes questions about them.

**Key line-items:**
- **Procedure** – a named block of code that performs a task; *does not return* a value; called by name
- **Function** – a named block of code that performs a task and *returns* a value to the caller
- **Parameters** – values passed *into* a sub-program when it is called
- **Return value** – value sent *back* from a function to the calling code
- **Why use sub-programs?**
  - *Code reuse* – write once, call many times; reduces duplication
  - *Modularity* – break large programs into smaller, manageable pieces
  - *Easier debugging* – test each sub-program independently
  - *Readability* – named sub-programs make code self-documenting
  - *Teamwork* – different programmers can work on different sub-programs simultaneously
- **Scope:**
  - *Local variable* – declared inside a sub-program; only accessible within it; created when called, destroyed when done
  - *Global variable* – declared outside all sub-programs; accessible everywhere; generally avoided because it makes debugging harder

**Examples:**
- `function calculateTax(income)` returns `income * 0.2` — used for every employee's salary calculation → code reuse
- `procedure printReceipt(items, total)` displays the receipt — no value needs to be returned
- A local variable `count` inside a loop sub-program → each call starts fresh; doesn't interfere with the rest of the program

---

## 4.7 Arrays and 2D Arrays

**Gist:** Arrays are the most fundamental data structure — an ordered, fixed-size collection accessed by index. You must be able to write code that processes arrays (find min/max, sum, average, count, search) and work with 2D arrays (grids, tables). Trace questions on arrays appear frequently.

**Key line-items:**
- **Array** – fixed-size collection of elements of the *same type*; accessed by integer index (0-based in IB unless stated otherwise)
- **Key array operations:**

```
// Find maximum
max = ARRAY[0]
loop I from 1 to N-1
    if ARRAY[I] > max then
        max = ARRAY[I]
    end if
end loop

// Sum and average
sum = 0
loop I from 0 to N-1
    sum = sum + ARRAY[I]
end loop
average = sum / N

// Count occurrences
count = 0
loop I from 0 to N-1
    if ARRAY[I] = target then
        count = count + 1
    end if
end loop
```

- **2D array** – a grid/table; accessed by `ARRAY[row][col]`

```
// Traverse entire 2D array
loop R from 0 to ROWS-1
    loop C from 0 to COLS-1
        output GRID[R][C]
    end loop
end loop
```

- **Array limitations:** fixed size at creation; cannot grow/shrink; use linked lists or dynamic structures for flexible size

**Examples:**
- A 5-element array SCORES = [85, 72, 91, 60, 78]; find average → sum=386, average=77.2
- A 3×3 GRID represents a tic-tac-toe board; `GRID[1][1]` is the centre cell
- A class list of 30 student names → `NAMES[0]` to `NAMES[29]`

---

## 4.8 Object-Oriented Programming (OOP)

**Gist:** OOP is a programming paradigm that organises code around *objects* — entities that combine data (attributes) and behaviour (methods). The four pillars of OOP (encapsulation, inheritance, polymorphism, abstraction) allow large systems to be built in a modular, reusable, and maintainable way. OOP questions in Paper 1 often involve reading/drawing UML class diagrams.

**Key line-items:**
- **Class** – a blueprint/template that defines the attributes and methods of a type of object
- **Object** – a specific *instance* of a class (e.g., the class is `Dog`; an object is `myDog`)
- **Attribute** – a variable belonging to an object, storing its state (e.g., `name`, `age`, `colour`)
- **Method** – a function belonging to an object, defining its behaviour (e.g., `bark()`, `eat()`)
- **Constructor** – a special method called automatically when an object is created; initialises its attributes

**Four pillars:**

| Pillar | Meaning | Key benefit |
|---|---|---|
| *Encapsulation* | Bundling data + methods; hiding internal state with access modifiers | Protects data; reduces dependencies |
| *Inheritance* | Subclass inherits attributes/methods from superclass | Code reuse; avoids duplication |
| *Polymorphism* | Same method name behaves differently in different classes | Flexible, extensible code |
| *Abstraction* | Hiding complexity; exposing only necessary interface | Simpler to use; implementation can change without breaking callers |

- **Access modifiers:**
  - `public` (+) – accessible from anywhere
  - `private` (−) – accessible only within the class
  - `protected` (#) – accessible within class and subclasses

- **UML Class diagram:**
```
+--------------------+
| Animal             |
+--------------------+
| - name : String    |
| - age : Integer    |
+--------------------+
| + speak() : void   |
| + eat() : void     |
+--------------------+
        ▲
        |  (inheritance — hollow arrow from child to parent)
+--------------------+
| Dog                |
+--------------------+
| - breed : String   |
+--------------------+
| + bark() : void    |
+--------------------+
```

**Examples:**
- `Dog` inherits `name`, `age`, `eat()` from `Animal`; adds `bark()` and `breed`
- `speak()` in `Animal` says "..."; `Dog.speak()` overrides it to say "Woof!" → polymorphism
- `private balance` in a `BankAccount` class; only the class's own methods can change the balance → encapsulation
- `Shape` class with `calculateArea()` method; `Circle` and `Rectangle` both override it with their own formula → polymorphism

---

## 4.9 Recursion

**Gist:** Recursion is a powerful technique where a function solves a problem by calling *itself* on a simpler version of the same problem. It is elegant for problems that are naturally self-similar (trees, fractals, divide-and-conquer). The two essential parts — base case and recursive case — must both be present or the function runs forever.

**Key line-items:**
- **Base case** – the condition that *stops* recursion; returns a value directly without a further recursive call; without this, recursion is infinite (stack overflow)
- **Recursive case** – the function calls itself with a *modified argument* that moves closer to the base case
- **Call stack** – each recursive call adds a new stack frame; when base case is reached, frames are resolved in reverse order (LIFO)
- **Stack overflow** – occurs if recursion is too deep (no base case or base case never reached); crashes the program

```
// Factorial — n! = n × (n-1)!
function factorial(N)
    if N = 0 then
        return 1               // base case
    else
        return N * factorial(N - 1)    // recursive case
    end if
end function

// Fibonacci
function fib(N)
    if N <= 1 then
        return N               // base case
    else
        return fib(N-1) + fib(N-2)    // recursive case
    end if
end function
```

- **Trace of factorial(4):**
```
factorial(4) → 4 × factorial(3)
               3 × factorial(2)
                   2 × factorial(1)
                       1 × factorial(0) → 1
               = 1 → 2 → 6 → 24
```

- **Recursion vs Iteration:**

| | Recursion | Iteration |
|---|---|---|
| Code clarity | Often elegant for self-similar problems | More explicit for simple loops |
| Memory | Uses call stack (risk of overflow) | Uses loop variable (constant memory) |
| Performance | Slower (function call overhead) | Faster |
| Best for | Trees, divide-and-conquer, mathematically recursive definitions | Simple repeated tasks |

**Examples:**
- Factorial, Fibonacci, power (xⁿ), traversing a tree, searching a file directory
- Removing the base case from factorial → infinite recursion → stack overflow crash
- IB question: trace recursive calls and show the call stack / returned values

---

## 4.10 Stacks and Queues

**Gist:** Stacks and queues are *abstract data types* — data structures defined by their behaviour, not their implementation. The key is knowing when each is appropriate and understanding the operations. Stacks are LIFO; queues are FIFO. Both appear in real systems (function call stacks, print queues) and in algorithm design (DFS uses a stack; BFS uses a queue).

**Key line-items:**

**Stack – LIFO (Last In, First Out):**
- *push(item)* – add item to the top
- *pop()* – remove and return the top item
- *peek() / top()* – view the top item without removing it
- *isEmpty()* – returns true if stack has no items
- **Uses:** undo/redo, function call stack, bracket matching, evaluating expressions, backtracking in mazes

```
PUSH 3 → stack: [3]
PUSH 7 → stack: [3, 7]
PUSH 1 → stack: [3, 7, 1]
POP    → returns 1; stack: [3, 7]
```

**Queue – FIFO (First In, First Out):**
- *enqueue(item)* – add item to the back
- *dequeue()* – remove and return the front item
- *isEmpty()* – returns true if queue has no items
- **Uses:** print spooling, CPU scheduling, network packet buffers, breadth-first search (BFS)

```
ENQUEUE A → queue: [A]
ENQUEUE B → queue: [A, B]
ENQUEUE C → queue: [A, B, C]
DEQUEUE   → returns A; queue: [B, C]
```

**Examples:**
- Browser back/forward history → stack (back = pop, visit = push)
- Call centre waiting queue → queue (first caller answered first)
- Recursion uses the call stack internally (each function call pushed, each return pops)
- Printer queue: first document sent is first document printed

---

## 4.11 Linked Lists

**Gist:** Unlike arrays, linked lists are *dynamic* — they can grow and shrink at runtime. Instead of stored in consecutive memory locations, each element (node) contains the data and a pointer to the next node. This makes insertion and deletion efficient but random access slow. Understanding linked lists sets the foundation for more advanced data structures (trees, graphs).

**Key line-items:**
- **Node** – the basic unit of a linked list; contains:
  - *Data* – the stored value
  - *Pointer/Next* – address of the next node (null at the end of the list)
- **Head** – pointer to the first node; entry point to the list
- **Null pointer** – marks the end of the list (no next node)

- **Operations:**
  - *Traverse* – follow pointers from head to null
  - *Insert* – create new node; update pointers (O(1) if position known)
  - *Delete* – update pointer of previous node to skip the deleted node; free the node (O(1) if position known)

- **Linked list vs Array:**

| | Array | Linked List |
|---|---|---|
| Size | Fixed at creation | Dynamic — grows/shrinks at runtime |
| Access by index | O(1) — direct | O(n) — must traverse from head |
| Insertion/deletion | O(n) — shift elements | O(1) — just change pointers |
| Memory layout | Contiguous blocks | Non-contiguous; uses extra memory for pointers |

- **Types:**
  - *Singly linked* – each node points to next only
  - *Doubly linked* – each node has pointers to both next and previous (easier to traverse backwards)
  - *Circular* – last node points back to head

**Examples:**
- Music playlist where you can add/remove songs without rearranging the whole list → linked list
- An array-based list removing element from the middle → must shift all subsequent elements; linked list just changes one pointer
- OS memory allocation uses linked lists to track free memory blocks of varying sizes

---

## 4.12 Binary Trees

**Gist:** Trees are hierarchical data structures, unlike the linear structures of arrays and linked lists. A *binary tree* is the most important type for IB CS SL — each node has at most two children. The *binary search tree* (BST) provides efficient searching and sorting. Tree traversals (in-order, pre-order, post-order) determine the *order* in which nodes are visited, and each has a specific use.

**Key line-items:**
- **Binary tree terminology:**
  - *Root* – topmost node; has no parent
  - *Leaf* – a node with no children
  - *Parent / child / sibling* – relational terms
  - *Subtree* – a node and all its descendants
  - *Height/depth* – number of levels (root at level 0 or 1 depending on convention)
  - *Left child / Right child* – at most one of each per node

- **Binary Search Tree (BST) property:**
  - All values in the *left* subtree < parent node value
  - All values in the *right* subtree > parent node value
  - Supports efficient search, insert, delete — O(log n) on a balanced tree

- **Inserting into a BST:** compare value to current node; go left if smaller, right if larger; repeat until null position found; insert there

- **Tree traversals:**

| Traversal | Order | Result for BST | Common use |
|---|---|---|---|
| *In-order* | Left → Root → Right | Sorted ascending | Printing BST in order |
| *Pre-order* | Root → Left → Right | — | Copying/serialising a tree |
| *Post-order* | Left → Right → Root | — | Deleting a tree; evaluating expression trees |

**Examples:**
- BST containing [8, 3, 10, 1, 6, 14, 4, 7, 13]:
  ```
          8
        /   \
       3    10
      / \     \
     1   6    14
        / \   /
       4   7 13
  ```
- In-order traversal: 1, 3, 4, 6, 7, 8, 10, 13, 14 → sorted!
- Searching BST for 7: 7<8 → go left; 7>3 → go right; 7>6 → go right; found! (4 comparisons vs up to 9 for linear)

---

# QUICK REFERENCE

## Command Terms

| Term | What to write |
|---|---|
| **State** | Single fact; no explanation |
| **Define** | Precise meaning of a term |
| **Identify** | Name or recognise |
| **Outline** | Brief description; main points only |
| **Describe** | Detailed account of characteristics |
| **Explain** | Give reasons — use "because" |
| **Construct** | Build/create (algorithm, diagram) |
| **Analyse** | Break down and examine in detail |
| **Evaluate** | Weigh advantages and disadvantages; make a judgement |
| **Suggest** | Propose a reasonable answer (no single right answer) |
| **Justify** | Give evidence or reasons to support a claim |

## Key Calculations

| Calculation | Formula |
|---|---|
| Values from n bits | **2ⁿ** |
| Max unsigned value, n bits | **2ⁿ − 1** |
| Image file size | width × height × bit depth ÷ 8 = bytes |
| Audio file size | sample rate × bit depth × seconds × channels ÷ 8 = bytes |
| Binary → Hex | Group into 4 bits from right; convert each group |

## Must-Know One-Line Definitions

| Term | Definition |
|---|---|
| Algorithm | Finite, precise, step-by-step instructions to solve a problem |
| Abstraction | Removing unnecessary detail; focusing on essential features |
| Decomposition | Breaking a complex problem into smaller sub-problems |
| Encapsulation | Bundling data + methods; hiding internal state |
| Inheritance | Subclass acquires attributes/methods from a superclass |
| Polymorphism | Same method name, different behaviour in different classes |
| Recursion | A function that calls itself, with a base case to stop it |
| Stack | LIFO data structure — last in, first out |
| Queue | FIFO data structure — first in, first out |
| Binary search | Halves search space each step; requires sorted data |
| Bubble sort | Repeatedly swaps adjacent out-of-order elements; O(n²) |
| Firewall | Monitors and filters network traffic based on security rules |
| Encryption | Transforms data so only authorised parties can read it |
| DNS | Translates human domain names into IP addresses |
| Packet switching | Data split into packets, routed independently, reassembled at destination |
| RAM | Volatile, read/write primary memory; lost when power off |
| ROM | Non-volatile, read-only memory; stores firmware |
| Validation | Checking data is reasonable / within expected range |
| Verification | Checking data was entered correctly |
| Parallel changeover | Running old and new systems simultaneously during transition |
| Legacy system | Old system still in use; hard to maintain, security risks |

---

*Read the command term. Answer exactly what is asked. Use correct CS terminology. Good luck.*
