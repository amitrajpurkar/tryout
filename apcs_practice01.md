# AP Computer Science A — Practice Exam 01
### 🔴 Difficulty: Higher Than Average | Full Mock Exam

> **Format:** Section I — 42 Multiple Choice (90 min) | Section II — 4 Free Response (90 min)  
> **Total Time:** 3 hours  
> Refer to the Java Quick Reference at the end of the revision guide where needed.

---

# SECTION I — Multiple Choice (42 Questions, 90 Minutes)

*Each question is worth the same number of points. There is no penalty for guessing.*

---

**Question 1**

What is the output of the following code?

```java
int x = 7;
int y = 2;
System.out.println(x / y + " " + x % y + " " + (double) x / y);
```

(A) `3 1 3.5`  
(B) `3.5 1 3.5`  
(C) `3 1 3`  
(D) `3.5 1 3`  

---

**Question 2**

What is the value of `result` after the following code executes?

```java
int result = 0;
for (int i = 1; i <= 5; i++) {
    if (i % 2 != 0) result += i;
}
```

(A) `6`  
(B) `9`  
(C) `15`  
(D) `12`  

---

**Question 3**

Consider the following method:

```java
public static int mystery(int n) {
    if (n <= 1) return n;
    return mystery(n - 1) + mystery(n - 2);
}
```

What is returned by `mystery(6)`?

(A) `6`  
(B) `8`  
(C) `13`  
(D) `21`  

---

**Question 4**

What is the output of the following code segment?

```java
String s = "abcdefg";
System.out.println(s.substring(2, 5).toUpperCase() + s.substring(5));
```

(A) `CDEfg`  
(B) `CDEfg`  
(C) `CDEfg`  
(D) `cdefg`  

*(A) `CDEfg`  
(B) `CDEef`  
(C) `CDEfg`  
(D) `cde`*

---

**Question 4** *(Corrected)*

What is the output of the following code segment?

```java
String s = "abcdefg";
System.out.println(s.substring(2, 5).toUpperCase() + s.substring(5));
```

(A) `CDEfg`  
(B) `CDEef`  
(C) `cdefg`  
(D) `CDEg`  

---

**Question 5**

Which of the following boolean expressions is equivalent to `!(x > 3 && y < 10)`?

(A) `x <= 3 && y >= 10`  
(B) `x < 3 || y > 10`  
(C) `x <= 3 || y >= 10`  
(D) `x > 3 || y < 10`  

---

**Question 6**

Consider the following code segment. What is printed?

```java
int[] arr = {5, 3, 8, 1, 9, 2};
int count = 0;
for (int i = 0; i < arr.length - 1; i++) {
    if (arr[i] > arr[i + 1]) count++;
}
System.out.println(count);
```

(A) `2`  
(B) `3`  
(C) `4`  
(D) `5`  

---

**Question 7**

What is the output of the following?

```java
int a = 5, b = 3;
a += b;
b = a - b;
a -= b;
System.out.println(a + " " + b);
```

(A) `3 5`  
(B) `5 3`  
(C) `8 5`  
(D) `3 8`  

---

**Question 8**

Consider the following class:

```java
public class Box {
    private int value;
    public Box(int v) { value = v; }
    public void increment() { value++; }
    public int getValue() { return value; }
}
```

What is printed by the following?

```java
Box b1 = new Box(10);
Box b2 = b1;
b2.increment();
b2.increment();
System.out.println(b1.getValue());
```

(A) `10`  
(B) `11`  
(C) `12`  
(D) `13`  

---

**Question 9**

Which of the following correctly generates a random integer between 5 and 15 inclusive?

(A) `(int)(Math.random() * 10) + 5`  
(B) `(int)(Math.random() * 11) + 5`  
(C) `(int)(Math.random() * 15) + 5`  
(D) `(int)(Math.random() * 10) + 1`  

---

**Question 10**

What is the output of the following code?

```java
int x = 10;
while (x > 0) {
    x -= 3;
}
System.out.println(x);
```

(A) `1`  
(B) `-2`  
(C) `0`  
(D) `-3`  

---

**Question 11**

Consider the following method. What is returned by `compute(12)`?

```java
public static int compute(int n) {
    int result = 0;
    while (n > 1) {
        result++;
        n /= 2;
    }
    return result;
}
```

(A) `2`  
(B) `3`  
(C) `4`  
(D) `6`  

---

**Question 12**

What is the output of the following nested loop?

```java
for (int i = 0; i < 4; i++) {
    for (int j = i; j < 4; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

(A)  
```
****
***
**
*
```  
(B)  
```
****
***
**
*
```  
(C)  
```
*
**
***
****
```  
(D)  
```
****
***
**
*
```  

*(A) 4, 3, 2, 1 stars on each line*  
*(B) 1, 2, 3, 4 stars on each line*  
*(C) same as A*  
*(D) 4, 3, 2, 1 — starts at j=i*

**Revised Question 12:**

How many total asterisks are printed by the above nested loop?

(A) `10`  
(B) `12`  
(C) `16`  
(D) `6`  

---

**Question 13**

Consider this ArrayList manipulation:

```java
ArrayList<Integer> list = new ArrayList<>();
list.add(10);
list.add(20);
list.add(30);
list.add(1, 15);
list.remove(2);
System.out.println(list);
```

What is printed?

(A) `[10, 15, 30]`  
(B) `[10, 20, 30]`  
(C) `[10, 15, 20]`  
(D) `[15, 20, 30]`  

---

**Question 14**

What does the following code print?

```java
String str = "Hello, World!";
int idx = str.indexOf("o");
System.out.println(str.substring(idx, idx + 3));
```

(A) `o, W`  
(B) `orl`  
(C) `o, `  
(D) `Wor`  

---

**Question 15**

Consider the following two-dimensional array:

```java
int[][] grid = {{1,2,3},{4,5,6},{7,8,9}};
int sum = 0;
for (int i = 0; i < grid.length; i++) {
    sum += grid[i][grid.length - 1 - i];
}
System.out.println(sum);
```

What is printed?

(A) `9`  
(B) `15`  
(C) `12`  
(D) `18`  

---

**Question 16**

A method `findFirst` is supposed to return the index of the first occurrence of `target` in `arr`, or -1 if not found. Which implementation is correct?

**(A)**
```java
public static int findFirst(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) return i;
    }
    return -1;
}
```

**(B)**
```java
public static int findFirst(int[] arr, int target) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) return i;
        else return -1;
    }
    return -1;
}
```

**(C)**
```java
public static int findFirst(int[] arr, int target) {
    int idx = -1;
    for (int val : arr) {
        if (val == target) idx = 0;
    }
    return idx;
}
```

**(D)**
```java
public static int findFirst(int[] arr, int target) {
    for (int val : arr) {
        if (val == target) return val;
    }
    return -1;
}
```

---

**Question 17**

What is the output of the following?

```java
public static int f(int n) {
    if (n == 0) return 0;
    return n + f(n - 1);
}

System.out.println(f(5));
```

(A) `5`  
(B) `10`  
(C) `15`  
(D) `0`  

---

**Question 18**

Consider the following code:

```java
int[] a = {3, 1, 4, 1, 5, 9, 2, 6};
int lo = 0, hi = a.length - 1;
while (lo < hi) {
    int temp = a[lo];
    a[lo] = a[hi];
    a[hi] = temp;
    lo++;
    hi--;
}
System.out.println(a[0] + " " + a[3]);
```

What is printed?

(A) `6 1`  
(B) `3 1`  
(C) `6 4`  
(D) `2 4`  

---

**Question 19**

Which of the following best describes what the method below does?

```java
public static boolean check(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        if (arr[i] > arr[i + 1]) return false;
    }
    return true;
}
```

(A) Returns true if the array is sorted in descending order.  
(B) Returns true if the array contains no duplicates.  
(C) Returns true if the array is sorted in non-decreasing order.  
(D) Returns true if the array is sorted in strictly increasing order.  

---

**Question 20**

What is the output?

```java
int i = 0;
int j = 10;
while (i < j) {
    i += 2;
    j--;
}
System.out.println(i + " " + j);
```

(A) `8 7`  
(B) `8 8`  
(C) `10 7`  
(D) `8 6`  

---

**Question 21**

Consider:

```java
public class Animal {
    private String name;
    private static int count = 0;

    public Animal(String name) {
        this.name = name;
        count++;
    }

    public static int getCount() { return count; }
    public String getName() { return name; }
}
```

After executing:
```java
Animal a = new Animal("Cat");
Animal b = new Animal("Dog");
Animal c = new Animal("Bird");
```

What does `Animal.getCount()` return?

(A) `0`  
(B) `1`  
(C) `2`  
(D) `3`  

---

**Question 22**

What value does the following return for input `n = 100`?

```java
public static int count(int n) {
    int c = 0;
    while (n > 1) {
        if (n % 2 == 0) n /= 2;
        else n = 3 * n + 1;
        c++;
    }
    return c;
}
```

(A) It returns 0.  
(B) It loops infinitely.  
(C) It returns a finite value greater than 0.  
(D) It throws an exception.  

---

**Question 23**

Given:

```java
ArrayList<String> words = new ArrayList<>();
words.add("ant");
words.add("bat");
words.add("cat");
words.add("dog");

for (int i = words.size() - 1; i >= 0; i--) {
    if (words.get(i).charAt(0) > 'b') {
        words.remove(i);
    }
}
```

What does `words` contain after this code?

(A) `["ant", "bat"]`  
(B) `["ant", "bat", "dog"]`  
(C) `["ant", "bat", "cat"]`  
(D) `["ant", "bat", "cat", "dog"]`  

---

**Question 24**

What is the output of the following?

```java
int x = 5;
int y = x++;
System.out.println(x + " " + y);
```

(A) `5 5`  
(B) `6 5`  
(C) `6 6`  
(D) `5 6`  

---

**Question 25**

Consider the method:

```java
public static void swap(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
}
```

After calling:
```java
int x = 3, y = 7;
swap(x, y);
System.out.println(x + " " + y);
```

What is printed?

(A) `7 3`  
(B) `3 7`  
(C) `3 3`  
(D) `7 7`  

---

**Question 26**

What is the result of the following?

```java
int[] arr = new int[5];
for (int i = 0; i < arr.length; i++) {
    arr[i] = i * i;
}
System.out.println(arr[3] + arr[4]);
```

(A) `7`  
(B) `16`  
(C) `25`  
(D) `9`  

---

**Question 27**

Which of the following correctly removes all negative numbers from an ArrayList `nums`?

**(A)**
```java
for (int i = 0; i < nums.size(); i++) {
    if (nums.get(i) < 0) nums.remove(i);
}
```

**(B)**
```java
for (int i = nums.size() - 1; i >= 0; i--) {
    if (nums.get(i) < 0) nums.remove(i);
}
```

**(C)**
```java
for (int n : nums) {
    if (n < 0) nums.remove(n);
}
```

**(D)**
```java
for (int i = 0; i <= nums.size(); i++) {
    if (nums.get(i) < 0) nums.remove(i);
}
```

---

**Question 28**

After the following selection sort pass (first outer iteration, i=0):

```java
int[] arr = {64, 25, 12, 22, 11};
```

What does the array look like after the first complete pass of selection sort?

(A) `{25, 64, 12, 22, 11}`  
(B) `{11, 25, 12, 22, 64}`  
(C) `{11, 64, 25, 22, 12}`  
(D) `{12, 25, 64, 22, 11}`  

---

**Question 29**

Consider the following method:

```java
public static String process(String s) {
    String result = "";
    for (int i = 0; i < s.length(); i++) {
        if (i % 2 == 0) result += s.substring(i, i + 1).toUpperCase();
        else result += s.substring(i, i + 1).toLowerCase();
    }
    return result;
}
```

What does `process("hElLo")` return?

(A) `"HeLlO"`  
(B) `"hElLo"`  
(C) `"HeLlO"`  
(D) `"HELLO"`  

---

**Question 30**

What is the output?

```java
int[][] grid = new int[3][3];
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        grid[i][j] = i + j;
    }
}
System.out.println(grid[2][2] + grid[0][2] + grid[2][0]);
```

(A) `4`  
(B) `8`  
(C) `6`  
(D) `9`  

---

**Question 31**

What is the value of `n` after the following executes?

```java
int n = 1;
for (int i = 0; i < 8; i++) {
    n *= 2;
}
```

(A) `16`  
(B) `128`  
(C) `256`  
(D) `64`  

---

**Question 32**

Consider:

```java
public static int g(int x, int y) {
    if (x == 0) return y;
    return g(x - 1, x + y);
}
```

What does `g(4, 0)` return?

(A) `4`  
(B) `10`  
(C) `6`  
(D) `0`  

---

**Question 33**

Which best describes the time complexity of the following?

```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < i; j++) {
        // constant work
    }
}
```

(A) O(n)  
(B) O(n log n)  
(C) O(n²)  
(D) O(2ⁿ)  

---

**Question 34**

What is printed?

```java
String a = "java";
String b = "java";
String c = new String("java");
System.out.println(a == b);
System.out.println(a == c);
System.out.println(a.equals(c));
```

(A) `true true true`  
(B) `true false true`  
(C) `false false true`  
(D) `true true false`  

---

**Question 35**

Consider:

```java
public static int mystery(int[] arr, int target) {
    int lo = 0, hi = arr.length - 1;
    while (lo <= hi) {
        int mid = (lo + hi) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) lo = mid + 1;
        else hi = mid - 1;
    }
    return -1;
}
```

For `arr = {2, 5, 8, 12, 16, 23, 38, 56, 72, 91}` and `target = 23`, how many iterations does the while loop execute?

(A) `1`  
(B) `2`  
(C) `3`  
(D) `4`  

---

**Question 36**

What is the output of the following?

```java
ArrayList<Integer> list = new ArrayList<>();
for (int i = 1; i <= 5; i++) list.add(i);

int prod = 1;
for (int i = 0; i < list.size(); i++) {
    if (list.get(i) % 2 != 0) prod *= list.get(i);
}
System.out.println(prod);
```

(A) `6`  
(B) `15`  
(C) `120`  
(D) `5`  

---

**Question 37**

Consider the following. What is `arr` after the code executes?

```java
int[] arr = {1, 2, 3, 4, 5};
for (int i = 0; i < arr.length / 2; i++) {
    arr[i] += arr[arr.length - 1 - i];
    arr[arr.length - 1 - i] = arr[i] - arr[arr.length - 1 - i];
    arr[i] = arr[i] - arr[arr.length - 1 - i];
}
```

What does `arr[0] + arr[4]` equal?

(A) `6`  
(B) `5`  
(C) `1`  
(D) `10`  

---

**Question 38**

What is the output of the following?

```java
int count = 0;
for (int i = 2; i <= 30; i++) {
    boolean prime = true;
    for (int j = 2; j < i; j++) {
        if (i % j == 0) { prime = false; break; }
    }
    if (prime) count++;
}
System.out.println(count);
```

(A) `8`  
(B) `9`  
(C) `10`  
(D) `11`  

---

**Question 39**

What is the output?

```java
public static void change(int[] arr) {
    for (int i = 0; i < arr.length; i++) {
        arr[i] *= 2;
    }
}

int[] nums = {1, 2, 3};
change(nums);
System.out.println(nums[1]);
```

(A) `2`  
(B) `4`  
(C) `6`  
(D) `1`  

---

**Question 40**

What is the output of the following recursion trace?

```java
public static void print(int n) {
    if (n <= 0) return;
    System.out.print(n + " ");
    print(n - 2);
    System.out.print(n + " ");
}
print(5);
```

(A) `5 3 1 1 3 5`  
(B) `5 3 1`  
(C) `1 3 5 5 3 1`  
(D) `5 3 1 3 5`  

---

**Question 41**

Which code segment correctly counts how many rows of `grid` have a sum greater than 10?

```java
int[][] grid = {{3, 5, 4}, {1, 2, 3}, {7, 6, 2}, {8, 1, 1}};
```

**(A)**
```java
int count = 0;
for (int[] row : grid) {
    int sum = 0;
    for (int val : row) sum += val;
    if (sum > 10) count++;
}
```

**(B)**
```java
int count = 0;
for (int i = 0; i < grid.length; i++) {
    if (grid[i][0] + grid[i][1] + grid[i][2] > 10) count++;
}
```

**(C)** Both A and B are correct.  
**(D)** Neither A nor B is correct.  

---

**Question 42**

Consider the `Temp` class:

```java
public class Temp {
    private double celsius;
    public Temp(double c) { celsius = c; }
    public double toFahrenheit() { return celsius * 9.0 / 5.0 + 32; }
    public static Temp fromFahrenheit(double f) {
        return new Temp((f - 32) * 5.0 / 9.0);
    }
}
```

What does the following print (approximately)?

```java
Temp t = Temp.fromFahrenheit(212.0);
System.out.println(t.toFahrenheit());
```

(A) `100.0`  
(B) `212.0`  
(C) `32.0`  
(D) `200.0`  

---

# SECTION II — Free Response (4 Questions, 90 Minutes)

*Show all work. Partial credit is awarded. Write complete Java code unless otherwise stated.*

---

## Free Response Question 1 — Methods and Control Structures (7 points)

A teacher wants a program to analyze student scores.

The following method, `getGrade`, has already been written:

```java
/** Returns letter grade for a given score.
 *  90-100: "A", 80-89: "B", 70-79: "C", 60-69: "D", below 60: "F"
 */
public static String getGrade(int score) { /* implementation not shown */ }
```

**(a)** Write the method `countGrade` that takes an array of integer scores and a String `grade`, and returns the number of students who received that grade.

```java
/** Returns the number of scores in scores[] that map to grade via getGrade.
 *  @param scores an array of student scores
 *  @param grade  the letter grade to count ("A", "B", "C", "D", or "F")
 *  @return the count of students who received the specified grade
 */
public static int countGrade(int[] scores, String grade)
```

**(b)** Write the method `topStudents` that takes an array of scores and an integer `n`, and returns a new array containing only scores that are in the top `n` percentile or above. A score is in the top n percentile if it is greater than or equal to `(100 - n)` percent of all scores. For simplicity, a score qualifies if it is **at least as large as the `(100-n)`th percentile value**, computed as:

```
threshold = (int)(maxScore * (100 - n) / 100.0)
```

where `maxScore` is the highest score in the array.

```java
/** Returns an array of all scores >= threshold.
 *  @param scores an array of student scores (non-empty)
 *  @param n      the top percentile (e.g., n=20 means top 20%)
 *  @return array of qualifying scores (order not required to be maintained)
 */
public static int[] topStudents(int[] scores, int n)
```

---

## Free Response Question 2 — Class Design (7 points)

Write a complete class `BankAccount` that represents a simple bank account.

A `BankAccount` object is created with:
- An account holder's name (`String`)
- An initial balance (`double`) — assume it is non-negative

The `BankAccount` class must include:

- A constructor that initializes both fields.
- A `deposit(double amount)` method: adds `amount` to the balance if `amount > 0`; does nothing otherwise.
- A `withdraw(double amount)` method: subtracts `amount` from balance if `amount > 0` AND `amount <= balance`; does nothing otherwise.
- A `getBalance()` method that returns the current balance.
- A `toString()` method that returns a String in the format:  
  `"Account[name=Alice, balance=250.0]"`

**Example usage:**
```java
BankAccount acc = new BankAccount("Alice", 200.0);
acc.deposit(100.0);
acc.withdraw(50.0);
System.out.println(acc.getBalance());   // 250.0
System.out.println(acc);               // Account[name=Alice, balance=250.0]
acc.withdraw(300.0);                   // does nothing — insufficient funds
System.out.println(acc.getBalance());   // 250.0
```

Write the complete `BankAccount` class.

---

## Free Response Question 3 — Data Analysis with ArrayList (5 points)

You are given an `ArrayList<Integer>` named `data` containing a sequence of integers.

**(a)** Write the method `removeBelowAverage` that removes all elements from `data` that are strictly below the average of all elements. The average is computed **before** any removal.

```java
/** Removes all elements from data that are strictly less than the average.
 *  Average is computed from the original list before removal.
 *  @param data an ArrayList of integers (non-empty)
 */
public static void removeBelowAverage(ArrayList<Integer> data)
```

**(b)** Write the method `alternatingSum` that takes an `ArrayList<Integer>` and returns the alternating sum: the sum where elements at even indices are added and elements at odd indices are subtracted.

For example, for list `[3, 1, 4, 1, 5]`:  
`alternatingSum = 3 - 1 + 4 - 1 + 5 = 10`

```java
/** Returns the alternating sum of the list.
 *  @param list a non-empty ArrayList of integers
 *  @return alternating sum (add even-indexed, subtract odd-indexed)
 */
public static int alternatingSum(ArrayList<Integer> list)
```

---

## Free Response Question 4 — 2D Array (6 points)

A `Grid` class is used to represent an m × n grid of integers.

**(a)** Write the method `rowSums` that takes a 2D integer array `grid` and returns a 1D array where each element is the sum of the corresponding row.

```java
/** Returns an array where result[i] is the sum of row i of grid.
 *  @param grid a 2D array of integers (non-empty, rectangular)
 *  @return array of row sums
 */
public static int[] rowSums(int[][] grid)
```

**(b)** Write the method `rotate90` that takes a square (n × n) 2D array and returns a **new** 2D array that is the original rotated 90 degrees clockwise. In a 90° clockwise rotation, element at `[i][j]` moves to `[j][n-1-i]` in the new array.

```java
/** Returns a new 2D array that is grid rotated 90 degrees clockwise.
 *  @param grid an n×n 2D array
 *  @return new n×n array rotated 90° clockwise
 */
public static int[][] rotate90(int[][] grid)
```

**Example:**
```
Input:           Output (90° CW):
1  2  3          7  4  1
4  5  6    →     8  5  2
7  8  9          9  6  3
```

---

# ANSWER KEY — Section I

| Q | Answer | Topic |
|---|---|---|
| 1 | A | Expressions, casting |
| 2 | B | Loops, conditionals |
| 3 | B | Recursion (Fibonacci) |
| 4 | A | String methods |
| 5 | C | De Morgan's Law |
| 6 | B | Array traversal |
| 7 | A | Variable swap via arithmetic |
| 8 | C | Object references |
| 9 | B | Math.random() range |
| 10 | B | while loop, negative result |
| 11 | B | Loop counting (log₂) |
| 12 | A | Nested loops (10 total) |
| 13 | A | ArrayList add/remove |
| 14 | C | String indexOf + substring |
| 15 | B | 2D array diagonal access |
| 16 | A | Linear search |
| 17 | C | Recursion (sum) |
| 18 | A | Array reversal tracing |
| 19 | C | Algorithm description |
| 20 | A | Two-variable while loop |
| 21 | D | Static variables |
| 22 | C | Collatz-like — terminates |
| 23 | A | ArrayList removal backwards |
| 24 | B | Post-increment |
| 25 | B | Primitive pass-by-value |
| 26 | C | Array squares |
| 27 | B | Safe ArrayList removal |
| 28 | B | Selection sort first pass |
| 29 | A | String alternating case |
| 30 | B | 2D array computation |
| 31 | C | Powers of 2 |
| 32 | B | Accumulation recursion |
| 33 | C | Nested loop complexity |
| 34 | B | String == vs equals |
| 35 | C | Binary search iterations |
| 36 | B | ArrayList product of odds |
| 37 | A | In-place swap via arithmetic |
| 38 | C | Counting primes (10 primes: 2,3,5,7,11,13,17,19,23,29) |
| 39 | B | Array pass by reference |
| 40 | A | Recursive print trace |
| 41 | C | Both A and B are correct |
| 42 | B | Conversion round-trip |

---

# SAMPLE FRQ SOLUTIONS

## FRQ 1(a) — `countGrade`

```java
public static int countGrade(int[] scores, String grade) {
    int count = 0;
    for (int score : scores) {
        if (getGrade(score).equals(grade)) count++;
    }
    return count;
}
```

## FRQ 1(b) — `topStudents`

```java
public static int[] topStudents(int[] scores, int n) {
    int maxScore = scores[0];
    for (int s : scores) {
        if (s > maxScore) maxScore = s;
    }
    int threshold = (int)(maxScore * (100 - n) / 100.0);
    
    // Count qualifying scores
    int count = 0;
    for (int s : scores) {
        if (s >= threshold) count++;
    }
    
    int[] result = new int[count];
    int idx = 0;
    for (int s : scores) {
        if (s >= threshold) result[idx++] = s;
    }
    return result;
}
```

## FRQ 2 — `BankAccount`

```java
public class BankAccount {
    private String name;
    private double balance;

    public BankAccount(String name, double initialBalance) {
        this.name = name;
        this.balance = initialBalance;
    }

    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) balance -= amount;
    }

    public double getBalance() { return balance; }

    public String toString() {
        return "Account[name=" + name + ", balance=" + balance + "]";
    }
}
```

## FRQ 3(a) — `removeBelowAverage`

```java
public static void removeBelowAverage(ArrayList<Integer> data) {
    double sum = 0;
    for (int val : data) sum += val;
    double avg = sum / data.size();
    
    for (int i = data.size() - 1; i >= 0; i--) {
        if (data.get(i) < avg) data.remove(i);
    }
}
```

## FRQ 3(b) — `alternatingSum`

```java
public static int alternatingSum(ArrayList<Integer> list) {
    int sum = 0;
    for (int i = 0; i < list.size(); i++) {
        if (i % 2 == 0) sum += list.get(i);
        else sum -= list.get(i);
    }
    return sum;
}
```

## FRQ 4(a) — `rowSums`

```java
public static int[] rowSums(int[][] grid) {
    int[] sums = new int[grid.length];
    for (int i = 0; i < grid.length; i++) {
        int rowSum = 0;
        for (int val : grid[i]) rowSum += val;
        sums[i] = rowSum;
    }
    return sums;
}
```

## FRQ 4(b) — `rotate90`

```java
public static int[][] rotate90(int[][] grid) {
    int n = grid.length;
    int[][] result = new int[n][n];
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            result[j][n - 1 - i] = grid[i][j];
        }
    }
    return result;
}
```

---

*End of Practice Exam 01 — Check your answers against the key and review any missed topics in APCS_lastminute_revision.md*
