Here’s a concise, exam-focused 1-page survival checklist for IB Computer Science SL – Paper 2 (Option D: OOP, B3.1). This is designed to be something you can quickly review right before the exam.

⸻

IB Computer Science SL – Paper 2 Survival Checklist (OOP B3.1)

⸻

🔹 1. Before You Start Coding

* Read the scenario twice → underline:
    * constraints (e.g., “cannot exceed”, “must be ≥ 0”)
    * boundary values (0, max, exactly equal cases)
* Identify:
    * attributes (data)
    * methods (behavior)
* Watch for hidden rules (discounts, caps, special cases)

⸻

🔹 2. Class Design Essentials

Make sure every class includes:

* Attributes with correct data types
* A constructor:
    * same name as class
    * no return type
    * initializes ALL attributes
* Use meaningful names (IB awards clarity)

⸻

🔹 3. Validation Rules (VERY COMMON MARKS)

Always enforce:

* No negative values (e.g., hours, counts)
* Upper bounds (e.g., completed ≤ total)
* Prevent invalid object states

👉 If unsure, add:

if (value >= 0 && value <= max) { ... }

⸻

🔹 4. Boundary Conditions (BIGGEST IB TRAP ⚠️)

Always check:

* Exactly 0
* Exactly at limit (e.g., == 20, == total)
* Just below / above limit

👉 Example mindset:

* What happens if value = 0?
* What happens if value = max?

⸻

🔹 5. Integer vs Double Issues

* int / int → integer division (truncates!)
* Use:

(double) a / b

or:

a / 2.0

⸻

🔹 6. Order of Logic Matters

Correct order:

1. Handle special cases first (e.g., zero, invalid)
2. Then main logic
3. Then caps/limits

👉 Wrong order = lost marks even if logic is “almost correct”

⸻

🔹 7. Common Method Patterns

Updating values safely:

if (newValue >= 0 && newValue <= limit) {
    value = newValue;
}

Avoid negative results:

if (result < 0) {
    result = 0;
}

Apply caps:

if (cost > max) {
    cost = max;
}

⸻

🔹 8. Reading & Tracing Code

* Track variables line by line
* Watch for:
    * method calls changing values
    * repeated updates
* Always check:
    * initial value → after each method call

👉 Write intermediate steps — IB rewards working

⸻

🔹 9. Explaining Answers (Command Terms)

* Identify → just name
* Describe → what it does
* Explain → why/how (cause + effect)

👉 For full marks:

“This happens because…”

⸻

🔹 10. Common IB Mistakes (Avoid These 🚫)

* Forgetting free/zero cases
* Applying logic in wrong order
* Ignoring edge cases
* Not validating inputs
* Integer division errors
* Negative intermediate values
* Constructor with return type ❌
* Missing semicolons / syntax slips

⸻

🔹 11. Final 2-Minute Check

Before submitting:

* ✅ Constructor correct?
* ✅ All attributes initialized?
* ✅ Edge cases handled?
* ✅ No negative results?
* ✅ Logic order correct?
* ✅ Units/values make sense?

⸻

🔹 Mental Model for Paper 2

Think like this:

“What could go wrong with this input?”

That’s exactly how IB designs questions.

⸻

If you want, I can turn this into:

* a printable PDF cheat sheet
* a last-day revision plan (2–3 hours)
* or a rapid-fire quiz to test these traps

Just say 👍