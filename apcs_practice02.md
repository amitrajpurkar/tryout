# AP Computer Science A — Practice Exam 02
### 🟠 Difficulty: Tricky & Conceptual | Full Mock Exam

> **Format:** Section I — 42 Multiple Choice (90 min) | Section II — 4 Free Response (90 min)  
> **Total Time:** 3 hours  
> ⚠️ This exam is specifically designed around **common misconceptions, subtle language traps, and counterintuitive Java behavior**. Every wrong answer choice is a plausible mistake.

---

# SECTION I — Multiple Choice (42 Questions, 90 Minutes)

---

**Question 1**

What is the value of `x` after the following executes?

```java
int x = 5;
int y = x;
y = 10;
System.out.println(x);
```

(A) `5`  
(B) `10`  
(C) `15`  
(D) `0`  

> *Trap: Students confuse primitive assignment (copy) with object reference sharing.*

---

**Question 2**

What is printed?

```java
System.out.println(1 + 2 + "3");
System.out.println("1" + 2 + 3);
```

(A) `33` and `123`  
(B) `33` and `15`  
(C) `123` and `123`  
(D) `6` and `15`  

> *Trap: String concatenation vs addition depends on order and left-to-right evaluation.*

---

**Question 3**

What is the output?

```java
double d = 1.0 / 3.0 * 3.0;
if (d == 1.0)
    System.out.println("equal");
else
    System.out.println("not equal");
```

(A) `equal`  
(B) `not equal`  
(C) A compile error occurs  
(D) An exception is thrown  

> *Trap: Floating-point arithmetic is imprecise — `1.0/3.0*3.0` may not exactly equal `1.0`.*

---

**Question 4**

Consider the following. What is the output?

```java
int x = 3;
if (x > 2)
    System.out.println("A");
    System.out.println("B");
```

(A) `A`  
(B) `B`  
(C) `A` then `B`  
(D) Neither A nor B  

> *Trap: Without braces, only the first statement is inside the if. `println("B")` always runs.*

---

**Question 5**

What is printed?

```java
for (int i = 0; i < 5; i++) {
    if (i == 3) continue;
    System.out.print(i + " ");
}
```

(A) `0 1 2 4`  
(B) `0 1 2`  
(C) `0 1 2 3 4`  
(D) `0 1 2 4 ` *(with trailing space)*  

> *Trap: `continue` skips the rest of the loop body for that iteration but does NOT exit the loop.*

---

**Question 6**

Which of the following will cause a compile error?

**(A)** `int x = (int) 3.9;`  
**(B)** `double d = 5;`  
**(C)** `int y = 3.9;`  
**(D)** `double e = (double) 5;`  

> *Trap: Widening conversions (int→double) are implicit; narrowing (double→int) requires explicit cast.*

---

**Question 7**

What is the output?

```java
String s = "hello";
s.toUpperCase();
System.out.println(s);
```

(A) `HELLO`  
(B) `hello`  
(C) A compile error occurs  
(D) `Hello`  

> *Trap: Strings are immutable. `toUpperCase()` returns a NEW String; the original is unchanged.*

---

**Question 8**

What is the value of `result` after this code?

```java
int result = 10;
result /= 3;
System.out.println(result);
```

(A) `3.33`  
(B) `3`  
(C) `3.0`  
(D) `4`  

> *Trap: `result` is an `int`. Integer division truncates. `/=` does not produce a double.*

---

**Question 9**

Consider:

```java
boolean a = true;
boolean b = false;
System.out.println(a || b && !a);
```

What is printed?

(A) `false`  
(B) `true`  
(C) A compile error  
(D) `0`  

> *Trap: Operator precedence — `!` > `&&` > `||`. So this is `a || (b && (!a))` = `true || (false && false)` = `true`.*

---

**Question 10**

What does the following print?

```java
int x = 0;
while (x++ < 3) {
    System.out.print(x + " ");
}
```

(A) `0 1 2 `  
(B) `1 2 3 `  
(C) `0 1 2 3 `  
(D) `1 2 3 4 `  

> *Trap: `x++` is post-increment — condition is checked BEFORE increment, but `x` is already incremented when used in the body.*

---

**Question 11**

What is printed?

```java
int[] arr = {1, 2, 3, 4, 5};
for (int val : arr) {
    val *= 2;
}
System.out.println(arr[2]);
```

(A) `6`  
(B) `3`  
(C) `2`  
(D) `0`  

> *Trap: Enhanced for loop copies the value into `val`. Modifying `val` does NOT change the array.*

---

**Question 12**

What is the output?

```java
String s1 = new String("AP");
String s2 = new String("AP");
System.out.println(s1 == s2);
System.out.println(s1.equals(s2));
```

(A) `true` then `true`  
(B) `false` then `false`  
(C) `false` then `true`  
(D) `true` then `false`  

> *Trap: `==` compares object references (different objects → false). `.equals()` compares content.*

---

**Question 13**

Consider this code. What is printed?

```java
int[] a = {1, 2, 3};
int[] b = a;
b[0] = 99;
System.out.println(a[0]);
```

(A) `1`  
(B) `99`  
(C) `0`  
(D) A runtime error  

> *Trap: Arrays are objects. `b = a` makes both variables point to the SAME array. Changing `b[0]` changes `a[0]`.*

---

**Question 14**

What is the output?

```java
int sum = 0;
for (int i = 1; i <= 10; i++);
{
    sum += i; // Note: this line is OUTSIDE the loop
}
System.out.println(sum);
```

(A) `55`  
(B) `10`  
(C) A compile error  
(D) `0`  

> *Trap: There's a semicolon after the for-loop header. The loop body is empty. `i` is out of scope in the block below → compile error.*

---

**Question 15**

What is the output?

```java
public static int add(int a, int b) {
    return a + b;
    System.out.println("done");
}
```

(A) This method returns the sum and prints "done".  
(B) This is a compile error — unreachable statement.  
(C) This prints "done" and then returns the sum.  
(D) This runs fine but "done" is never printed.  

> *Trap: Any code after a `return` in the same block is unreachable — compile error.*

---

**Question 16**

What is the value of `x` after this code runs?

```java
int x = 5;
int y = ++x * 2;
```

(A) `x = 5`  
(B) `x = 6`  
(C) `x = 10`  
(D) `x = 12`  

> *Trap: `++x` is pre-increment — `x` becomes 6 BEFORE the multiplication. So `y = 12`, `x = 6`.*

---

**Question 17**

What is output by the following?

```java
ArrayList<Integer> list = new ArrayList<>();
list.add(1);
list.add(2);
list.add(3);
list.remove(1);
System.out.println(list);
```

(A) `[1, 3]`  
(B) `[2, 3]`  
(C) `[1, 2]`  
(D) `[1, 2, 3]`  

> *Trap: `list.remove(1)` removes the element at **index** 1 (which is `2`), not the element with **value** 1.*

---

**Question 18**

What is the output?

```java
int n = 5;
int result = 1;
do {
    result *= n;
    n--;
} while (n > 5);
System.out.println(result);
```

(A) `120`  
(B) `0`  
(C) `5`  
(D) Infinite loop  

> *Trap: `do-while` always executes at least once. After one iteration, `n = 4`, condition `4 > 5` is false → loop ends. Result = 5.*

---

**Question 19**

What is printed?

```java
String word = "computer";
System.out.println(word.substring(3, 3));
```

(A) `"put"`  
(B) `""`  
(C) `"p"`  
(D) A runtime error  

> *Trap: `substring(3, 3)` — from index 3 to index 3 is empty. Returns `""`, not an error.*

---

**Question 20**

What is the output of the following?

```java
int x = 7;
System.out.println(x > 5 ? x > 10 ? "big" : "medium" : "small");
```

(A) `big`  
(B) `medium`  
(C) `small`  
(D) A compile error  

> *Trap: Nested ternary. `x > 5` is true → evaluate `x > 10` → false → returns `"medium"`.*

---

**Question 21**

Consider:

```java
public class Counter {
    private int n;
    public Counter(int start) { n = start; }
    public void increment() { n++; }
    public int get() { return n; }
}
```

What is printed?

```java
Counter c = new Counter(0);
for (int i = 0; i < 3; i++) {
    Counter d = c;
    d.increment();
}
System.out.println(c.get());
```

(A) `0`  
(B) `1`  
(C) `3`  
(D) `9`  

> *Trap: `d = c` — both point to the same object. Each `d.increment()` modifies `c`'s state.*

---

**Question 22**

Which expression evaluates to `true` when `x = 5`?

(A) `x > 3 && x < 4`  
(B) `!(x == 5)`  
(C) `x != 5 || x > 4`  
(D) `x >= 6 || x <= 4`  

> *Trap: (C) — `x != 5` is false but `x > 4` is true → `false || true` = `true`.*

---

**Question 23**

What is the output?

```java
int[] arr = new int[3];
System.out.println(arr[0] + " " + arr[1] + " " + arr[2]);
```

(A) `null null null`  
(B) `0 0 0`  
(C) A runtime error  
(D) `1 2 3`  

> *Trap: `int` arrays are initialized to `0` by default (not null — that's for object arrays).*

---

**Question 24**

What is printed?

```java
for (int i = 10; i >= 1; i = i / 2) {
    System.out.print(i + " ");
}
```

(A) `10 5 2 1`  
(B) `10 5 2 1 0`  
(C) Infinite loop  
(D) `10 5 2`  

> *Trap: When `i = 1`, `1 / 2 = 0` in integer division. Then condition `0 >= 1` is false → stops. Prints `10 5 2 1`.*

---

**Question 25**

What is the output?

```java
System.out.println(Math.abs(-3.7));
System.out.println((int) Math.abs(-3.7));
```

(A) `3.7` then `4`  
(B) `3.7` then `3`  
(C) `-3.7` then `-3`  
(D) `4.0` then `4`  

> *Trap: `Math.abs(-3.7)` = `3.7`. Casting to `int` truncates → 3, not 4.*

---

**Question 26**

Consider the following:

```java
public static boolean isEven(int n) {
    if (n % 2 == 0)
        return true;
    else
        return false;
}
```

Which of the following is an equivalent, simpler implementation?

(A) `return n % 2;`  
(B) `return n / 2 == 0;`  
(C) `return n % 2 == 0;`  
(D) `return !n % 2;`  

> *Trap: (A) returns int (not boolean), (B) is wrong logic, (D) syntax error. Only (C) is correct.*

---

**Question 27**

What is printed?

```java
int x = 2;
switch (x) {
    case 1: System.out.print("one ");
    case 2: System.out.print("two ");
    case 3: System.out.print("three ");
    default: System.out.print("other");
}
```

(A) `two`  
(B) `two three other`  
(C) `one two three other`  
(D) `other`  

> *Trap: Without `break` statements, switch falls through all subsequent cases.*

---

**Question 28**

Consider:

```java
String s = null;
System.out.println(s.length());
```

What happens?

(A) Prints `0`  
(B) Prints `null`  
(C) A compile error occurs  
(D) A `NullPointerException` is thrown at runtime  

> *Trap: `null` compiles fine as a String variable, but calling a method on `null` causes NullPointerException at runtime.*

---

**Question 29**

What does the following print?

```java
int count = 0;
for (int i = 0; i < 10; i++) {
    for (int j = 0; j < 10; j++) {
        if (i == j) count++;
    }
}
System.out.println(count);
```

(A) `100`  
(B) `0`  
(C) `10`  
(D) `1`  

> *Trap: The condition `i == j` is true exactly 10 times (when i=j=0, 1, 2, ..., 9).*

---

**Question 30**

Consider the recursive method:

```java
public static int sum(int n) {
    if (n == 1) return 1;
    return n + sum(n - 1);
}
```

What happens if you call `sum(0)`?

(A) Returns `0`  
(B) Returns `1`  
(C) A compile error  
(D) Infinite recursion leading to a `StackOverflowError`  

> *Trap: The base case is `n == 1`. With `n = 0`, it recurses to `sum(-1)`, then `sum(-2)`, forever.*

---

**Question 31**

What is the output?

```java
int[] arr = {10, 20, 30, 40, 50};
System.out.println(arr[arr.length / 2]);
```

(A) `20`  
(B) `30`  
(C) `25`  
(D) `40`  

> *Trap: `arr.length = 5`, `5 / 2 = 2` (integer division), so `arr[2] = 30`.*

---

**Question 32**

What is printed?

```java
ArrayList<String> list = new ArrayList<>();
list.add("X");
list.add("Y");
list.add("Z");
list.add(0, "A");
System.out.println(list.get(2));
```

(A) `Y`  
(B) `Z`  
(C) `X`  
(D) `A`  

> *Trap: `add(0, "A")` inserts at index 0 and shifts everything right. List becomes ["A","X","Y","Z"]. `get(2)` = "Y".*

---

**Question 33**

Consider the following method that is supposed to find the index of the max element:

```java
public static int maxIndex(int[] arr) {
    int maxIdx = 0;
    for (int i = 0; i <= arr.length; i++) {
        if (arr[i] > arr[maxIdx]) maxIdx = i;
    }
    return maxIdx;
}
```

What is wrong with this method?

(A) It does not correctly compare elements.  
(B) It returns the value, not the index.  
(C) It throws `ArrayIndexOutOfBoundsException` when `i == arr.length`.  
(D) Nothing — it works correctly.  

> *Trap: Loop condition `i <= arr.length` goes one past the last valid index.*

---

**Question 34**

What is the output?

```java
System.out.println("hello".substring(0, 5));
System.out.println("hello".substring(5));
```

(A) `hello` and runtime error  
(B) `hello` and `""`  
(C) `hell` and `o`  
(D) Compile error  

> *Trap: `substring(0, 5)` of a 5-character string is the full string. `substring(5)` on a 5-char string returns `""`, not an error.*

---

**Question 35**

What is printed?

```java
int a = 3, b = 4;
if (a++ > 3 && b-- < 4) {
    System.out.println("yes");
} else {
    System.out.println("no");
}
System.out.println(a + " " + b);
```

(A) `yes` then `4 3`  
(B) `no` then `4 4`  
(C) `no` then `4 3`  
(D) `yes` then `3 4`  

> *Trap: `a++` is post-increment — evaluates as `3 > 3` which is **false**. Short-circuit: `b--` is NOT evaluated. `a = 4`, `b = 4` (unchanged).*

---

**Question 36**

Which of the following correctly declares a 2D array with 4 rows and 3 columns, and sets all values to 1?

**(A)**
```java
int[][] grid = new int[3][4];
for (int[] row : grid)
    for (int val : row) val = 1;
```

**(B)**
```java
int[][] grid = new int[4][3];
for (int i = 0; i < grid.length; i++)
    for (int j = 0; j < grid[0].length; j++)
        grid[i][j] = 1;
```

**(C)**
```java
int[][] grid = new int[4][3];
for (int[] row : grid)
    for (int val : row) val = 1;
```

**(D)**
```java
int[4][3] grid;
```

> *Trap: (A) has wrong dimensions [3][4]. (C) uses enhanced for loop to "set" values — won't work. (B) is the only correct one.*

---

**Question 37**

What is returned by `mystery("racecar")`?

```java
public static boolean mystery(String s) {
    for (int i = 0; i < s.length() / 2; i++) {
        if (s.charAt(i) != s.charAt(s.length() - 1 - i)) return false;
    }
    return true;
}
```

(A) `false`  
(B) `true`  
(C) A runtime error  
(D) Compile error  

> *This checks for a palindrome. "racecar" is a palindrome → `true`. Testing: r==r, a==a, c==c (center skipped).*

---

**Question 38**

What is the output?

```java
int x = 5;
int y = 3;
int z = x-- - --y;
System.out.println(x + " " + y + " " + z);
```

(A) `4 2 3`  
(B) `5 3 2`  
(C) `4 2 2`  
(D) `4 3 2`  

> *Trap: `x--` = post-decrement (uses 5, then x becomes 4). `--y` = pre-decrement (y becomes 2, uses 2). z = 5 - 2 = 3. Result: x=4, y=2, z=3.*

---

**Question 39**

Consider the following:

```java
public class Person {
    private String name;
    public Person(String name) { this.name = name; }
    public String getName() { return name; }
}
```

What is printed?

```java
Person p1 = new Person("Alice");
Person p2 = new Person("Alice");
System.out.println(p1 == p2);
System.out.println(p1.getName() == p2.getName());
System.out.println(p1.getName().equals(p2.getName()));
```

(A) `false false true`  
(B) `true true true`  
(C) `false true true`  
(D) `false false false`  

> *Trap: `p1 == p2` → false (different objects). `p1.getName() == p2.getName()` — tricky! String literals may be interned. Since "Alice" is a literal, JVM may intern it → `true`. But this is implementation-dependent. On the AP exam, string literals created at compile time are typically interned → **true**. `equals` → true.*

---

**Question 40**

What is the output?

```java
int total = 0;
for (int i = 1; i <= 100; i++) {
    total += i;
    if (total > 50) break;
}
System.out.println(total);
```

(A) `50`  
(B) `5050`  
(C) `55`  
(D) `56`  

> *Trace: 1+2+...+9=45, +10=55. 55 > 50 → break. Output: 55.*

---

**Question 41**

What is the output?

```java
public static void tricky(int n, int[] arr) {
    n = 99;
    arr[0] = 99;
}

int x = 1;
int[] a = {1, 2, 3};
tricky(x, a);
System.out.println(x + " " + a[0]);
```

(A) `99 99`  
(B) `1 1`  
(C) `1 99`  
(D) `99 1`  

> *Trap: `n = 99` has no effect on `x` (primitive, passed by value). `arr[0] = 99` DOES affect `a` (object reference, same array).*

---

**Question 42**

Which of the following will NOT throw an exception at runtime?

**(A)**
```java
int[] arr = new int[5];
System.out.println(arr[5]);
```

**(B)**
```java
String s = null;
System.out.println(s.length());
```

**(C)**
```java
int x = 5 / 0;
```

**(D)**
```java
int[] arr = new int[5];
System.out.println(arr[4]);
```

> *Trap: (A) out-of-bounds, (B) NullPointer, (C) ArithmeticException. (D) `arr[4]` = last valid index → prints 0, no error.*

---

# SECTION II — Free Response (4 Questions, 90 Minutes)

---

## Free Response Question 1 — Methods and Control Structures (7 points)

A developer is building a word analysis tool.

**(a)** Write the method `countVowels` that takes a `String` and returns the number of vowels (`a, e, i, o, u` — both upper and lower case) it contains.

```java
/** Returns the number of vowel characters in s.
 *  Both uppercase and lowercase vowels are counted.
 *  @param s a non-null String
 *  @return number of vowels in s
 */
public static int countVowels(String s)
```

**(b)** Write the method `isPalindrome` that returns `true` if a String reads the same forwards and backwards (case-insensitive), `false` otherwise.

```java
/** Returns true if s is a palindrome (case-insensitive), false otherwise.
 *  @param s a non-null String
 *  @return true if s is a palindrome
 */
public static boolean isPalindrome(String s)
```

**Examples:**
- `isPalindrome("Racecar")` → `true`
- `isPalindrome("hello")` → `false`
- `isPalindrome("A")` → `true`

---

## Free Response Question 2 — Class Design (7 points)

Write a complete class `Scoreboard` that tracks scores in a game.

A `Scoreboard` is created with a player's name (`String`). It starts with a score of `0` and a `round` number of `1`.

The class must include:
- A constructor taking the player's name.
- `addScore(int points)`: adds `points` to the score if `points > 0`; increments round by 1 regardless of whether points were added (even if points <= 0).
- `getRound()`: returns the current round number.
- `getScore()`: returns the total score.
- `getAverage()`: returns the average points per round **for rounds that have been played** (i.e., all rounds including the current one that just completed). Return 0.0 if no rounds have been played.
- `toString()`: returns `"Player: Alice | Score: 45 | Round: 3"`

**Example:**
```java
Scoreboard sb = new Scoreboard("Alice");
sb.addScore(20);   // round becomes 2, score = 20
sb.addScore(15);   // round becomes 3, score = 35
sb.addScore(-5);   // invalid score, round becomes 4, score = 35
sb.addScore(10);   // round becomes 5, score = 45
System.out.println(sb.getRound());    // 5
System.out.println(sb.getScore());    // 45
System.out.println(sb.getAverage()); // 45.0 / 4 = 11.25 (4 rounds played)
```

> Note: Round starts at 1 (before any `addScore` call). Each `addScore` call advances the round. "Rounds played" = round - 1.

Write the complete `Scoreboard` class.

---

## Free Response Question 3 — Data Analysis with ArrayList (5 points)

**(a)** Write the method `removeDuplicates` that takes an `ArrayList<Integer>` and removes all **duplicate** elements, keeping only the **first** occurrence of each value. The order of remaining elements must be preserved.

```java
/** Removes duplicate values from list, keeping first occurrence of each.
 *  Modifies the list in place.
 *  @param list an ArrayList of integers
 */
public static void removeDuplicates(ArrayList<Integer> list)
```

**Example:** `[3, 1, 4, 1, 5, 3, 2]` → `[3, 1, 4, 5, 2]`

**(b)** Write the method `mergeIncreasing` that takes two `ArrayList<Integer>` objects, each sorted in non-decreasing order, and returns a **new** `ArrayList<Integer>` containing all elements of both lists merged in non-decreasing order.

```java
/** Returns a new ArrayList containing all elements of a and b in sorted order.
 *  Both a and b are already sorted in non-decreasing order.
 *  @param a first sorted ArrayList
 *  @param b second sorted ArrayList
 *  @return new merged sorted ArrayList
 */
public static ArrayList<Integer> mergeIncreasing(ArrayList<Integer> a, ArrayList<Integer> b)
```

**Example:** `[1, 3, 5]` and `[2, 4, 6]` → `[1, 2, 3, 4, 5, 6]`

---

## Free Response Question 4 — 2D Array (6 points)

A teacher stores quiz results in a 2D array where `results[i][j]` is the score of student `i` on quiz `j`. All scores are between 0 and 100 inclusive.

**(a)** Write the method `studentAverages` that returns a 1D array where each element is the average score of the corresponding student across all quizzes.

```java
/** Returns array of student averages.
 *  result[i] = average of results[i][0..numQuizzes-1]
 *  @param results 2D array of scores (non-empty, rectangular)
 *  @return array of double averages, one per student
 */
public static double[] studentAverages(int[][] results)
```

**(b)** Write the method `topStudentIndex` that returns the **index** of the student with the highest average score. If there is a tie, return the **lower** index. You **must** call `studentAverages` to implement this.

```java
/** Returns the index of the student with the highest average.
 *  Ties broken by lower index.
 *  @param results 2D array of scores (non-empty, rectangular)
 *  @return index of student with highest average
 */
public static int topStudentIndex(int[][] results)
```

**(c)** Write the method `failingStudents` that returns an `ArrayList<Integer>` of indices of all students whose average is strictly below 60.0. Indices should be in increasing order.

```java
/** Returns list of indices of students with average < 60.0, in order.
 *  @param results 2D array of scores
 *  @return ArrayList of failing student indices
 */
public static ArrayList<Integer> failingStudents(int[][] results)
```

---

# ANSWER KEY — Section I

| Q | Answer | Concept Tested |
|---|---|---|
| 1 | A | Primitive copy — y=x copies value, not reference |
| 2 | A | Left-to-right string concatenation |
| 3 | B | Floating-point imprecision |
| 4 | C | Missing braces — both lines run |
| 5 | A | `continue` skips iteration, loop continues |
| 6 | C | Narrowing cast required for double→int |
| 7 | B | String immutability |
| 8 | B | Integer `/=` truncates |
| 9 | B | Operator precedence with `!`, `&&`, `||` |
| 10 | B | Post-increment in while condition |
| 11 | B | Enhanced for loop copies, doesn't modify array |
| 12 | C | `new String()` creates distinct object; `==` vs `.equals()` |
| 13 | B | Array reference aliasing |
| 14 | C | Semicolon after for-loop → `i` out of scope |
| 15 | B | Unreachable statement after return |
| 16 | B | Pre-increment `++x` modifies x before expression |
| 17 | A | `remove(int)` removes by index, not value |
| 18 | C | do-while executes at least once |
| 19 | B | `substring(i,i)` returns empty string |
| 20 | B | Nested ternary evaluation |
| 21 | C | Object reference — d and c point to same Counter |
| 22 | C | Short-circuit OR with `x != 5 || x > 4` |
| 23 | B | Default int array value is 0 |
| 24 | A | Integer division in for loop update |
| 25 | B | `Math.abs` then truncation with `(int)` cast |
| 26 | C | Boolean return simplification |
| 27 | B | Switch fall-through without break |
| 28 | D | NullPointerException at runtime |
| 29 | C | Diagonal count in nested loop |
| 30 | D | Recursion without proper base case → StackOverflow |
| 31 | B | Integer division: `5/2 = 2`, `arr[2] = 30` |
| 32 | A | `add(0,...)` shifts elements → get(2) = "Y" |
| 33 | C | Off-by-one: `i <= arr.length` out of bounds |
| 34 | B | `substring(0,5)` = full string; `substring(5)` = "" |
| 35 | B | Post-increment + short-circuit AND |
| 36 | B | 2D array dimensions and enhanced for limitation |
| 37 | B | Palindrome check |
| 38 | A | Mixed pre/post decrement: `x-- - --y` |
| 39 | C | String literal interning for `getName()` |
| 40 | C | Break after accumulation: 1+...+10=55 |
| 41 | C | Primitive vs reference parameter passing |
| 42 | D | Valid last index access |

---

# SAMPLE FRQ SOLUTIONS

## FRQ 1(a) — `countVowels`

```java
public static int countVowels(String s) {
    int count = 0;
    String vowels = "aeiouAEIOU";
    for (int i = 0; i < s.length(); i++) {
        if (vowels.indexOf(s.charAt(i)) != -1) count++;
    }
    return count;
}
```

## FRQ 1(b) — `isPalindrome`

```java
public static boolean isPalindrome(String s) {
    s = s.toLowerCase();
    for (int i = 0; i < s.length() / 2; i++) {
        if (s.charAt(i) != s.charAt(s.length() - 1 - i)) return false;
    }
    return true;
}
```

## FRQ 2 — `Scoreboard`

```java
public class Scoreboard {
    private String playerName;
    private int score;
    private int round;

    public Scoreboard(String name) {
        playerName = name;
        score = 0;
        round = 1;
    }

    public void addScore(int points) {
        if (points > 0) score += points;
        round++;
    }

    public int getRound() { return round; }
    public int getScore() { return score; }

    public double getAverage() {
        int roundsPlayed = round - 1;
        if (roundsPlayed == 0) return 0.0;
        return (double) score / roundsPlayed;
    }

    public String toString() {
        return "Player: " + playerName + " | Score: " + score + " | Round: " + round;
    }
}
```

## FRQ 3(a) — `removeDuplicates`

```java
public static void removeDuplicates(ArrayList<Integer> list) {
    ArrayList<Integer> seen = new ArrayList<>();
    for (int i = list.size() - 1; i >= 0; i--) {
        int val = list.get(i);
        if (seen.contains(val)) {
            list.remove(i);
        } else {
            seen.add(val);
        }
    }
}
```

## FRQ 3(b) — `mergeIncreasing`

```java
public static ArrayList<Integer> mergeIncreasing(ArrayList<Integer> a, ArrayList<Integer> b) {
    ArrayList<Integer> result = new ArrayList<>();
    int i = 0, j = 0;
    while (i < a.size() && j < b.size()) {
        if (a.get(i) <= b.get(j)) result.add(a.get(i++));
        else result.add(b.get(j++));
    }
    while (i < a.size()) result.add(a.get(i++));
    while (j < b.size()) result.add(b.get(j++));
    return result;
}
```

## FRQ 4(a) — `studentAverages`

```java
public static double[] studentAverages(int[][] results) {
    double[] avgs = new double[results.length];
    for (int i = 0; i < results.length; i++) {
        int sum = 0;
        for (int score : results[i]) sum += score;
        avgs[i] = (double) sum / results[i].length;
    }
    return avgs;
}
```

## FRQ 4(b) — `topStudentIndex`

```java
public static int topStudentIndex(int[][] results) {
    double[] avgs = studentAverages(results);
    int topIdx = 0;
    for (int i = 1; i < avgs.length; i++) {
        if (avgs[i] > avgs[topIdx]) topIdx = i;
    }
    return topIdx;
}
```

## FRQ 4(c) — `failingStudents`

```java
public static ArrayList<Integer> failingStudents(int[][] results) {
    double[] avgs = studentAverages(results);
    ArrayList<Integer> failing = new ArrayList<>();
    for (int i = 0; i < avgs.length; i++) {
        if (avgs[i] < 60.0) failing.add(i);
    }
    return failing;
}
```

---

## ⚠️ Post-Exam Trap Review

After finishing, review each question you got wrong against this checklist:

| Trap Category | Questions |
|---|---|
| Primitive vs reference copy | 1, 13, 25, 41 |
| String immutability | 7 |
| `==` vs `.equals()` | 12, 39 |
| Integer division & casting | 3, 6, 8, 24, 25 |
| Missing braces / semicolon bugs | 4, 14 |
| Loop variable scope / enhanced for | 5, 11 |
| Post vs pre increment | 10, 16, 38 |
| ArrayList index vs value remove | 17 |
| Do-while executes at least once | 18 |
| Short-circuit evaluation | 9, 35 |
| Default array initialization | 23 |
| Recursion base case missing | 30 |
| Switch fall-through | 27 |
| Null pointer at runtime | 28 |
| Off-by-one errors | 33 |

---

*End of Practice Exam 02 — Cross-reference any misses with APCS_lastminute_revision.md*
