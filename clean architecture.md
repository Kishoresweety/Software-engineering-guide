# 🏗️ Step 6 → Clean Architecture

🔹 Concept

Clean Architecture is a way to organize code so that it is independent of frameworks, UI, databases, or external tools.

It focuses on separating concerns → each layer of code has its own responsibility.

The idea: Business rules shouldn’t depend on external systems.


Think of it like an onion 🧅 → at the core, we have business logic; outer layers handle details (DB, UI, APIs).


---

🔹 Layers of Clean Architecture

1. Entities (Core Business Rules)

Pure business logic → independent of everything.

Example: User, Order, Invoice.



2. Use Cases (Application Rules)

Orchestrates entities to solve business problems.

Example: “Register User”, “Place Order”.



3. Interface Adapters

Converts data from external systems (DB, Web, API) into entities/use cases.

Example: Controllers, Presenters, Repositories.



4. Frameworks & Drivers (Outer Layer)

Actual tech stuff (UI, Database, Web frameworks).

Example: Flask, Django, MySQL, REST API.





---

🔹 Rules of Clean Architecture

Dependency Rule: Code dependencies always point inward (towards business logic).

Inner layers never depend on outer layers.

Frameworks are plugged in, not hardcoded.



---

🔹 Example → User Registration

1️⃣ Entities (Core Business Object)

class User:
    def __init__(self, username, email):
        self.username = username
        self.email = email


---

2️⃣ Use Case (Business Rule)

class RegisterUserUseCase:
    def __init__(self, user_repo):
        self.user_repo = user_repo

    def execute(self, username, email):
        user = User(username, email)
        self.user_repo.save(user)
        return user


---

3️⃣ Interface Adapter (Repository)

class UserRepository:
    def __init__(self):
        self.users = []

    def save(self, user):
        self.users.append(user)
        print(f"User {user.username} saved!")


---

4️⃣ Framework Layer (Web API with Flask)

from flask import Flask, request, jsonify

app = Flask(__name__)
repo = UserRepository()
use_case = RegisterUserUseCase(repo)

@app.route("/register", methods=["POST"])
def register():
    data = request.json
    user = use_case.execute(data["username"], data["email"])
    return jsonify({"message": f"User {user.username} registered!"})

if __name__ == "__main__":
    app.run(debug=True)

✅ Notice how business logic (User, RegisterUserUseCase) doesn’t depend on Flask.
If tomorrow you switch Flask → FastAPI or Django, the core logic remains safe.


---

🔹 Benefits of Clean Architecture

Testable → business logic can be tested without UI/DB.

Flexible → swap databases, UI, or frameworks easily.

Maintainable → clear separation of responsibilities.



---

💡 Summary:

Entities = pure rules

Use Cases = application flow

Adapters = glue code

Frameworks = outer tools



---
