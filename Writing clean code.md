
# 🧑‍💻 Step 2 → Writing Clean Code

🔹 Concept

Clean code means code that is easy to read, understand, and maintain.

Other developers (and your future self) should be able to quickly grasp what the code does.



---

🔹 Key Principles of Clean Code

1. Meaningful Names → Variables, functions, and classes should clearly say what they do.
❌ int x; ✅ int studentCount;


2. Small Functions → Each function should do only one thing.
❌ processStudentData() (too big)
✅ getStudentMarks(), calculateAverage(), printResult()


3. Consistent Formatting → Proper indentation, spacing, and structure.


4. Avoid Duplication → Don’t copy-paste the same code in multiple places. Extract into functions.


5. Comments for Why, not What → Write comments to explain why you did something, not obvious details.




---

🔹 Example (Bad Code in C++)

#include <iostream>
using namespace std;

int main() {
    int a, b, c;
    cout << "Enter marks in 3 subjects: ";
    cin >> a >> b >> c;
    int d = a + b + c;
    double e = d / 3.0;
    if (e >= 50)
        cout << "Pass";
    else
        cout << "Fail";
}

Problems here:

Variables have meaningless names (a, b, c, d, e).

Logic is all inside main().

No comments.



---

🔹 Example (Clean Code in C++)

#include <iostream>
using namespace std;

// Function to calculate average marks
double calculateAverage(int mark1, int mark2, int mark3) {
    return (mark1 + mark2 + mark3) / 3.0;
}

int main() {
    int subject1, subject2, subject3;
    cout << "Enter marks in 3 subjects: ";
    cin >> subject1 >> subject2 >> subject3;

    double average = calculateAverage(subject1, subject2, subject3);

    if (average >= 50)
        cout << "Pass" << endl;
    else
        cout << "Fail" << endl;

    return 0;
}

✅ Improvements:

Clear variable names (subject1, average).

Logic moved to a separate function.

Comment explains function purpose.

Easy to read and maintain.



---

🔹 Example in Python (Clean Code Style)

def calculate_average(marks):
    return sum(marks) / len(marks)

def main():
    marks = [int(x) for x in input("Enter marks in 3 subjects: ").split()]
    average = calculate_average(marks)
    print("Pass" if average >= 50 else "Fail")

if __name__ == "__main__":
    main()


# the best write clean code notes on our page, check write clean code repository you got a better idea 💡 
