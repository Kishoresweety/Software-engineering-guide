# 👨‍💻 Code Review & Pair Programming

These are software engineering practices that make your code more reliable, readable, and professional.


---

🔹 1. Code Review

🔸 What is it?

Code Review = when another developer reviews your code before merging it.

Goal: Find bugs, improve readability, share knowledge, and maintain standards.


🔸 Code Review Checklist

When reviewing or writing code, check for:

1. Correctness – Does the code do what it should?


2. Readability – Is it easy to understand?


3. Simplicity – Is there unnecessary complexity?


4. Consistency – Does it follow naming, formatting, and project style guides?


5. Testing – Are there enough tests, and do they pass?


6. Security – Are there vulnerabilities (SQL injection, unsafe input, etc.)?




---

🔸 Example of Bad vs Good Code

❌ Bad:

def cal(x,y): return x+y

✅ Good:

def calculate_sum(a: int, b: int) -> int:
    """Return the sum of two integers."""
    return a + b

Clear function name ✅

Docstring ✅

Type hints ✅

Readable formatting ✅



---

🔸 Tools for Code Review

GitHub Pull Requests

GitLab Merge Requests

Bitbucket

Linters/Formatters (Black, Pylint, ESLint, clang-format)



---

🔹 2. Pair Programming

🔸 What is it?

Two developers working together on one computer (physically or remotely).

One is the Driver → writes code.

One is the Navigator → reviews in real time, thinks about design.



---

🔸 Benefits

1. Fewer bugs (two brains > one).


2. Faster learning for juniors.


3. Knowledge sharing across team.


4. Higher code quality.




---

🔸 Example Scenario

👨‍💻 Kishore (Driver): Writing function for login.
👩‍💻 Partner (Navigator): Suggests input validation, security improvements, better naming.

Driver writes → def login(user, pass): ...

Navigator says → “Rename pass (reserved keyword), add password hashing, test cases.”


✅ Together, they write clean, secure code.


---

🔹 Best Practices

For Code Review:

Keep reviews small and frequent.

Be respectful, focus on code not person.

Suggest improvements instead of commands.


For Pair Programming:

Switch roles (Driver ↔ Navigator).

Communicate constantly.

Use tools like Visual Studio Live Share, CodeTogether, Tuple for remote pairing.




---

✅ Summary:

Code Review = Reviewing code after it’s written.

Pair Programming = Writing code together in real time.

Both → improve code quality, collaboration, and learning.



---
