Here’s a high-fidelity IB Computer Science SL Paper 2 mock with a full unseen scenario and a long 15-mark question, closely matching the structure and thinking style of real IB exams.

⸻

IB Computer Science SL – Paper 2 (Full Mock)

Option D: Object-Oriented Programming (B3.1)

Time: 1 hour
Marks: 45

⸻

Unseen Scenario: Online Course Enrollment System

A company is building a system to manage student enrollments in online courses. The system uses a single class called CourseEnrollment.

Each object represents one student enrolled in a course.

⸻

Data Stored

Each CourseEnrollment object includes:

* studentName (String)
* courseName (String)
* totalModules (int)
* completedModules (int)
* enrollmentFee (double)

⸻

Business Rules (Read Carefully – IB traps included)

* completedModules:
    * cannot exceed totalModules
    * cannot be negative
* A student completes the course when:

completedModules == totalModules

* A certificate is awarded ONLY IF:
    * course is completed
    * AND at least 80% of modules were completed on time
        (Assume a boolean method completedOnTime() exists and returns true/false)
* Refund policy:
    * If completedModules = 0 → 100% refund
    * If completedModules < 50% → 50% refund
    * Otherwise → no refund

⸻

Section A – Understanding the System (10 marks)

1. (4 marks)
Identify four attributes and their appropriate data types.

⸻

2. (3 marks)
Explain two validation rules that must be enforced when updating completedModules.

⸻

3. (3 marks)
Explain why a method is more appropriate than an attribute for determining if a certificate is awarded.

⸻

Section B – Code Development (20 marks)

4. (6 marks)
Write the class definition including:

* attributes
* a constructor initializing all attributes
* ensure valid initialization

⸻

5. (6 marks)
Write a method:

public void updateProgress(int modulesCompleted)

This method should:

* update completedModules
* enforce all constraints

⸻

6. (8 marks)
Write a method:

public double calculateRefund()

This method must:

* return the correct refund based on rules
* handle boundary values correctly

⸻

Section C – Extended Response (15 marks)

(This is the IB-style long question — multi-step reasoning required)

⸻

7. (15 marks)

A developer adds the following methods:

public boolean isCourseCompleted() {
    return completedModules == totalModules;
}
public boolean isCertificateAwarded() {
    if (isCourseCompleted() && completedOnTime()) {
        return true;
    }
    return false;
}

And the following main program:

CourseEnrollment c1 = new CourseEnrollment("Ava", "CS101", 10, 4, 200.0);
CourseEnrollment c2 = new CourseEnrollment("Leo", "CS101", 10, 10, 200.0);
c1.updateProgress(6);
c2.updateProgress(10);
System.out.println(c1.calculateRefund());
System.out.println(c2.calculateRefund());
System.out.println(c1.isCertificateAwarded());
System.out.println(c2.isCertificateAwarded());

⸻

7(a) (4 marks)

Determine the value of completedModules for:

* c1
* c2

Explain your answer.

⸻

7(b) (4 marks)

Determine the output of:

System.out.println(c1.calculateRefund());
System.out.println(c2.calculateRefund());

Show all working.

⸻

7(c) (3 marks)

Explain the output of:

System.out.println(c1.isCertificateAwarded());
System.out.println(c2.isCertificateAwarded());

(Assume completedOnTime() returns true for both students)

⸻

7(d) (4 marks)

A student rewrites calculateRefund() as:

public double calculateRefund() {
    if (completedModules < totalModules / 2) {
        return enrollmentFee * 0.5;
    } else if (completedModules == 0) {
        return enrollmentFee;
    } else {
        return 0;
    }
}

Identify and explain two logical errors.

⸻

Markscheme (Examiner Style – Key Points)

⸻

Section A

Q1 (4)

* studentName → String
* courseName → String
* totalModules → int
* completedModules → int
* enrollmentFee → double

⸻

Q2 (3)

* completedModules ≥ 0
* completedModules ≤ totalModules
* prevent invalid states

⸻

Q3 (3)

* depends on logic/conditions (1)
* computed dynamically (1)
* avoids redundancy (1)

⸻

Section B

Q4 (6)

class CourseEnrollment {
    String studentName;
    String courseName;
    int totalModules;
    int completedModules;
    double enrollmentFee;
    public CourseEnrollment(String s, String c, int t, int comp, double fee) {
        studentName = s;
        courseName = c;
        totalModules = t;
        if (comp >= 0 && comp <= t) {
            completedModules = comp;
        } else {
            completedModules = 0;
        }
        enrollmentFee = fee;
    }
}

⸻

Q5 (6)

public void updateProgress(int modulesCompleted) {
    if (modulesCompleted >= 0 && modulesCompleted <= totalModules) {
        completedModules = modulesCompleted;
    }
}

⸻

Q6 (8)

public double calculateRefund() {
    if (completedModules == 0) {
        return enrollmentFee;
    } else if (completedModules < totalModules / 2.0) {
        return enrollmentFee * 0.5;
    } else {
        return 0;
    }
}

⸻

Section C (15 marks breakdown)

⸻

7(a) (4)

* c1:
    * initial = 4
    * updateProgress(6) → 6
* c2:
    * initial = 10
    * updateProgress(10) → 10

(2 + 2 with explanation)

⸻

7(b) (4)

* c1:
    * 6/10 = 60% → no refund → 0.0
* c2:
    * 10/10 → no refund → 0.0

⸻

7(c) (3)

* c1:
    * not completed → false
* c2:
    * completed + on time → true

⸻

7(d) (4) — IB Trap Focus

Errors:

1. Order of conditions wrong:
    * completedModules == 0 never reached
2. Integer division issue:
    * totalModules / 2 may truncate
3. Incorrect logic precedence

(Any two well explained = full marks)

⸻

Why this is very close to real IB

This paper tests:

* Validation + invariants
* Integer vs floating-point traps
* Order of conditions (classic IB mistake)
* Multi-step reasoning across methods
* Hidden assumptions in method calls

⸻

If you want final prep:

I can give you:

* A 1-page “IB Paper 2 survival checklist”
* A list of 20 most common mistakes (from examiner reports style)
* Or a timed mock with strict marking + grading (1–7 band)

Just tell me 👍