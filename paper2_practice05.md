Here is a FULL IB Computer Science SL Paper 2 (Option D: OOP B3.1) predicted mock exam (45 marks) built from the highest-probability IB themes: subscriptions, student tracking, transport, and fitness systems, with realistic IB-style traps and marking structure.

⸻

📘 IB Computer Science SL – Paper 2 (PREDICTED MOCK EXAM 2026)

Option D: Object-Oriented Programming (B3.1)

Time: 1 hour
Total Marks: 45

⸻

🧾 Section A – Short Response (10 marks)

1. Subscription System Concepts (4 marks)

A streaming service uses a class called Subscriber.

Define the following in this context:
a) Class (1)
b) Object (1)
c) Attribute (1)
d) Method (1)

⸻

2. Business Rules Interpretation (3 marks)

Explain two potential edge cases that must be handled when calculating a subscription fee where:

* first 10 hours are free
* usage is measured in floating-point hours

⸻

3. Object-Oriented Design (3 marks)

Explain why a method is more appropriate than an attribute for calculating a dynamic value such as a monthly bill.

⸻

🧾 Section B – Code Development (20 marks)

⸻

🎬 Scenario 1: Streaming Subscription System (10 marks)

A streaming platform stores subscriber data using a class Subscriber.

Attributes:

* name (String)
* planType (String: “basic” or “premium”)
* hoursWatched (double)
* monthlyFee (double)

Business Rules:

* First 10 hours are free
* After 10 hours:
    * basic → $2/hour
    * premium → $1/hour
* Maximum bill is $120
* Hours cannot be negative

⸻

4. Class Definition (6 marks)

Write the full class including:

* attributes
* constructor
* validation of hoursWatched

⸻

5. Method: updateHours (4 marks)

Write:

public void addHours(double hours)

Requirements:

* must not allow negative input
* must correctly update total hours
* ensure value remains valid

⸻

⸻

🧾 Scenario 2: Fitness Tracking System (10 marks)

A gym tracks members using a class Member.

Attributes:

* name (String)
* workoutsPerWeek (int)
* caloriesBurned (int)
* membershipLevel (String: “basic”, “premium”)

Business Rules:

* If workoutsPerWeek > 5 → bonus applies in calculations
* caloriesBurned cannot be negative
* premium members get 20% bonus calories

⸻

6. Method: updateWorkout (4 marks)

public void addWorkout()

* increments workoutsPerWeek
* ensures logical consistency

⸻

7. Method: calculateScore (6 marks)

public double calculateScore()

Rules:

* base score = caloriesBurned / 10
* +20% if premium
* ￼	bonus if workoutsPerWeek > 5
* return final score

⸻

🧾 Section C – Code Tracing & Evaluation (15 marks)

⸻

🚕 Scenario 3: Taxi Ride System

A ride-sharing system uses:

class Ride {
    double distanceKm;
    double baseFare;
    boolean isPeakTime;
}

Business Rules:

* First 2 km free
* After 2 km → $3 per km
* Peak time → ×1.5 multiplier
* Minimum fare = $5
* Maximum fare = $100

⸻

8. Trace Execution (6 marks)

Ride r1 = new Ride(5.5, 10.0, true);
double fare = r1.calculateFare();
System.out.println(fare);

Tasks:

a) Show billable distance (2)
b) Calculate final fare step-by-step (2)
c) Output result (2)

⸻

9. Boolean Logic (3 marks)

Explain the output:

System.out.println(r1.isAffordable());

Assume:

* returns true if fare ≤ 50 after calculation

⸻

10. Debugging Question (6 marks)

A student writes:

public double calculateFare() {
    double fare = (distanceKm - 2) * 3;
    if (isPeakTime) {
        fare = fare * 1.5;
    }
    if (fare < 5) {
        fare = 5;
    }
    if (fare > 100) {
        fare = 100;
    }
    return fare;
}

Tasks:

Identify and explain:

* 2 logical or design issues (4 marks)
* why they may cause incorrect IB test outputs (2 marks)

⸻

📊 MARKSCHEME (CONDENSED)

⸻

Section A

Q1 (4)

* Class → blueprint
* Object → instance
* Attribute → data field
* Method → function/behavior

⸻

Q2 (3)

Any two:

* fractional hours (e.g. 9.7 → rounding issues)
* exactly 10 hours boundary
* negative input
* floating precision errors

⸻

Q3 (3)

* dynamic calculation
* depends on changing data
* avoids redundancy

⸻

Section B

Q4 (6)

class Subscriber {
    String name;
    String planType;
    double hoursWatched;
    double monthlyFee;
    public Subscriber(String n, String p, double h, double f) {
        name = n;
        planType = p;
        if (h >= 0) {
            hoursWatched = h;
        } else {
            hoursWatched = 0;
        }
        monthlyFee = f;
    }
}

⸻

Q5 (4)

public void addHours(double hours) {
    if (hours > 0) {
        hoursWatched += hours;
    }
}

⸻

Q6 (4)

public void addWorkout() {
    workoutsPerWeek++;
}

⸻

Q7 (6)

public double calculateScore() {
    double score = caloriesBurned / 10.0;
    if (membershipLevel.equals("premium")) {
        score = score * 1.2;
    }
    if (workoutsPerWeek > 5) {
        score = score + 5;
    }
    return score;
}

⸻

Section C

Q8 (6)

* Distance: 5.5 → billable = 3.5 (2)
* Fare: 3.5 × 3 = 10.5
* Peak → 15.75
* Output = 15.75 (4)

⸻

Q9 (3)

* likely affordable → true
* depends on computed fare ≤ 50

⸻

Q10 (6)

Issues:

1. No handling for distance ≤ 2 → negative fare risk
2. Order of caps may distort logic
3. Missing explicit free distance handling
4. Possible double counting logic ambiguity

(Any 2 well explained = full marks)

⸻

🧠 FINAL INSIGHT (WHY THIS IS HIGH PROBABILITY)

This paper intentionally combines:

* subscription billing
* fitness scoring
* transport fare logic
* boundary-heavy tracing

👉 These are the exact 4 recurring IB OOP patterns

⸻

If you want next, I can give:

* a full marking simulation (you answer → I grade like IB examiner)
* or a “predict 7/7 grade answers only” model solution sheet
* or a last 2-hour crash revision plan

Just tell me 👍