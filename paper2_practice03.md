Alright—this one is designed to trip you up in classic IB ways: boundary values, hidden assumptions, method side effects, and subtle logic flaws.

⸻

IB Computer Science SL – Paper 2 (Advanced Mock)

Option D: Object-Oriented Programming (B3.1)

Time: 1 hour
Marks: 45

⸻

Case Study: Parking Garage System

A parking garage is developing a system using a single class called Car.

Each Car object stores:

* license plate number
* number of hours parked
* hourly parking rate
* a boolean indicating whether the car is a VIP

⸻

Business Rules (Read Carefully — traps included)

* The first 2 hours are free for all cars
* After that:
    * Regular cars pay full hourly rate
    * VIP cars get 50% discount AFTER the free period
* Parking hours:
    * cannot be negative
    * must be rounded down to the nearest whole number
* Maximum charge per day = $50
* If hours = 0 → cost must be 0

⸻

Section A – Understanding & Edge Cases (10 marks)

1. (4 marks)
Identify four attributes for the Car class with appropriate data types.

⸻

2. (3 marks)
Explain two edge cases that must be handled when calculating parking cost.

(IB trap: not just obvious ones—think boundaries and invalid states)

⸻

3. (3 marks)
Explain why storing hoursParked as a floating-point number may cause issues.

⸻

Section B – Code Development (20 marks)

4. (6 marks)
Write the class definition with:

* attributes
* constructor initializing all attributes

⸻

5. (6 marks)
Write a method:

public void setHours(double hours)

This method should:

* reject negative values
* round down to nearest integer
* update the attribute correctly

⸻

6. (8 marks)
Write a method:

public double calculateCharge()

This method must:

* apply free hours rule
* apply VIP discount correctly
* enforce maximum daily charge
* handle all edge cases

⸻

Section C – Code Tracing & Traps (15 marks)

7. (6 marks)
Consider the following:

Car c1 = new Car("ABC123", 3.7, 10.0, false);
double charge = c1.calculateCharge();
System.out.println(charge);

a) What value is used for hours after processing? (2 marks)
b) What is the final charge? (2 marks)
c) Explain your reasoning (2 marks)

⸻

8. (5 marks)
Consider:

Car c2 = new Car("VIP001", 2.9, 20.0, true);
double charge = c2.calculateCharge();
System.out.println(charge);

a) What is the output? (2 marks)
b) Explain why this is a common mistake point for students (3 marks)

⸻

9. (4 marks)
A student writes:

public double calculateCharge() {
    double cost = (hoursParked - 2) * hourlyRate;
    if (vip) {
        cost = cost / 2;
    }
    if (cost > 50) {
        cost = 50;
    }
    return cost;
}

Identify two logical errors and explain them.

⸻

Markscheme (Condensed with IB Traps Highlighted)

Q1 (4 marks)

* licensePlate → String
* hoursParked → int or double
* hourlyRate → double
* vip → boolean

⸻

Q2 (3 marks)

Any two:

* hours ≤ 2 → cost = 0 (critical boundary trap)
* negative hours input
* fractional hours rounding
* cost exceeding max limit
* VIP discount applied incorrectly before free hours

⸻

Q3 (3 marks)

* precision issues (1)
* rounding inconsistencies (1)
* incorrect billing if not truncated (1)

⸻

Q4 (6 marks)

class Car {
    String licensePlate;
    int hoursParked;
    double hourlyRate;
    boolean vip;
    public Car(String plate, double hours, double rate, boolean v) {
        licensePlate = plate;
        setHours(hours);
        hourlyRate = rate;
        vip = v;
    }
}

⸻

Q5 (6 marks)

public void setHours(double hours) {
    if (hours >= 0) {
        hoursParked = (int) hours; // truncates
    } else {
        hoursParked = 0;
    }
}

⸻

Q6 (8 marks) — Full Trap Logic

public double calculateCharge() {
    if (hoursParked == 0) return 0;
    int billableHours = hoursParked - 2;
    if (billableHours <= 0) return 0;
    double cost;
    if (vip) {
        cost = billableHours * hourlyRate * 0.5;
    } else {
        cost = billableHours * hourlyRate;
    }
    if (cost > 50) {
        cost = 50;
    }
    return cost;
}

⸻

Q7 (6 marks)

* Hours: 3.7 → 3 (2)
* Billable hours: 3 - 2 = 1
* Cost: 1 × 10 = 10 → Output = 10.0 (2)
* Explanation: truncation + free hours applied first (2)

⸻

Q8 (5 marks)

* Hours: 2.9 → 2
* Billable hours = 0 → cost = 0 → Output = 0.0 (2)

Explanation (3):

* Students mistakenly:
    * round to 3 instead of truncate
    * apply VIP discount incorrectly
    * forget free hours eliminate all cost

⸻

Q9 (4 marks)

Errors:

1. (hoursParked - 2) can be negative → negative cost ❌
2. VIP discount applied to negative or zero incorrectly ❌
3. No handling for hours ≤ 2 ❌
4. Missing zero-floor constraint

(Any two explained = full marks)

⸻

Why this is IB-level tricky

This paper intentionally tests:

* Order of operations (free hours BEFORE discount)
* Integer truncation vs rounding
* Boundary conditions (2 hours exactly)
* Negative intermediate values
* Hidden constraints (max cap, zero floor)

⸻

If you want next level:

I can generate:

* A Paper 2 with a full unseen scenario + multi-part 15-mark question (very close to actual IB finals)
* A marking grid with examiner comments
* Or a “common mistakes + how to avoid them” cheat sheet

Just tell me how far you want to push it.