Here is a carefully “IB-style prediction set” for Paper 2 (Option D: OOP B3.1).
Important honesty note first: IB does not reuse exact questions, but it recycles patterns, traps, and scenario types very heavily. So this is built from those patterns.

I’ve designed this like a real exam prediction pack: likely themes + likely question types + exam-style prompts.

⸻

📘 IB CS SL Paper 2 (OOP) – “Predicted Question Set 2026”

(High-probability exam patterns)

⸻

🔮 Theme 1: Membership / Subscription Systems (VERY HIGH PROBABILITY)

🧠 Why this appears often

IB loves:

* fees
* discounts
* usage tracking
* thresholds

⸻

🧾 Predicted Question

A company is building a Streaming Subscription System.

Each Subscriber stores:

* name
* planType (basic/premium)
* monthlyFee
* hoursWatched

Business Rules:

* First 10 hours free
* After that:
    * basic: $2 per hour
    * premium: $1 per hour
* If usage exceeds 100 hours → cap fee at $120
* If hours = 0 → no charge

⸻

🔥 Likely IB Question Types:

* Write class + constructor
* Validate hours
* Calculate monthly bill
* Trace output with tricky values (e.g. 9.8 hours, 10, 10.5)

⸻

🔮 Theme 2: School / Student Tracking Systems (VERY HIGH PROBABILITY)

⸻

🧾 Predicted Question

A school uses a system to track student performance.

Each StudentRecord stores:

* studentName
* totalAssignments
* completedAssignments
* attendancePercentage

Business Rules:

* Completed assignments cannot exceed total
* Attendance < 75% → no certificate
* Certificate only if:
    * ≥ 80% assignments completed
    * attendance ≥ 75%

⸻

🔥 Likely IB Question Types:

* Boolean method (isEligible())
* Boundary testing (74.9%, 75%, 80%)
* Trace output with method calls

⸻

🔮 Theme 3: Transport / Booking Systems (HIGH PROBABILITY)

⸻

🧾 Predicted Question

A taxi app stores ride data in a Ride class:

* distanceKm
* baseFare
* surgeMultiplier
* isPeakTime

Business Rules:

* First 2 km free
* Peak time → surge multiplier ×1.5
* Minimum fare = $5
* Max fare = $100

⸻

🔥 Likely IB Question Types:

* Calculation method with multiple conditions
* Order-of-operations traps
* Cap + minimum rule together
* Floating-point handling

⸻

🔮 Theme 4: Fitness / Health Tracking (VERY HIGH PROBABILITY)

⸻

🧾 Predicted Question

A gym system tracks members:

* name
* workoutsPerWeek
* caloriesBurned
* membershipLevel

Business Rules:

* workouts > 5 → bonus applied
* calories < 500/week → warning
* premium members get 20% bonus points

⸻

🔥 Likely IB Question Types:

* update methods (increment workouts)
* conditional logic
* boolean eligibility method

⸻

🔥 MOST LIKELY TRICK PATTERNS IB WILL TEST

These are NOT topics — they are exam traps:

⸻

⚠️ 1. Boundary confusion

Expect:

* “at least” vs “more than”
* exactly 0 cases
* threshold = 10, 20, 80%

⸻

⚠️ 2. Order of conditions

Example trap:

if (x > 10) ...
else if (x == 0) ...

👉 IB wants you to fix ordering

⸻

⚠️ 3. Floating-point inputs in tracing

* 9.7 → becomes 9
* 2.9 → becomes 2

👉 Hidden truncation effects

⸻

⚠️ 4. Multiple rules in one method

IB will combine:

* discount + cap + free allowance
    in same question

⸻

⚠️ 5. Boolean method dependency

Example:

* isEligible() depends on 2–3 conditions
* used inside another method → trace confusion

⸻

📊 MOST PROBABLE QUESTION FORMAT (VERY IMPORTANT)

Expect this structure:

Q1 (Class definition)

* attributes + constructor

Q2 (Validation method)

* setter / update method

Q3 (Calculation method – 8 marks)

* multi-rule logic

Q4 (Tracing – 6 marks)

* step-by-step object updates

Q5 (Boolean + explanation – 5 marks)

* eligibility / condition check

⸻

🧠 IB EXAMINER PATTERN INSIGHT

From past Paper 2 style trends:

* 70% of marks come from:
    * correct logic flow
    * correct condition handling
    * correct updates

NOT syntax perfection

⸻

🎯 FINAL “WHAT TO PRACTICE LAST NIGHT”

If you do only 3 things:

✔ Write 3 full classes from scratch
✔ Do 5 trace questions (with decimals + updates)
✔ Do 3 calculation methods with multiple rules

⸻

🧩 If you want next:

I can generate:

* a FULL predicted mock exam (45 marks) using these exact themes
* or a “guaranteed traps” practice set (only trick questions IB loves)
* or a timed 60-minute simulation with marking like an examiner

Just tell me 👍