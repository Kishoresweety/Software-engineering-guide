# 🧪 Test-Driven Development (TDD)

🔹 Concept

TDD = Write tests before writing code.

The cycle is called Red → Green → Refactor:

1. Red: Write a failing test.


2. Green: Write the minimum code to make the test pass.


3. Refactor: Clean up the code while keeping tests green.




👉 TDD ensures:

You only write code that’s needed.

Code is always testable and reliable.



---

🔹 Example → Calculator (Python + TDD)

Step 1: Write Test (Failing First)

File: test_calculator.py

import unittest
from calculator import Calculator

class TestCalculator(unittest.TestCase):
    def test_add(self):
        calc = Calculator()
        self.assertEqual(calc.add(2, 3), 5)

    def test_subtract(self):
        calc = Calculator()
        self.assertEqual(calc.subtract(5, 2), 3)

if __name__ == '__main__':
    unittest.main()

✅ This will fail because calculator.py doesn’t exist yet.


---

Step 2: Write Code to Pass Test

File: calculator.py

class Calculator:
    def add(self, a, b):
        return a + b

    def subtract(self, a, b):
        return a - b

✅ Now when you run tests → they pass (Green ✅).


---

Step 3: Refactor (if needed)

Improve code without breaking tests.

Example: Add input validation or cleaner methods.



---

🔹 C++ Example (GoogleTest Framework)

Test File (test_calculator.cpp):

#include "calculator.h"
#include <gtest/gtest.h>

TEST(CalculatorTest, AddTest) {
    Calculator calc;
    EXPECT_EQ(calc.add(2, 3), 5);
}

TEST(CalculatorTest, SubtractTest) {
    Calculator calc;
    EXPECT_EQ(calc.subtract(5, 2), 3);
}

Code File (calculator.h + calculator.cpp):

// calculator.h
class Calculator {
public:
    int add(int a, int b);
    int subtract(int a, int b);
};

// calculator.cpp
#include "calculator.h"
int Calculator::add(int a, int b) { return a + b; }
int Calculator::subtract(int a, int b) { return a - b; }


---

🔹 Benefits of TDD

Catches bugs early.

Makes code clean, simple, and testable.

Builds confidence → when refactoring, tests ensure nothing breaks.

Encourages modular design.



---

🔹 TDD Workflow (Always Remember)

1. Write a test → it fails.


2. Write the simplest code → test passes.


3. Refactor → code gets cleaner, tests still pass.




---

✅ Summary:

TDD is about tests first, code later.

Use unittest/pytest (Python) or GoogleTest (C++).

Always follow Red → Green → Refactor.



---
