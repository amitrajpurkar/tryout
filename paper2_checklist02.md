Here’s a focused IB Computer Science SL Paper 2 (OOP) cheat sheet: common mistakes + how to avoid them, based on typical IB examiner patterns.

⸻

IB Computer Science SL – Paper 2 (OOP)

Common Mistakes + How to Avoid Them

⸻

🔴 1. Ignoring Edge Cases (BIGGEST LOSS OF MARKS)

❌ Mistake

* Forgetting cases like:
    * value = 0
    * value = maximum limit
    * negative input
    * exact boundary (e.g., 20, 50%)

💡 Why it loses marks

IB often hides conditions in business rules.

✅ How to avoid it

Ask yourself after every question:

“What happens if the value is 0 or at the limit?”

Always explicitly code or explain:

if (value <= 0) { return 0; }

⸻

🔴 2. Wrong Order of Conditions

❌ Mistake

Putting general logic before special cases.

Example:

if (x < 50) { ... }
else if (x == 0) { ... } // unreachable

💡 Why it loses marks

Later conditions may never execute.

✅ How to avoid it

Order must be:

1. Special cases first
2. Main logic
3. Limits/caps last

⸻

🔴 3. Integer Division Errors

❌ Mistake

int result = 5 / 2; // = 2 not 2.5

💡 Why it loses marks

Breaks calculations silently → wrong outputs.

✅ How to avoid it

Force double:

5 / 2.0
(double)5 / 2

⸻

🔴 4. Not Validating Inputs

❌ Mistake

Direct assignment without checks:

hours = input;

💡 Why it loses marks

Invalid data breaks entire system logic.

✅ How to avoid it

Always validate:

if (input >= 0 && input <= max) {
    value = input;
}

⸻

🔴 5. Confusing Attribute vs Method

❌ Mistake

* Treating calculations as attributes
* Storing derived values permanently

💡 Why it loses marks

Breaks OOP design principles.

✅ How to avoid it

Rule:

If it changes → method
If it stores data → attribute

⸻

🔴 6. Forgetting “return” in Methods

❌ Mistake

public double calc() {
    double x = 10;
}

💡 Why it loses marks

Method produces no output.

✅ How to avoid it

Always ask:

“What should this method give back?”

return x;

⸻

🔴 7. Off-by-One Errors

❌ Mistake

if (visits >= 20) // wrong rule interpretation

💡 Why it loses marks

Misinterprets thresholds.

✅ How to avoid it

Translate carefully:

* “more than 20” → > 20
* “at least 20” → >= 20

⸻

🔴 8. Not Updating Object State Correctly

❌ Mistake

Using local variable instead of attribute:

int temp = visits + 1;

💡 Why it loses marks

Object never actually changes.

✅ How to avoid it

Always update:

visits++;

⸻

🔴 9. Ignoring Maximum Caps

❌ Mistake

Not enforcing limits like:

* max charge
* max modules
* max hours

💡 Why it loses marks

Violates business rules (IB loves these)

✅ How to avoid it

Always check after calculation:

if (cost > max) {
    cost = max;
}

⸻

🔴 10. Constructor Mistakes

❌ Mistake

* Adding return type
* Not initializing all attributes

public void Car(...) // WRONG

💡 Why it loses marks

Constructor becomes a normal method.

✅ How to avoid it

Checklist:

* Same name as class
* No return type
* Initializes ALL attributes

⸻

🔴 11. Misreading “Business Rules”

❌ Mistake

Skipping small words like:

* “only if”
* “after”
* “must not exceed”

💡 Why it loses marks

IB hides logic in wording.

✅ How to avoid it

Underline keywords:

* ONLY
* AFTER
* MUST NOT
* AT LEAST

⸻

🔴 12. Overcomplicating Solutions

❌ Mistake

Writing complex logic when simple works.

💡 Why it loses marks

Increases chance of bugs.

✅ How to avoid it

Prefer:

* simple if-else
* direct arithmetic
* minimal nesting

⸻

Final IB Survival Rule

If your code is complex, it is probably wrong.

⸻

If you want next, I can give you:

* a 1-page “perfect answer templates for full marks” sheet
* or a 10-question rapid-fire IB trap quiz
* or a full timed mock exam + marking like an examiner

Just tell me 👍