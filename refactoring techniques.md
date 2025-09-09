# 🧑‍💻 Step 3 → Refactoring Techniques

🔹 Concept

Refactoring = Improving the structure of code without changing its behavior.

Think of it like cleaning your room: same things, but organized better.



---

🔹 Why Refactor?

1. To make code easier to read and maintain.


2. To reduce duplication.


3. To improve performance (sometimes).


4. To prepare code for new features.




---

🔹 Common Refactoring Techniques

1. Rename Variables/Functions → Give meaningful names.

❌ int x;

✅ int studentCount;



2. Extract Function → Move repeated logic into its own function.

Instead of writing the same formula in 3 places → put it in one function.



3. Simplify Conditionals → Avoid too many nested if statements.

❌ if(a) { if(b) { if(c) { ... }}}

✅ Use early returns or logical operators.



4. Remove Duplicated Code → Write reusable functions or classes.


5. Use Constants → Avoid “magic numbers”.

❌ if (marks >= 50)

✅ const int PASS_MARK = 50; if (marks >= PASS_MARK)





---

🔹 Example: Before Refactoring (Messy C++)

#include <iostream>
using namespace std;

int main() {
    int a, b, c;
    cout << "Enter marks in 3 subjects: ";
    cin >> a >> b >> c;

    int total = a + b + c;
    double avg = total / 3.0;

    if (avg >= 50) {
        cout << "Pass";
    } else {
        cout << "Fail";
    }
}

Problems:

Variables a, b, c are not meaningful.

No function reuse.

Hard to extend (e.g., if subjects increase).



---

🔹 After Refactoring (Clean C++)

#include <iostream>
#include <vector>
using namespace std;

const int PASS_MARK = 50;

// Function to calculate average of marks
double calculateAverage(const vector<int>& marks) {
    int sum = 0;
    for (int mark : marks) {
        sum += mark;
    }
    return static_cast<double>(sum) / marks.size();
}

int main() {
    vector<int> marks(3);
    cout << "Enter marks in 3 subjects: ";
    for (int& mark : marks) {
        cin >> mark;
    }

    double average = calculateAverage(marks);

    if (average >= PASS_MARK)
        cout << "Pass" << endl;
    else
        cout << "Fail" << endl;

    return 0;
}

✅ Refactored improvements:

Used vector → can scale easily.

Constants (PASS_MARK) used.

Function calculateAverage() for reusability.

Code easier to read.



---

🔹 Refactoring in Python (Cleaner Example)

PASS_MARK = 50

def calculate_average(marks):
    return sum(marks) / len(marks)

def print_result(marks):
    average = calculate_average(marks)
    print("Pass" if average >= PASS_MARK else "Fail")

def main():
    marks = [int(x) for x in input("Enter marks in 3 subjects: ").split()]
    print_result(marks)

if __name__ == "__main__":
    main()

✅ Here we extracted logic into functions and avoided duplication.


---

🔹 Summary

Refactoring = Improving structure, not functionality.

Techniques: Rename, Extract Functions, Remove Duplication, Use Constants, Simplify Conditionals.

Benefits: Clean, maintainable, extendable code.
