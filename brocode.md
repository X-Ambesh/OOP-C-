# C++ Full Course Notes 📘
> Based on **[C++ Full Course for free ⚡️ by Bro Code](https://youtu.be/-TkoO8Z07hI)**
> A 6-hour beginner-friendly introduction to C++ — from zero to OOP.

---

## Table of Contents

1. [Introduction to C++](#1-introduction-to-c)
2. [Variables and Basic Data Types](#2-variables-and-basic-data-types)
3. [Const](#3-const)
4. [Namespaces](#4-namespaces)
5. [Typedef and Type Aliases](#5-typedef-and-type-aliases)
6. [Arithmetic Operators](#6-arithmetic-operators)
7. [Type Conversion](#7-type-conversion)
8. [User Input](#8-user-input)
9. [Useful Math Functions](#9-useful-math-functions)
10. [Hypotenuse Calculator](#10-hypotenuse-calculator-practice-program)
11. [If Statements](#11-if-statements)
12. [Switch Statements](#12-switch-statements)
13. [Console Calculator Program](#13-console-calculator-program)
14. [Ternary Operator](#14-ternary-operator)
15. [Logical Operators](#15-logical-operators)
16. [Temperature Conversion Program](#16-temperature-conversion-program)
17. [Useful String Methods](#17-useful-string-methods-in-c)
18. [While Loops](#18-while-loops)
19. [Do While Loops](#19-do-while-loops)
20. [For Loops](#20-for-loops)
21. [Break & Continue](#21-break--continue)
22. [Nested Loops](#22-nested-loops)
23. [Random Number Generator](#23-random-number-generator)
24. [Random Event Generator](#24-random-event-generator)
25. [Number Guessing Game](#25-number-guessing-game)
26. [User Defined Functions](#26-user-defined-functions)
27. [Return Keyword](#27-return-keyword)
28. [Overloaded Functions](#28-overloaded-functions)
29. [Variable Scope](#29-variable-scope)
30. [Banking Practice Program](#30-banking-practice-program)
31. [Rock Paper Scissors Game](#31-rock-paper-scissors-game)
32. [Arrays](#32-arrays)
33. [Sizeof() Operator](#33-sizeof-operator)
34. [Iterate Over an Array](#34-iterate-over-an-array)
35. [Foreach Loop](#35-foreach-loop)
36. [Pass Array to a Function](#36-pass-array-to-a-function)
37. [Search an Array](#37-search-an-array-for-an-element)
38. [Sort an Array](#38-sort-an-array)
39. [Fill() Function](#39-fill-function)
40. [Fill an Array with User Input](#40-fill-an-array-with-user-input)
41. [Multidimensional Arrays](#41-multidimensional-arrays)
42. [Quiz Game](#42-quiz-game)
43. [Memory Addresses](#43-memory-addresses)
44. [Pass by Value vs Pass by Reference](#44-pass-by-value-vs-pass-by-reference)
45. [Const Parameters](#45-const-parameters)
46. [Credit Card Validator Program](#46-credit-card-validator-program)
47. [Pointers](#47-pointers)
48. [Null Pointers](#48-null-pointers)
49. [Tic Tac Toe Game](#49-tic-tac-toe-game)
50. [Dynamic Memory](#50-dynamic-memory)
51. [Recursion](#51-recursion)
52. [Function Templates](#52-function-templates)
53. [Structs](#53-structs)
54. [Pass Structs as Arguments](#54-pass-structs-as-arguments)
55. [Enums](#55-enums)
56. [Object Oriented Programming (OOP)](#56-object-oriented-programming-oop)
57. [Constructors](#57-constructors)
58. [Constructor Overloading](#58-constructor-overloading)
59. [Getters & Setters](#59-getters--setters)
60. [Inheritance](#60-inheritance)

---

## 1. Introduction to C++

> C++ is a **fast, general-purpose, middle-level** programming language.
> It is widely used in game development, operating systems, embedded systems, and high-performance applications.

**Why C++?**
- Very fast execution speed
- Supports both low-level (memory management) and high-level (OOP) programming
- Foundation for many other languages (Java, C#, etc.)

**Basic Structure:**

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

| Part | Meaning |
|------|---------|
| `#include <iostream>` | Includes standard input/output library |
| `using namespace std;` | Allows use of `cout`, `cin` without `std::` prefix |
| `int main()` | Entry point of the program |
| `return 0;` | Indicates successful execution |

---

## 2. Variables and Basic Data Types

> A **variable** is a named container that stores a value in memory.

**Data Types:**

| Data Type | Size | Example |
|-----------|------|---------|
| `int` | 4 bytes | `int age = 21;` |
| `double` | 8 bytes | `double gpa = 3.9;` |
| `float` | 4 bytes | `float height = 5.9f;` |
| `char` | 1 byte | `char grade = 'A';` |
| `bool` | 1 byte | `bool student = true;` |
| `string` | varies | `string name = "Bro";` |

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    int age = 21;
    double gpa = 3.9;
    char grade = 'A';
    bool student = true;
    string name = "Bro";

    cout << "Name: " << name << endl;
    cout << "Age: " << age << endl;
    cout << "GPA: " << gpa << endl;
    cout << "Grade: " << grade << endl;
    cout << "Is a student: " << student << endl;
    return 0;
}
```

---

## 3. Const

> `const` is used to declare a **constant variable** — its value cannot be changed after initialization.

```cpp
#include <iostream>
using namespace std;

int main() {
    const double PI = 3.14159;
    const int DAYS_IN_WEEK = 7;

    cout << "PI = " << PI << endl;
    cout << "Days in a week = " << DAYS_IN_WEEK << endl;

    // PI = 3.0; // ❌ ERROR: cannot assign to a const variable
    return 0;
}
```

> **Convention:** Constant names are written in `ALL_CAPS`.

---

## 4. Namespaces

> A **namespace** is a declarative region that provides scope to identifiers (names of functions, variables, etc.) to prevent naming conflicts.

```cpp
#include <iostream>

namespace first {
    int x = 1;
}

namespace second {
    int x = 2;
}

int main() {
    // Access variables from different namespaces
    std::cout << first::x << std::endl;   // Output: 1
    std::cout << second::x << std::endl;  // Output: 2
    return 0;
}
```

> `using namespace std;` is shorthand so you don't have to type `std::` every time.

---

## 5. Typedef and Type Aliases

> `typedef` and `using` allow you to create **aliases** (alternate names) for data types, making code easier to read.

```cpp
#include <iostream>
using namespace std;

typedef string text_t;    // old-style typedef
using number_t = int;     // modern C++11 type alias

int main() {
    text_t firstName = "Bro";
    number_t age = 21;

    cout << firstName << endl;
    cout << age << endl;
    return 0;
}
```

---

## 6. Arithmetic Operators

> Operators used to perform mathematical calculations.

| Operator | Description | Example |
|----------|-------------|---------|
| `+` | Addition | `a + b` |
| `-` | Subtraction | `a - b` |
| `*` | Multiplication | `a * b` |
| `/` | Division | `a / b` |
| `%` | Modulus (remainder) | `a % b` |
| `++` | Increment | `a++` or `++a` |
| `--` | Decrement | `a--` or `--a` |

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 3;

    cout << "a + b = " << a + b << endl;  // 13
    cout << "a - b = " << a - b << endl;  // 7
    cout << "a * b = " << a * b << endl;  // 30
    cout << "a / b = " << a / b << endl;  // 3  (integer division)
    cout << "a % b = " << a % b << endl;  // 1

    a++;  // a is now 11
    cout << "After a++: " << a << endl;
    return 0;
}
```

---

## 7. Type Conversion

> **Type conversion** is converting a value from one data type to another.

**Implicit Conversion** (done automatically by the compiler):
```cpp
int x = 5;
double y = x;  // int automatically converted to double
```

**Explicit Conversion** (cast):
```cpp
#include <iostream>
using namespace std;

int main() {
    double pi = 3.14159;
    int intPi = (int)pi;       // C-style cast
    int intPi2 = int(pi);      // Function-style cast

    cout << "double: " << pi << endl;     // 3.14159
    cout << "int:    " << intPi << endl;  // 3 (truncated, not rounded)

    // Integer division vs floating-point division
    cout << 5 / 2 << endl;    // 2  (integer division)
    cout << 5.0 / 2 << endl;  // 2.5 (double division)
    return 0;
}
```

---

## 8. User Input

> `cin` is used to read input from the user via the keyboard.

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string name;
    int age;

    cout << "Enter your name: ";
    cin >> name;         // reads one word

    cout << "Enter your age: ";
    cin >> age;

    cout << "Hello " << name << "! You are " << age << " years old." << endl;
    return 0;
}
```

> For input with spaces, use `getline(cin, variableName)`:
```cpp
string fullName;
cout << "Enter full name: ";
getline(cin, fullName);
```

---

## 9. Useful Math Functions

> Included via `#include <cmath>`

| Function | Description | Example |
|----------|-------------|---------|
| `abs(x)` | Absolute value | `abs(-5)` → 5 |
| `pow(x, y)` | x to the power y | `pow(2, 10)` → 1024 |
| `sqrt(x)` | Square root | `sqrt(9)` → 3 |
| `cbrt(x)` | Cube root | `cbrt(27)` → 3 |
| `round(x)` | Round to nearest | `round(2.6)` → 3 |
| `ceil(x)` | Round up | `ceil(2.1)` → 3 |
| `floor(x)` | Round down | `floor(2.9)` → 2 |
| `max(x, y)` | Larger value | `max(4, 8)` → 8 |
| `min(x, y)` | Smaller value | `min(4, 8)` → 4 |

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    cout << "sqrt(25) = " << sqrt(25) << endl;
    cout << "pow(2,8) = " << pow(2, 8) << endl;
    cout << "max(3,7) = " << max(3, 7) << endl;
    cout << "round(2.6) = " << round(2.6) << endl;
    return 0;
}
```

---

## 10. Hypotenuse Calculator Practice Program

> Applying `sqrt()` and `pow()` in a practical program.

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    double a, b, c;

    cout << "Enter side A: ";
    cin >> a;
    cout << "Enter side B: ";
    cin >> b;

    c = sqrt(pow(a, 2) + pow(b, 2));

    cout << "Hypotenuse C = " << c << endl;
    return 0;
}
```

---

## 11. If Statements

> Used to execute code **conditionally** based on a boolean expression.

```cpp
#include <iostream>
using namespace std;

int main() {
    int age;
    cout << "Enter your age: ";
    cin >> age;

    if (age >= 18) {
        cout << "You are an adult." << endl;
    }
    else if (age >= 13) {
        cout << "You are a teenager." << endl;
    }
    else {
        cout << "You are a child." << endl;
    }
    return 0;
}
```

**Relational Operators:**

| Operator | Meaning |
|----------|---------|
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |
| `==` | Equal to |
| `!=` | Not equal to |

---

## 12. Switch Statements

> An alternative to multiple `if-else` chains when comparing **one variable** to many values.

```cpp
#include <iostream>
using namespace std;

int main() {
    int day;
    cout << "Enter day (1-7): ";
    cin >> day;

    switch (day) {
        case 1: cout << "Monday";    break;
        case 2: cout << "Tuesday";   break;
        case 3: cout << "Wednesday"; break;
        case 4: cout << "Thursday";  break;
        case 5: cout << "Friday";    break;
        case 6: cout << "Saturday";  break;
        case 7: cout << "Sunday";    break;
        default: cout << "Invalid day";
    }
    return 0;
}
```

> `break` prevents **fall-through** (executing the next case). `default` runs when no case matches.

---

## 13. Console Calculator Program

> Combines `if/switch`, `cin`, and operators.

```cpp
#include <iostream>
using namespace std;

int main() {
    double x, y;
    char op;

    cout << "Enter an expression (e.g. 5 + 3): ";
    cin >> x >> op >> y;

    switch (op) {
        case '+': cout << x + y; break;
        case '-': cout << x - y; break;
        case '*': cout << x * y; break;
        case '/':
            if (y != 0) cout << x / y;
            else cout << "Cannot divide by zero!";
            break;
        default: cout << "Invalid operator";
    }
    return 0;
}
```

---

## 14. Ternary Operator

> A **shorthand** `if-else` in a single line.
> **Syntax:** `condition ? value_if_true : value_if_false`

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 7;

    int max = (a > b) ? a : b;
    cout << "Max = " << max << endl;  // 10

    string result = (a % 2 == 0) ? "even" : "odd";
    cout << "a is " << result << endl;  // even
    return 0;
}
```

---

## 15. Logical Operators

> Used to combine multiple conditions.

| Operator | Symbol | Example | Result |
|----------|--------|---------|--------|
| AND | `&&` | `(a > 0) && (b > 0)` | true if both are true |
| OR | `\|\|` | `(a > 0) \|\| (b > 0)` | true if at least one is true |
| NOT | `!` | `!(a > 0)` | reverses the condition |

```cpp
#include <iostream>
using namespace std;

int main() {
    int temp;
    cout << "Enter temperature (Celsius): ";
    cin >> temp;

    if (temp > 0 && temp < 35) {
        cout << "Nice weather!" << endl;
    }
    else if (temp <= 0 || temp >= 35) {
        cout << "Extreme weather!" << endl;
    }
    return 0;
}
```

---

## 16. Temperature Conversion Program

```cpp
#include <iostream>
using namespace std;

int main() {
    char unit;
    double temp;

    cout << "Enter temperature: ";
    cin >> temp;
    cout << "Is it (C)elsius or (F)ahrenheit? ";
    cin >> unit;

    if (unit == 'C' || unit == 'c') {
        cout << temp << "°C = " << (temp * 9 / 5) + 32 << "°F" << endl;
    }
    else if (unit == 'F' || unit == 'f') {
        cout << temp << "°F = " << (temp - 32) * 5 / 9 << "°C" << endl;
    }
    else {
        cout << "Invalid unit." << endl;
    }
    return 0;
}
```

---

## 17. Useful String Methods in C++

> Include `#include <string>` to use string functions.

| Method | Description | Example |
|--------|-------------|---------|
| `.length()` | Returns length of string | `name.length()` |
| `.empty()` | Returns true if string is empty | `name.empty()` |
| `.clear()` | Erases the string | `name.clear()` |
| `.append(str)` | Appends to string | `name.append(" Code")` |
| `.at(index)` | Character at position | `name.at(0)` |
| `.find(str)` | Position of substring | `name.find("Bro")` |
| `.substr(pos, len)` | Extract substring | `name.substr(0, 3)` |

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string name = "Bro Code";

    cout << "Length: "    << name.length() << endl;
    cout << "First char: " << name.at(0) << endl;
    cout << "Substring: "  << name.substr(0, 3) << endl;
    cout << "Find 'Code': " << name.find("Code") << endl;

    name.append("!");
    cout << "Appended: " << name << endl;
    return 0;
}
```

---

## 18. While Loops

> Repeats a block of code **while** a condition is true.
> The condition is checked **before** each iteration.

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;

    while (i <= 5) {
        cout << i << " ";
        i++;
    }
    // Output: 1 2 3 4 5
    return 0;
}
```

---

## 19. Do While Loops

> Similar to `while`, but the condition is checked **after** each iteration — so the body always runs **at least once**.

```cpp
#include <iostream>
using namespace std;

int main() {
    int number;

    do {
        cout << "Enter a positive number: ";
        cin >> number;
    } while (number <= 0);

    cout << "You entered: " << number << endl;
    return 0;
}
```

---

## 20. For Loops

> Best used when the number of iterations is **known in advance**.
> **Syntax:** `for (init; condition; update)`

```cpp
#include <iostream>
using namespace std;

int main() {
    // Count up
    for (int i = 1; i <= 5; i++) {
        cout << i << " ";
    }
    cout << endl;

    // Count down
    for (int i = 5; i >= 1; i--) {
        cout << i << " ";
    }
    return 0;
}
```

---

## 21. Break & Continue

> **`break`** exits the loop immediately.
> **`continue`** skips the rest of the current iteration and moves to the next.

```cpp
#include <iostream>
using namespace std;

int main() {
    // break example
    for (int i = 1; i <= 10; i++) {
        if (i == 5) break;       // stops at 5
        cout << i << " ";
    }
    cout << endl;

    // continue example
    for (int i = 1; i <= 10; i++) {
        if (i == 5) continue;    // skips 5
        cout << i << " ";
    }
    return 0;
}
```

---

## 22. Nested Loops

> A loop inside another loop. Useful for patterns, tables, and 2D structures.

```cpp
#include <iostream>
using namespace std;

int main() {
    // Multiplication table
    for (int i = 1; i <= 3; i++) {
        for (int j = 1; j <= 3; j++) {
            cout << i * j << "\t";
        }
        cout << endl;
    }
    return 0;
}
```

```
Output:
1   2   3
2   4   6
3   6   9
```

---

## 23. Random Number Generator

> Use `<cstdlib>` and `<ctime>` to generate random numbers.

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    srand(time(0));  // seed with current time for true randomness

    int num = rand() % 6 + 1;  // random number between 1 and 6
    cout << "Dice roll: " << num << endl;
    return 0;
}
```

> `rand() % N` gives a number between **0 and N-1**. Add 1 to start from 1.

---

## 24. Random Event Generator

> Using random numbers to simulate probability-based events.

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    srand(time(0));
    int event = rand() % 3 + 1;  // 1, 2, or 3

    switch (event) {
        case 1: cout << "⚔️  You found a sword!" << endl; break;
        case 2: cout << "🐉 A dragon appears!" << endl;   break;
        case 3: cout << "💰 You found gold!" << endl;     break;
    }
    return 0;
}
```

---

## 25. Number Guessing Game

> Combines loops, conditionals, and random numbers.

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    srand(time(0));
    int secret = rand() % 100 + 1;  // 1–100
    int guess;
    int attempts = 0;

    cout << "Guess the number (1–100)!" << endl;

    do {
        cout << "Your guess: ";
        cin >> guess;
        attempts++;

        if (guess > secret) cout << "Too high!" << endl;
        else if (guess < secret) cout << "Too low!" << endl;
        else cout << "Correct! 🎉 You got it in " << attempts << " attempts!" << endl;

    } while (guess != secret);

    return 0;
}
```

---

## 26. User Defined Functions

> Functions allow you to **reuse** blocks of code.
> **Syntax:** `returnType functionName(parameters) { body }`

```cpp
#include <iostream>
using namespace std;

void greet(string name) {
    cout << "Hello, " << name << "!" << endl;
}

int add(int a, int b) {
    return a + b;
}

int main() {
    greet("Bro");             // Output: Hello, Bro!
    cout << add(3, 4);        // Output: 7
    return 0;
}
```

> **Formal parameters** are in the function definition. **Actual parameters (arguments)** are passed when calling.

---

## 27. Return Keyword

> `return` sends a value back to the caller and **exits** the function.

```cpp
#include <iostream>
using namespace std;

bool isEven(int number) {
    return (number % 2 == 0);
}

string getGrade(int score) {
    if (score >= 90) return "A";
    if (score >= 80) return "B";
    if (score >= 70) return "C";
    return "F";
}

int main() {
    cout << isEven(4) << endl;        // 1 (true)
    cout << getGrade(85) << endl;     // B
    return 0;
}
```

---

## 28. Overloaded Functions

> **Function overloading** means having multiple functions with the **same name** but **different parameters**.

```cpp
#include <iostream>
using namespace std;

void print(int x)    { cout << "Integer: " << x << endl; }
void print(double x) { cout << "Double: "  << x << endl; }
void print(string x) { cout << "String: "  << x << endl; }

int main() {
    print(5);        // calls int version
    print(3.14);     // calls double version
    print("Hello");  // calls string version
    return 0;
}
```

---

## 29. Variable Scope

> **Scope** defines where a variable is **accessible**.
> A variable declared inside `{}` is only available within those braces (local scope).

```cpp
#include <iostream>
using namespace std;

int globalVar = 100;  // global scope — accessi