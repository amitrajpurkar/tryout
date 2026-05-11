Here’s a full IB Computer Science SL Paper 2–style practice paper focused on Option D: Object-Oriented Programming (B3.1 – single class). I’ve kept the structure, command terms, and mark distribution aligned with IB style so you can use it like a real exam.

⸻

IB Computer Science SL – Paper 2 (Practice)

Option D: Object-Oriented Programming (B3.1)

Time: 1 hour
Marks: 45

⸻

Section A – Short Answer (15 marks)

1. (4 marks)
Define the following terms in the context of object-oriented programming:
a) Class
b) Object
c) Attribute
d) Method

⸻

2. (3 marks)
Explain the difference between:

* a constructor method
* a regular method

⸻

3. (4 marks)
Consider the following class:

class Book {
    String title;
    String author;
    int pages;
    public Book(String t, String a, int p) {
        title = t;
        author = a;
        pages = p;
    }
    public void displayDetails() {
        System.out.println(title + " by " + author);
    }
}

a) Identify the attributes (2 marks)
b) Identify the method(s) (2 marks)

⸻

4. (4 marks)
Describe two advantages of using object-oriented programming.

⸻

Section B – Code Reading & Tracing (10 marks)

5. (5 marks)
Consider the following code:

class Student {
    String name;
    int grade;
    public Student(String n, int g) {
        name = n;
        grade = g;
    }
    public void updateGrade(int newGrade) {
        grade = newGrade;
    }
    public void printInfo() {
        System.out.println(name + ": " + grade);
    }
}

And the following main program:

Student s1 = new Student("Alex", 70);
s1.printInfo();
s1.updateGrade(85);
s1.printInfo();

a) What is the output of the program? (3 marks)
b) Explain how the updateGrade method affects the object (2 marks)

⸻

6. (5 marks)
Identify and explain two errors in the following code:

class Car {
    String brand;
    int speed;
    public void Car(String b, int s) {
        brand = b;
        speed = s;
    }
    public void accelerate() {
        speed = speed + 10
    }
}

⸻

Section C – Design & Implementation (20 marks)

7. (10 marks)
A BankAccount class is required.

a) Identify three attributes suitable for this class (3 marks)
b) Write a constructor to initialize these attributes (3 marks)
c) Write a method deposit(double amount) (2 marks)
d) Write a method displayBalance() (2 marks)

⸻

8. (10 marks)
A Rectangle class is required.

a) Define attributes for length and width (2 marks)
b) Write a constructor (2 marks)
c) Write a method to calculate the area (3 marks)
d) Write a method to calculate the perimeter (3 marks)

⸻

Optional Extension (Exam-Style Challenge)

9. (Bonus – not IB graded)
Modify the Rectangle class to include:

* validation (length and width must be > 0)
* a method isSquare() that returns true if the rectangle is a square

⸻

Markscheme (Condensed)

Q1

* Class: blueprint/template (1)
* Object: instance of class (1)
* Attribute: data/variables (1)
* Method: function/behavior (1)

Q2

* Constructor initializes object (1)
* Same name as class / no return type (1)
* Regular methods perform actions (1)

Q3

* Attributes: title, author, pages (2)
* Methods: constructor, displayDetails (2)

Q4

Any two:

* Code reuse
* Modularity
* Maintainability
* Real-world modeling

Q5

* Output:

Alex: 70
Alex: 85

    (3)
* Explanation: method updates attribute value (2)

Q6

* Constructor incorrectly defined (should not have return type) (2)
* Missing semicolon in speed = speed + 10 (2)
* (1 mark for explanation clarity)

Q7 (example solution)

class BankAccount {
    String accountHolder;
    double balance;
    int accountNumber;
    public BankAccount(String name, double bal, int num) {
        accountHolder = name;
        balance = bal;
        accountNumber = num;
    }
    public void deposit(double amount) {
        balance += amount;
    }
    public void displayBalance() {
        System.out.println("Balance: " + balance);
    }
}

Q8 (example solution)

class Rectangle {
    double length;
    double width;
    public Rectangle(double l, double w) {
        length = l;
        width = w;
    }
    public double area() {
        return length * width;
    }
    public double perimeter() {
        return 2 * (length + width);
    }
}

⸻

If you want next:

I can also generate:

* ￼ A harder Paper 2 (with trickier tracing/debugging)
* ￼ A mock exam with unseen scenario + long question (like real IB case-based questions)
* Or ￼ convert this into a timed test + grading rubric sheet for practice

Just tell me 👍