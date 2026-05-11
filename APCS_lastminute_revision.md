# 🖥️ AP Computer Science A — Last-Minute Revision Guide
> **Exam in 2 days. Use this as your final sweep.** Go unit by unit, skim what you know, drill what's fuzzy.  
> Language: **Java** | Exam: 42 MCQ (90 min) + 4 FRQ (90 min)

---

## 📋 Exam Structure At a Glance

| Section | Format | Time | Weight |
|---|---|---|---|
| Section I | 42 Multiple Choice | 90 min | 55% |
| Section II | 4 Free Response | 90 min | 45% |

**FRQ Breakdown:**
- Q1: Methods and Control Structures (7 pts)
- Q2: Class Design (7 pts)
- Q3: Data Analysis with ArrayList (5 pts)
- Q4: 2D Array (6 pts)

**Unit Exam Weights:**
- Unit 1: Using Objects and Methods → **15–25%**
- Unit 2: Selection and Iteration → **25–35%**
- Unit 3: Class Creation → **10–18%**
- Unit 4: Data Collections → **30–40%**

---

# UNIT 1: Using Objects and Methods (15–25%)

---

## 1.1 Introduction to Algorithms, Programming, and Compilers

**Key Points:**
- An **algorithm** is a step-by-step process for solving a problem — finite, unambiguous, and effective.
- Java is a **compiled language**: source code (.java) → compiled to bytecode (.class) → run by JVM.
- Syntax errors are caught at **compile time**; logic errors only show at **runtime**.

**Do's:**
- Think through your algorithm on paper before coding in FRQs.
- Use pseudocode to plan logic before writing Java.

**Don'ts:**
- Don't confuse compilation errors (typos, missing semicolons) with runtime errors (divide by zero, null pointer).

---

## 1.2 Variables and Data Types

**Key Points:**
- **Primitive types tested:** `int`, `double`, `boolean`
- `int` stores whole numbers (−2,147,483,648 to 2,147,483,647)
- `double` stores decimals
- `boolean` stores `true` or `false`
- Variable declaration: `int x = 5;`

**Example:**
```java
int age = 17;
double gpa = 3.85;
boolean isPassing = true;
```

**Do's:**
- Always initialize variables before use.
- Use `double` when division might produce a decimal.

**Don'ts:**
- Don't use `int` where decimal precision is needed.
- Don't declare a variable without a type (`x = 5` won't compile).

---

## 1.3 Expressions and Output

**Key Points:**
- Arithmetic operators: `+`, `-`, `*`, `/`, `%`
- Integer division truncates: `7 / 2 = 3` (not 3.5)
- Modulo `%` gives the remainder: `7 % 2 = 1`
- `System.out.println()` prints with newline; `System.out.print()` does not.
- String concatenation: `"Score: " + score`

**Example:**
```java
System.out.println(7 / 2);    // prints 3
System.out.println(7 % 2);    // prints 1
System.out.println(7.0 / 2);  // prints 3.5
int x = 5;
System.out.println("x = " + x); // prints x = 5
```

**Do's:**
- Watch out for integer vs. double division in MCQ tracing questions.
- Remember: `"" + 1 + 2` → `"12"`, but `1 + 2 + ""` → `"3"`.

**Don'ts:**
- Don't expect `5 / 2` to give `2.5` — it gives `2`.
- Don't forget that `%` on negatives can be tricky: `-7 % 2 = -1` in Java.

---

## 1.4 Assignment Statements and Input

**Key Points:**
- Assignment uses `=` (not `==`)
- Right side is evaluated first, then stored into variable on left.
- `Scanner` is used for input (not heavily tested, but know it exists).

**Example:**
```java
int x = 10;
x = x + 5;  // x is now 15
int a = 3, b = 4;
a = b;      // a is now 4, b is still 4
```

**Do's:**
- Trace through assignments step by step in MCQ.

**Don'ts:**
- Don't confuse `=` (assignment) with `==` (equality check).

---

## 1.5 Casting and Range of Variables

**Key Points:**
- **Widening cast** (automatic): `int → double`
- **Narrowing cast** (explicit): `(int) 3.9 → 3` (truncates, does NOT round)
- Integer overflow: if you exceed `int` range, it wraps around.

**Example:**
```java
double d = 9.99;
int i = (int) d;       // i = 9, not 10!
int j = (int)(d + 0.5); // rounding trick → j = 10

double result = (double) 7 / 2; // 3.5 — cast before dividing!
double wrong  = (double)(7 / 2); // 3.0 — too late, division already happened
```

**Do's:**
- Cast `(double)` before division if you want a decimal result.
- Know that casting truncates (chops decimals), not rounds.

**Don'ts:**
- Don't cast the result of integer division — cast the operand first.
- Don't assume `(int) 3.9 == 4`.

---

## 1.6 Compound Assignment Operators

**Key Points:**
- `x += 5` is shorthand for `x = x + 5`
- `x -= 3`, `x *= 2`, `x /= 4`, `x %= 3`
- `x++` increments by 1; `x--` decrements by 1.

**Example:**
```java
int x = 10;
x += 3;   // x = 13
x *= 2;   // x = 26
x--;      // x = 25
```

**Don'ts:**
- Don't use `++x` vs `x++` in complex expressions on the AP exam — keep it simple.

---

## 1.7 API and Libraries

**Key Points:**
- An **API** is a set of pre-built classes and methods you can call.
- The AP exam provides a **Java Quick Reference** sheet listing key methods.
- You don't need to memorize exact signatures — the reference sheet is given.

**Do's:**
- Familiarize yourself with the Quick Reference layout so you can find methods fast during the exam.

---

## 1.8 Documentation with Comments

**Key Points:**
- Single-line comment: `// this is a comment`
- Multi-line comment: `/* ... */`
- Javadoc comment: `/** ... */`
- Comments are ignored by the compiler.

**Do's:**
- In FRQs, write brief comments to clarify your logic — graders appreciate it and it won't hurt.

---

## 1.9 Method Signatures

**Key Points:**
- A method signature includes: **access modifier, return type, method name, parameter list**
- `public int add(int a, int b)` — returns int, takes two ints
- `public void printName(String name)` — returns nothing, takes a String
- **Overloading:** two methods can have the same name but different parameter lists.

**Example:**
```java
public int square(int n) { return n * n; }
public double square(double n) { return n * n; } // overloaded
```

**Don'ts:**
- Don't confuse method signature (declaration line) with the method body.
- Overloaded methods differ by parameter type/count, NOT return type alone.

---

## 1.10 Calling Class (Static) Methods

**Key Points:**
- Static methods are called on the **class**, not an object: `ClassName.methodName()`
- No object needed.

**Example:**
```java
int result = Math.abs(-5);    // calling static method
double r = Math.random();      // returns 0.0 ≤ r < 1.0
```

---

## 1.11 Math Class

**Key Points — Commonly Tested Methods:**

| Method | Description | Example |
|---|---|---|
| `Math.abs(x)` | Absolute value | `Math.abs(-3)` → `3` |
| `Math.pow(base, exp)` | Power | `Math.pow(2, 3)` → `8.0` |
| `Math.sqrt(x)` | Square root | `Math.sqrt(16)` → `4.0` |
| `Math.random()` | Random double [0.0, 1.0) | varies |
| `Math.min(a, b)` | Smaller of two | `Math.min(3,7)` → `3` |
| `Math.max(a, b)` | Larger of two | `Math.max(3,7)` → `7` |

**Random number in range [min, max]:**
```java
int rand = (int)(Math.random() * (max - min + 1)) + min;
// e.g., random 1–6 die:
int die = (int)(Math.random() * 6) + 1;
```

**Do's:**
- Know `Math.random()` returns [0.0, 1.0) — never exactly 1.0.
- `Math.pow` always returns `double`.

---

## 1.12 Objects: Instances of Classes

**Key Points:**
- A **class** is a blueprint; an **object** is an instance of that class.
- Objects have **state** (instance variables) and **behavior** (methods).
- Reference variables store the **address** of an object, not the object itself.

---

## 1.13 Object Creation and Storage (Instantiation)

**Key Points:**
- Create objects with `new`: `ClassName obj = new ClassName(args);`
- `null` means a reference variable points to no object.
- Two references can point to the same object.

**Example:**
```java
String s = new String("hello"); // or just String s = "hello";
String a = s;    // a and s point to the SAME object
a = null;        // a points to nothing; s still valid
```

**Don'ts:**
- Don't call methods on a `null` reference — causes `NullPointerException`.

---

## 1.14 Calling Instance Methods

**Key Points:**
- Call on an object: `objectName.methodName(args)`
- The object must be instantiated first.

**Example:**
```java
String name = "Alice";
int len = name.length();    // 5
String upper = name.toUpperCase(); // "ALICE"
```

---

## 1.15 String Manipulation

**Key Points — Must-Know String Methods:**

| Method | Description | Example |
|---|---|---|
| `s.length()` | Number of chars | `"hello".length()` → `5` |
| `s.substring(i)` | From index i to end | `"hello".substring(2)` → `"llo"` |
| `s.substring(i, j)` | From i (inclusive) to j (exclusive) | `"hello".substring(1,3)` → `"el"` |
| `s.indexOf("x")` | First index of x, -1 if not found | `"hello".indexOf("l")` → `2` |
| `s.equals("x")` | Compares content | `"hi".equals("hi")` → `true` |
| `s.compareTo("x")` | Lexicographic compare | negative/0/positive |
| `s.toUpperCase()` | All caps | `"hi".toUpperCase()` → `"HI"` |
| `s.toLowerCase()` | All lowercase | `"HI".toLowerCase()` → `"hi"` |

**String indexing starts at 0:**
```
"LMNOP"
 01234
"LMNOP".substring(3)     → "OP"
"LMNOP".substring(2, 3)  → "N"
```

**Strings are IMMUTABLE** — methods return new strings, they don't modify the original.

**Do's:**
- Always use `.equals()` to compare String content — never `==`.
- `==` on Strings compares references (memory address), not characters.

**Don'ts:**
- Don't use `s == "hello"` — use `s.equals("hello")`.
- Don't modify a String in place — you must reassign: `s = s + "!"`.

---

# UNIT 2: Selection and Iteration (25–35%)

---

## 2.1 Algorithms with Selection and Repetition

**Key Points:**
- Selection = `if/else` — choosing which path to take.
- Repetition = loops — repeating a block of code.
- All algorithms are built from these two building blocks plus sequence.

---

## 2.2 Boolean Expressions

**Key Points:**
- A boolean expression evaluates to `true` or `false`.
- Comparison operators: `==`, `!=`, `<`, `>`, `<=`, `>=`
- Logical operators: `&&` (AND), `||` (OR), `!` (NOT)

**Truth Table:**

| A | B | A && B | A \|\| B | !A |
|---|---|---|---|---|
| T | T | T | T | F |
| T | F | F | T | F |
| F | T | F | T | T |
| F | F | F | F | T |

**Short-circuit evaluation:**
- `&&`: if left is `false`, right is NOT evaluated.
- `||`: if left is `true`, right is NOT evaluated.

---

## 2.3 if Statements

**Key Points:**
- `if`, `if-else`, `if-else if-else` chains
- Only one branch executes.

**Example:**
```java
int score = 85;
if (score >= 90) {
    System.out.println("A");
} else if (score >= 80) {
    System.out.println("B");   // this prints
} else {
    System.out.println("C");
}
```

**Do's:**
- Always use braces `{}` even for single-line bodies (prevents bugs).

---

## 2.4 Nested if Statements

**Key Points:**
- An `if` statement inside another `if`.
- The **dangling else** rule: else pairs with the nearest unmatched if.

**Example:**
```java
if (x > 0)
    if (y > 0)
        System.out.println("both positive");
    else
        System.out.println("x positive, y not"); // belongs to inner if
```

**Don'ts:**
- Don't assume indentation determines which `if` an `else` belongs to — Java uses nearest-if rule.

---

## 2.5 Compound Boolean Expressions

**Key Points:**
- Combine multiple conditions: `x > 0 && x < 10`
- **De Morgan's Laws:**
  - `!(A && B)` is equivalent to `!A || !B`
  - `!(A || B)` is equivalent to `!A && !B`

**Example:**
```java
// Check if x is between 1 and 10 inclusive
if (x >= 1 && x <= 10) { ... }

// NOT (hot AND humid) == NOT hot OR NOT humid
!(isHot && isHumid) == !isHot || !isHumid
```

**Do's:**
- Memorize De Morgan's Laws — they appear frequently in MCQ.

---

## 2.6 Comparing Boolean Expressions

**Key Points:**
- Don't write `if (b == true)` — just write `if (b)`.
- Don't write `if (b == false)` — just write `if (!b)`.
- `==` works for comparing boolean primitives, but prefer direct use.

---

## 2.7 while Loops

**Key Points:**
- Condition checked **before** each iteration.
- If condition is false from the start, body never runs.
- Beware of **infinite loops** if condition never becomes false.

**Example:**
```java
int i = 0;
while (i < 5) {
    System.out.println(i);  // prints 0,1,2,3,4
    i++;
}
```

**Do's:**
- Make sure the loop variable changes inside the loop to avoid infinite loops.
- Use while when you don't know how many iterations in advance.

---

## 2.8 for Loops

**Key Points:**
- Structure: `for (initialization; condition; update)`
- All three parts optional (but semicolons required).
- Loop variable is local to the for loop (in standard Java).

**Example:**
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);  // prints 0,1,2,3,4
}

// Count down
for (int i = 10; i >= 0; i--) {
    System.out.println(i);
}
```

**Do's:**
- For standard array traversal: `for (int i = 0; i < arr.length; i++)`
- Know how many times a loop runs: if condition is `i < n` starting at 0, it runs `n` times.

**Don'ts:**
- Don't change the loop variable inside the body unless intentional — it's confusing and error-prone.

---

## 2.9 Implementing Selection and Iteration Algorithms

**Key Points — Common Patterns:**

**Find max in an array:**
```java
int max = arr[0];
for (int i = 1; i < arr.length; i++) {
    if (arr[i] > max) max = arr[i];
}
```

**Sum all elements:**
```java
int sum = 0;
for (int val : arr) sum += val;
```

**Count elements meeting a condition:**
```java
int count = 0;
for (int val : arr) {
    if (val % 2 == 0) count++;
}
```

---

## 2.10 Implementing String Algorithms

**Key Points:**
- Traverse a String character by character using `substring` or `charAt`.
- `s.charAt(i)` returns the `char` at index i.

**Example — count vowels:**
```java
String s = "hello";
int count = 0;
for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);
    if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') count++;
}
```

**Example — reverse a String:**
```java
String reversed = "";
for (int i = s.length() - 1; i >= 0; i--) {
    reversed += s.charAt(i);
}
```

**Do's:**
- Use `charAt(i)` for character access; returns a `char` (use single quotes `'a'`).
- Compare chars with `==` (they're primitives).

---

## 2.11 Nested Iteration

**Key Points:**
- Loop inside a loop.
- Outer loop runs m times, inner loop runs n times → total: m × n iterations.
- Commonly used for 2D arrays and building patterns.

**Example:**
```java
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        System.out.print(i + "" + j + " ");
    }
    System.out.println();
}
// Output:
// 00 01 02
// 10 11 12
// 20 21 22
```

**Do's:**
- Trace carefully in MCQs — keep track of both loop variables.

---

## 2.12 Informal Run-Time Analysis

**Key Points:**
- **O(n)**: single loop through n items — linear time.
- **O(n²)**: nested loop through n items — quadratic time.
- **O(log n)**: halving the problem each step (binary search).
- More iterations = slower. Bigger O = worse performance for large n.

| Algorithm | Time Complexity |
|---|---|
| Linear search | O(n) |
| Binary search | O(log n) |
| Bubble/Selection/Insertion Sort | O(n²) |
| Single traversal | O(n) |

**Do's:**
- Count how many times the main operation runs — that gives you the order.

---

# UNIT 3: Class Creation (10–18%)

---

## 3.1 Abstraction and Program Design

**Key Points:**
- **Abstraction** hides complexity — you use a method without knowing its internals.
- Classes encapsulate data and behavior together.
- Good design: each class has a single, clear purpose.

---

## 3.2 Impact of Program Design

**Key Points:**
- Ethical implications of computing: privacy, data misuse, algorithmic bias.
- Programs can have unintended social consequences.
- Software reliability and bugs can cause real-world harm.

**Do's:**
- For MCQs on ethics/impact, think: who is affected, is data used appropriately, are there biases?

---

## 3.3 Anatomy of a Class

**Key Points:**
- A class contains: **instance variables**, **constructors**, **methods**.
- **Instance variables** store the object's state; declared at class level (not inside a method).
- Use `private` for instance variables to enforce **encapsulation**.

**Structure:**
```java
public class Dog {
    // instance variables
    private String name;
    private int age;

    // constructor
    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // methods
    public String getName() { return name; }
    public int getAge()  { return age; }
}
```

---

## 3.4 Constructors

**Key Points:**
- Constructors have the **same name as the class** and **no return type** (not even void).
- Called when creating an object with `new`.
- If no constructor defined, Java gives a default no-arg constructor.
- You can overload constructors (multiple constructors, different parameters).

**Example:**
```java
public class Point {
    private int x, y;

    public Point() { x = 0; y = 0; }              // no-arg
    public Point(int x, int y) { this.x = x; this.y = y; } // parameterized
}
```

**Do's:**
- Always initialize ALL instance variables inside the constructor.

**Don'ts:**
- Don't give a constructor a return type — even `void` is wrong.
- Don't forget to use `this.name = name` when parameter name matches instance variable name.

---

## 3.5 Methods: How to Write Them

**Key Points:**
- A method has: access modifier, return type, name, parameters, body.
- `void` methods do NOT use `return value` (can use bare `return;` to exit early).
- Return type must match what you return.

**Example:**
```java
public int add(int a, int b) {
    return a + b;
}

public void greet(String name) {
    System.out.println("Hello, " + name);
}
```

**Do's:**
- Every non-void method must have a `return` statement on every possible path.

**Don'ts:**
- Don't return a value from a `void` method.
- Don't forget `return` in branches of if/else — compiler will catch it, but watch out.

---

## 3.6 Methods: Passing and Returning References

**Key Points:**
- **Primitive parameters**: passed by value — changes inside method don't affect original.
- **Object parameters**: passed by reference — changes to the object's state ARE visible outside.
- You can return objects from methods.

**Example:**
```java
public void increment(int x) { x++; } // no effect on caller's variable

public void addToList(ArrayList<Integer> list) {
    list.add(5); // THIS modifies the caller's list
}
```

**Do's:**
- Know the difference: primitives pass a copy; objects pass a reference (address).

---

## 3.7 Class Variables and Methods (Static)

**Key Points:**
- `static` variables/methods belong to the **class**, not any instance.
- All objects share the same static variable.
- Call static methods via class name: `ClassName.method()`.

**Example:**
```java
public class Counter {
    private static int count = 0; // shared by ALL Counter objects

    public Counter() { count++; }
    public static int getCount() { return count; }
}
```

**Do's:**
- Use static for utility methods that don't need object state (like `Math.sqrt`).

**Don'ts:**
- Don't access instance variables from a static method — they don't belong to any particular object.

---

## 3.8 Scope and Access

**Key Points:**
- **Local variable**: declared inside a method — only accessible within that method.
- **Instance variable**: declared in class body — accessible by all methods in the class.
- **Scope**: the region of code where a variable exists.
- **Access modifiers**: `public` (any class), `private` (this class only).

**Do's:**
- Make instance variables `private` and provide `public` getters/setters (encapsulation).

---

## 3.9 this Keyword

**Key Points:**
- `this` refers to the **current object**.
- Used to distinguish instance variable from parameter with same name.
- Can be used to call another constructor: `this(args)` (not heavily tested).

**Example:**
```java
public class Car {
    private String color;
    public Car(String color) {
        this.color = color; // this.color = instance var; color = parameter
    }
}
```

---

# UNIT 4: Data Collections (30–40%)

---

## 4.1 Ethical and Social Issues Around Data Collection

**Key Points:**
- Collecting data comes with responsibility: privacy, consent, security.
- Big datasets can introduce biases into algorithms.
- Consider: who has access to data, how it's stored, how it's used.

---

## 4.2 Introduction to Using Data Sets

**Key Points:**
- Data sets can be stored in arrays, ArrayLists, or text files.
- Choose the right structure: known fixed size → array; dynamic size → ArrayList.

---

## 4.3 Array Creation and Access

**Key Points:**
- Fixed size, declared with a type and size.
- **0-indexed**: first element is at index 0, last at `arr.length - 1`.
- Accessing out-of-bounds throws `ArrayIndexOutOfBoundsException`.

**Example:**
```java
int[] scores = new int[5];     // array of 5 ints, all initialized to 0
int[] grades = {90, 85, 78, 92, 88}; // initializer list

System.out.println(grades[0]); // 90
System.out.println(grades.length); // 5 (not grades.length())
```

**Do's:**
- Use `.length` (no parentheses) for arrays.
- Initialize array elements explicitly if you need non-default values.

**Don'ts:**
- Don't access `arr[arr.length]` — last valid index is `arr.length - 1`.
- Don't use `.length()` on arrays — that's for Strings.

---

## 4.4 Array Traversals

**Key Points:**
- Standard for loop: `for (int i = 0; i < arr.length; i++)`
- Enhanced for loop (for-each): `for (int val : arr)` — use when you don't need the index.

**Example:**
```java
int[] arr = {1, 2, 3, 4, 5};

// Standard
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}

// Enhanced
for (int val : arr) {
    System.out.println(val);
}
```

**Do's:**
- Use the enhanced for loop for read-only traversal.
- Use standard for loop when you need the index or need to modify elements.

**Don'ts:**
- Don't use enhanced for loop when you need to modify array elements — changes to `val` won't affect the array.

---

## 4.5 Implementing Array Algorithms

**Common Patterns:**

**Find minimum:**
```java
int min = arr[0];
for (int i = 1; i < arr.length; i++) {
    if (arr[i] < min) min = arr[i];
}
```

**Shift elements right (insert at position):**
```java
// Move elements right starting from end
for (int i = arr.length - 1; i > pos; i--) {
    arr[i] = arr[i - 1];
}
arr[pos] = newValue;
```

**Reverse an array:**
```java
for (int i = 0; i < arr.length / 2; i++) {
    int temp = arr[i];
    arr[i] = arr[arr.length - 1 - i];
    arr[arr.length - 1 - i] = temp;
}
```

---

## 4.6 Using Text Files

**Key Points:**
- Files can be used to read/write persistent data.
- Not a major FRQ topic, but may appear in context.

---

## 4.7 Wrapper Classes

**Key Points:**
- Each primitive has a corresponding **wrapper class**: `int → Integer`, `double → Double`.
- **Autoboxing**: automatic conversion from primitive to wrapper (`int → Integer`).
- **Unboxing**: automatic conversion from wrapper to primitive.
- Used because `ArrayList` can only hold objects, not primitives.

**Example:**
```java
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(5);           // autoboxing: 5 (int) → Integer(5)
int x = list.get(0);  // unboxing: Integer(5) → 5
```

**Do's:**
- Use `Integer.parseInt("42")` to convert String to int.
- Use `Double.parseDouble("3.14")` to convert String to double.

---

## 4.8 ArrayList Methods

**Key Points — Must-Know Methods:**

| Method | Description |
|---|---|
| `list.add(obj)` | Appends obj to end |
| `list.add(i, obj)` | Inserts obj at index i, shifts rest |
| `list.get(i)` | Returns element at index i |
| `list.set(i, obj)` | Replaces element at index i, returns old value |
| `list.remove(i)` | Removes element at index i, shifts rest, returns removed |
| `list.size()` | Returns number of elements |

**Example:**
```java
ArrayList<String> names = new ArrayList<String>();
names.add("Alice");   // ["Alice"]
names.add("Bob");     // ["Alice", "Bob"]
names.add(0, "Zara"); // ["Zara", "Alice", "Bob"]
names.remove(1);      // ["Zara", "Bob"]
String s = names.get(0); // "Zara"
names.set(0, "Nia");  // ["Nia", "Bob"]
int n = names.size(); // 2
```

**Do's:**
- Use `.size()` (not `.length`) for ArrayList.

**Don'ts:**
- Don't use index `list.size()` — last valid index is `list.size() - 1`.

---

## 4.9 ArrayList Traversals

**Key Points:**
- Use standard for loop or enhanced for loop.
- **When removing elements**, traverse **backwards** (or use iterator pattern) to avoid skipping.

**Example:**
```java
// Forward traversal
for (int i = 0; i < list.size(); i++) {
    System.out.println(list.get(i));
}

// Enhanced for loop (read only)
for (String s : list) {
    System.out.println(s);
}
```

**Removing during traversal (go backwards):**
```java
for (int i = list.size() - 1; i >= 0; i--) {
    if (list.get(i) < 0) list.remove(i);
}
```

**Do's:**
- Traverse backwards when removing elements to avoid index-shift bugs.

**Don'ts:**
- Don't remove elements while using an enhanced for loop — causes `ConcurrentModificationException`.
- Don't forget that `remove(i)` shifts all elements after i down by one.

---

## 4.10 Implementing ArrayList Algorithms

**Common Patterns:**

**Find all elements matching a condition:**
```java
ArrayList<Integer> evens = new ArrayList<Integer>();
for (int val : original) {
    if (val % 2 == 0) evens.add(val);
}
```

**Remove duplicates of a specific value:**
```java
for (int i = list.size() - 1; i >= 0; i--) {
    if (list.get(i).equals(target)) list.remove(i);
}
```

---

## 4.11 2D Array Creation and Access

**Key Points:**
- A 2D array is an array of arrays.
- Declaration: `int[][] grid = new int[rows][cols];`
- Access: `grid[row][col]`
- `grid.length` = number of rows; `grid[0].length` = number of columns.

**Example:**
```java
int[][] matrix = new int[3][4]; // 3 rows, 4 columns
matrix[0][0] = 1;
matrix[2][3] = 9;

// Initializer
int[][] grid = {{1,2,3},{4,5,6},{7,8,9}};
System.out.println(grid[1][2]); // 6
```

---

## 4.12 2D Array Traversals

**Key Points:**
- **Row-major order**: outer loop = rows, inner loop = columns (standard).
- **Column-major order**: outer loop = columns, inner loop = rows.

**Example:**
```java
for (int row = 0; row < grid.length; row++) {
    for (int col = 0; col < grid[0].length; col++) {
        System.out.print(grid[row][col] + " ");
    }
    System.out.println();
}
```

**Do's:**
- Use `grid.length` for rows and `grid[0].length` for columns.

---

## 4.13 Implementing 2D Array Algorithms

**Common Patterns:**

**Sum all elements:**
```java
int sum = 0;
for (int[] row : grid) {
    for (int val : row) {
        sum += val;
    }
}
```

**Find max in 2D array:**
```java
int max = grid[0][0];
for (int[] row : grid) {
    for (int val : row) {
        if (val > max) max = val;
    }
}
```

---

## 4.14 Searching Algorithms

### Linear Search
- Checks each element one by one.
- Works on **unsorted** or sorted arrays.
- Time complexity: **O(n)**.

```java
public static int linearSearch(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) return i;
    }
    return -1; // not found
}
```

### Binary Search
- Requires a **sorted** array.
- Repeatedly halves the search space.
- Time complexity: **O(log n)** — much faster for large arrays.

```java
public static int binarySearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

**Do's:**
- Binary search only works on SORTED data.
- Know which is faster: binary search for large sorted arrays.

**Don'ts:**
- Don't apply binary search to an unsorted array.

---

## 4.15 Sorting Algorithms

### Selection Sort
- Find the minimum, swap it to the front. Repeat.
- Time complexity: **O(n²)**.

```java
for (int i = 0; i < arr.length - 1; i++) {
    int minIdx = i;
    for (int j = i + 1; j < arr.length; j++) {
        if (arr[j] < arr[minIdx]) minIdx = j;
    }
    int temp = arr[i];
    arr[i] = arr[minIdx];
    arr[minIdx] = temp;
}
```

### Insertion Sort
- Build sorted portion one element at a time by inserting each into its correct position.
- Time complexity: **O(n²)** worst case, **O(n)** best case (already sorted).

```java
for (int i = 1; i < arr.length; i++) {
    int key = arr[i];
    int j = i - 1;
    while (j >= 0 && arr[j] > key) {
        arr[j + 1] = arr[j];
        j--;
    }
    arr[j + 1] = key;
}
```

**Do's:**
- Know both sort algorithms and be able to trace them on paper.
- Know that both are O(n²) — slower than merge sort, but AP CS A only tests these two in detail.

---

## 4.16 Recursion

**Key Points:**
- A method that calls itself.
- Must have a **base case** (stops recursion) and a **recursive case** (calls itself with a simpler problem).
- Without a base case → **stack overflow**.

**Structure:**
```java
public static int factorial(int n) {
    if (n == 0) return 1;          // base case
    return n * factorial(n - 1);   // recursive case
}
```

**Example — Fibonacci:**
```java
public static int fib(int n) {
    if (n <= 1) return n;           // base case
    return fib(n - 1) + fib(n - 2); // recursive case
}
```

**Tracing recursion:**
```
factorial(4)
= 4 * factorial(3)
= 4 * 3 * factorial(2)
= 4 * 3 * 2 * factorial(1)
= 4 * 3 * 2 * 1 * factorial(0)
= 4 * 3 * 2 * 1 * 1 = 24
```

**Do's:**
- Always identify the base case first.
- Trace calls by substituting and unwinding.

**Don'ts:**
- Don't write recursion without a base case.
- Don't assume recursion is always more efficient — factorial is fine, but naive Fibonacci is exponential.

---

## 4.17 Recursive Searching and Sorting

**Binary Search (Recursive):**
```java
public static int binarySearch(int[] arr, int target, int low, int high) {
    if (low > high) return -1;       // base case: not found
    int mid = (low + high) / 2;
    if (arr[mid] == target) return mid;
    else if (arr[mid] < target) return binarySearch(arr, target, mid+1, high);
    else return binarySearch(arr, target, low, mid-1);
}
```

**Merge Sort (concept):**
- Divide array in half, sort each half recursively, then merge.
- Time complexity: **O(n log n)** — significantly faster than O(n²) sorts.
- You should know the concept; implementation won't be on the AP exam in full.

---

# ⚡ Quick Reference — Things That Commonly Trip Students Up

## Operator Precedence (high → low)
1. `!` (NOT)
2. `*`, `/`, `%`
3. `+`, `-`
4. `<`, `>`, `<=`, `>=`
5. `==`, `!=`
6. `&&`
7. `||`
8. `=` (assignment)

## Common Gotchas

| Gotcha | Wrong | Right |
|---|---|---|
| String comparison | `s == "hello"` | `s.equals("hello")` |
| Array length | `arr.length()` | `arr.length` |
| ArrayList size | `list.length` | `list.size()` |
| Last array index | `arr[arr.length]` | `arr[arr.length - 1]` |
| Integer division | `7 / 2 = 3.5` | `7 / 2 = 3` |
| Casting | `(int) 3.9 = 4` | `(int) 3.9 = 3` |
| Null reference | calling methods on null | always check for null first |
| Off-by-one | `i <= arr.length` | `i < arr.length` |

---

# 🎯 FRQ Strategy

## General Tips
1. **Write something** — partial credit is real. Even a method signature earns a point.
2. **Don't leave blanks** — an incorrect answer doesn't cost extra; a blank always costs.
3. **Use the Java Quick Reference** — it's provided, use it.
4. **Use proper Java syntax** — missing semicolons, wrong brackets lose points.
5. **Trace your code** — re-read what you wrote and mentally run it with a test case.

## Q1: Methods and Control Structures
- You'll write a method (or two) using loops, conditionals, and possibly String manipulation.
- Look for: traversal patterns, accumulator patterns, conditional logic.

## Q2: Class Design
- Write a complete class with instance variables, constructor(s), and methods.
- Checklist: `private` instance variables, constructor assigns all variables, getters/setters if needed, `this.` when parameter names match instance variable names.

## Q3: Data Analysis with ArrayList
- You'll traverse, filter, or modify an ArrayList.
- Key: traverse backwards when removing, use `.size()` and `.get()` correctly.

## Q4: 2D Array
- Row-major traversal, finding values, modifying specific cells.
- Key: outer loop = rows (`grid.length`), inner loop = cols (`grid[0].length`).

---

# 📝 Java Quick Reference Cheat Sheet

## String Methods
```java
int length()                   // s.length()
String substring(int from)     // s.substring(2) → from index 2 to end
String substring(int from, int to) // s.substring(1,3) → indices 1,2
int indexOf(String str)        // first occurrence, -1 if not found
boolean equals(String other)   // content equality
int compareTo(String other)    // <0, 0, >0
```

## Math Methods
```java
static int abs(int x)
static double abs(double x)
static double pow(double base, double exp)
static double sqrt(double x)
static double random()    // [0.0, 1.0)
static int max(int a, int b)
static int min(int a, int b)
```

## ArrayList<E> Methods
```java
boolean add(E obj)            // appends to end
void add(int index, E obj)    // inserts at index
E get(int index)              // returns element
E set(int index, E obj)       // replaces, returns old
E remove(int index)           // removes, shifts, returns removed
int size()                    // number of elements
```

---

# 🧠 Final Day-Before Reminders

- **String is immutable** — every method returns a new String.
- **Arrays use `.length`**, ArrayList uses `.size()`.
- **`==` vs `.equals()`** — use `.equals()` for objects (String, Integer, etc.).
- **Integer division truncates** — cast to double before dividing if you need decimals.
- **Casting truncates** — `(int) 3.9 → 3`, not 4.
- **Recursion needs a base case** — always.
- **Remove from ArrayList while traversing → go backwards**.
- **Binary search requires sorted array**.
- **Static methods** called on class; **instance methods** called on object.
- **`this.`** disambiguates when parameter and instance variable share a name.
- **Constructors have no return type** (not even void).

---

*Good luck on the exam! You've got this. 🚀*

*Sources: AP Computer Science A Course and Exam Description (CED), Course Overview, Course at a Glance — College Board © 2025*
