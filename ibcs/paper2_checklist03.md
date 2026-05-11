Here’s a 1-page IB Computer Science SL Paper 2 (OOP B3.1) “Perfect Answer Templates” sheet. These are exam-safe patterns you can reuse to reliably hit full marks.

⸻

IB CS SL Paper 2 (OOP) – Perfect Answer Templates

“Write-this-get-marks” Sheet

⸻

🔹 1. Class Definition (FULL MARK TEMPLATE)

✅ Use when: defining any class question

class ClassName {
    // attributes
    dataType attribute1;
    dataType attribute2;
    // constructor
    public ClassName(dataType a1, dataType a2) {
        attribute1 = a1;
        attribute2 = a2;
    }
}

💡 Examiner wants:

* correct data types
* correct constructor name
* all attributes initialized

⸻

🔹 2. Safe Constructor (WITH VALIDATION)

✅ Use when constraints exist

public ClassName(type x, type y) {
    if (x >= 0) {
        attribute1 = x;
    } else {
        attribute1 = 0;
    }
    attribute2 = y;
}

💡 Key idea:

Never trust input → validate immediately

⸻

🔹 3. Setter / Update Method Template

✅ Use for updating values safely

public void updateValue(type newValue) {
    if (newValue >= 0 && newValue <= maxLimit) {
        attribute = newValue;
    }
}

💡 Examiner checks:

* validation
* correct update
* no direct unsafe assignment

⸻

🔹 4. Increment / Counter Method

✅ Use for visits, attempts, counts

public void increment() {
    attribute++;
}

Optional safe version:

if (attribute >= 0) {
    attribute++;
}

⸻

🔹 5. Calculation Method (CORE MARKS)

✅ Use for cost, score, refund, etc.

public double calculateSomething() {
    double result;
    if (condition1) {
        result = logicA;
    } else {
        result = logicB;
    }
    return result;
}

⸻

🔹 6. Multi-Condition Business Logic Template

✅ Use when IB gives rules

if (specialCase) {
    result = value1;
}
else if (anotherCase) {
    result = value2;
}
else {
    result = value3;
}

⸻

🔹 7. Boundary Protection Template (VERY IMPORTANT)

✅ Use for caps, limits, constraints

if (value > maxLimit) {
    value = maxLimit;
}
if (value < 0) {
    value = 0;
}

⸻

🔹 8. Boolean Method Template

✅ Use for yes/no logic

public boolean isConditionMet() {
    if (attribute1 == attribute2 && condition2) {
        return true;
    }
    return false;
}

⸻

🔹 9. Refund / Discount Pattern (COMMON IB QUESTION)

public double calculateRefund() {
    if (value == 0) {
        return fullAmount;
    }
    else if (value < threshold) {
        return fullAmount * 0.5;
    }
    else {
        return 0;
    }
}

⸻

🔹 10. Trace / Output Answer Template

✅ Use when explaining output

Step format:

1. Initial values
2. After each method call
3. Final values

Example structure:

* Start: x = 5
* After method1: x = 10
* Output: 10

⸻

🔹 11. Explanation Answer Template (FULL MARK STYLE)

✅ Use for “explain” questions

This happens because [rule].
As a result, [effect on variable].
Therefore, [final outcome].

⸻

🔹 12. Error Identification Template

✅ Use for debugging questions

Error 1: [what is wrong]
This is incorrect because [reason]
Error 2: [what is wrong]
This is incorrect because [reason]

⸻

🔹 FINAL EXAM STRATEGY (VERY IMPORTANT)

✔ Always do this:

* Handle 0 case first
* Handle limits next
* Then main logic
* Always return something in methods
* Always validate inputs

⸻

🧠 IB MARKER THINKING RULE

If your answer shows:

* structure ✔
* validation ✔
* correct logic order ✔
* edge cases ✔

👉 You get full marks even if syntax is slightly imperfect.

⸻

If you want next level prep, I can give you:

* a full “model answers for a 45/45 Paper 2” paper
* or a timed 30-minute drill set (very exam-like pressure)
* or a final revision sheet combining EVERYTHING (1-page mega cheat sheet)