Here’s your final 1-page IB Computer Science SL Paper 2 (OOP B3.1) Mega Cheat Sheet—a compressed “everything you need before the exam” sheet combining rules, templates, traps, and scoring strategy.

⸻

IB Computer Science SL – Paper 2 (OOP) FINAL MEGA CHEAT SHEET

Option D: Object-Oriented Programming (B3.1)

⸻

🔷 1. CORE OOP CONCEPTS (MUST KNOW)

* Class → blueprint
* Object → instance of class
* Attribute → data stored in object
* Method → behavior/functions of object
* Constructor → initializes object (same name, no return type)

⸻

🔷 2. GOLDEN CLASS TEMPLATE (FULL MARK BASE)

class ClassName {
    dataType attr1;
    dataType attr2;
    public ClassName(dataType a1, dataType a2) {
        attr1 = a1;
        attr2 = a2;
    }
}

✔ Always include ALL attributes
✔ Constructor = same name as class
✔ No return type ever

⸻

🔷 3. VALIDATION RULES (HIGH FREQUENCY MARKS)

Always enforce:

* no negatives
* within bounds
* logical consistency

if (value >= 0 && value <= max) {
    attribute = value;
}

⸻

🔷 4. METHOD TEMPLATES (FULL MARK PATTERNS)

✔ Update method

public void updateValue(int newValue) {
    if (newValue >= 0) {
        attribute = newValue;
    }
}

✔ Increment method

attribute++;

⸻

✔ Calculation method (MOST IMPORTANT)

public double calculate() {
    double result;
    if (condition1) {
        result = value1;
    } else {
        result = value2;
    }
    return result;
}

⸻

✔ Boolean method

public boolean check() {
    if (condition) {
        return true;
    }
    return false;
}

⸻

🔷 5. IB BUSINESS LOGIC PATTERNS

✔ Multi-rule structure

if (specialCase) {
    result = a;
}
else if (middleCase) {
    result = b;
}
else {
    result = c;
}

⸻

✔ Cap / limit rule

if (value > max) {
    value = max;
}
if (value < 0) {
    value = 0;
}

⸻

✔ Refund / discount pattern (VERY COMMON)

if (value == 0) {
    return full;
}
else if (value < threshold) {
    return full * 0.5;
}
else {
    return 0;
}

⸻

🔷 6. BIGGEST IB TRAPS ⚠️

❌ Edge cases missed

✔ Always check:

* 0
* max value
* negative values
* boundary exactly equal

⸻

❌ Wrong condition order

✔ Always:

1. special cases first
2. main logic
3. caps last

⸻

❌ Integer division mistake

5 / 2  // = 2 (WRONG if expecting 2.5)

✔ Fix:

5 / 2.0
(double)5 / 2

⸻

❌ Not updating object state

✔ Always use:

attribute++;

NOT:

int temp = attribute + 1;

⸻

❌ Constructor mistakes

* must NOT have return type
* must initialize all attributes

⸻

🔷 7. TRACE QUESTIONS STRATEGY

ALWAYS write:

1. Initial values
2. After each method call
3. Final output

✔ Don’t guess — simulate step-by-step

⸻

🔷 8. EXPLANATION TEMPLATE (FULL MARK ANSWERS)

This happens because [rule].
This causes [effect].
Therefore, [result].

⸻

🔷 9. ERROR IDENTIFICATION TEMPLATE

Error 1: ...
This is incorrect because ...
Error 2: ...
This is incorrect because ...

⸻

🔷 10. EXAM SCORING STRATEGY

To get full marks:

✔ correct structure
✔ correct logic order
✔ handles edge cases
✔ valid OOP design
✔ clear reasoning

👉 IB does NOT require perfect syntax
👉 IB DOES require correct logic + coverage of cases

⸻

🔷 11. 2-MINUTE FINAL CHECK BEFORE SUBMISSION

✔ Constructor correct?
✔ All attributes initialized?
✔ Edge cases handled?
✔ No negative outputs?
✔ Limits enforced?
✔ Logic order correct?
✔ Return statements included?

⸻

🧠 FINAL IB MINDSET

“If I try extreme inputs, does my code still work?”

If YES → full marks territory.

⸻

If you want next, I can simulate:

* a real timed Paper 2 (with timer + grading after you answer)
* or a “predict the IB exam questions for this year” set
* or a rapid-fire 20-question trap quiz for last-day prep

Just tell me 👍