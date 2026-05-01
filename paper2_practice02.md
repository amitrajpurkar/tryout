Here’s a realistic IB Computer Science SL Paper 2 mock exam for Option D (OOP – B3.1) with an unseen scenario + extended case-based questions, closely modeled on how IB structures these.

⸻

IB Computer Science SL – Paper 2 (Mock Exam)

Option D: Object-Oriented Programming (B3.1)

Time: 1 hour
Marks: 45

⸻

Case Study: Smart Gym Membership System

A local gym wants to develop a simple system to manage its members. The system will use object-oriented programming with a single class called Member.

Each Member has:

* a name
* a membership ID
* a monthly fee
* the number of visits made in a month

The system should allow:

* creating a new member
* recording visits
* calculating total monthly cost (base fee + extra charges if visits exceed a limit)
* displaying member details

Business Rules:

* Each member has a base monthly fee
* If visits exceed 20 per month, each extra visit costs $2
* Visits cannot be negative

⸻

Section A – Understanding the Scenario (10 marks)

1. (4 marks)
Identify four attributes required for the Member class and state an appropriate data type for each.

⸻

2. (3 marks)
Explain the role of a constructor in this scenario.

⸻

3. (3 marks)
Explain why methods are required in this class instead of writing all logic in the main program.

⸻

Section B – Code Development (20 marks)

4. (6 marks)
Write the class definition for Member including:

* attributes
* a constructor to initialize all attributes

⸻

5. (6 marks)
Write a method:

public void addVisit()

This method should:

* increase the visit count by 1
* ensure visits do not become invalid

⸻

6. (8 marks)
Write a method:

public double calculateMonthlyCost()

This method should:

* return the total cost
* apply the rule: visits > 20 → extra visits × $2

⸻

Section C – Code Reading & Evaluation (15 marks)

7. (6 marks)
Consider the following code:

Member m1 = new Member("Jordan", 1023, 50.0, 18);
m1.addVisit();
m1.addVisit();
m1.addVisit();
double cost = m1.calculateMonthlyCost();
System.out.println(cost);

a) What is the final number of visits? (2 marks)
b) What is the output of the program? (2 marks)
c) Explain how the cost was calculated (2 marks)

⸻

8. (5 marks)
A student writes the following method:

public void addVisit() {
    visits = visits + 1;
}

Explain two improvements that should be made to ensure robustness.

⸻

9. (4 marks)
Discuss two benefits of using a class like Member in this system.

⸻

Markscheme (Condensed)

Q1 (4 marks)

Any four:

* name → String
* membershipID → int
* monthlyFee → double
* visits → int

⸻

Q2 (3 marks)

* Initializes object attributes (1)
* Called when object is created (1)
* Ensures valid starting state (1)

⸻

Q3 (3 marks)

* Improves modularity (1)
* Reusability (1)
* Easier maintenance / readability (1)

⸻

Q4 (6 marks)

class Member {
    String name;
    int membershipID;
    double monthlyFee;
    int visits;
    public Member(String n, int id, double fee, int v) {
        name = n;
        membershipID = id;
        monthlyFee = fee;
        visits = v;
    }
}

⸻

Q5 (6 marks)

public void addVisit() {
    if (visits >= 0) {
        visits++;
    }
}

(Allow simple increment with basic validation explanation)

⸻

Q6 (8 marks)

public double calculateMonthlyCost() {
    if (visits > 20) {
        int extra = visits - 20;
        return monthlyFee + (extra * 2);
    } else {
        return monthlyFee;
    }
}

⸻

Q7 (6 marks)

* Visits: 18 → 21 (2)
* Output: 52.0 (2)
* Explanation:
    * 1 extra visit (21 - 20)
    * extra cost = 2 → total = 50 + 2 = 52 (2)

⸻

Q8 (5 marks)

Any two:

* Validate visits not negative
* Prevent overflow / unrealistic values
* Add input validation
* Possibly return value or confirm update

⸻

Q9 (4 marks)

Any two:

* Encapsulation
* Code reuse
* Real-world modeling
* Easier debugging/maintenance

⸻

If you want to go further:

I can push this into true IB difficulty with:

* hidden edge cases (very IB-style traps)
* markscheme with command term grading (describe vs explain vs outline)
* or a full 3-paper mock set (Paper 1 + 2 + 3 style)

Just tell me how hard you want it.