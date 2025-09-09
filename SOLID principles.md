# 🧑‍💻 Step 6 → SOLID Principles

🔹 Concept

SOLID is a set of five principles that make Object-Oriented code more maintainable, flexible, and scalable.
Each letter stands for a principle:

1. S → Single Responsibility Principle (SRP)


2. O → Open/Closed Principle (OCP)


3. L → Liskov Substitution Principle (LSP)


4. I → Interface Segregation Principle (ISP)


5. D → Dependency Inversion Principle (DIP)




---

🔹 1. Single Responsibility Principle (SRP)

A class should have only one reason to change.

Each class = one job.


Bad Example (C++):

class Report {
public:
    void generateReport() { /* logic */ }
    void printReport() { /* printing logic */ }
    void saveToFile() { /* file handling logic */ }
};

👉 Problem: This class does too many things (generate + print + save).

Refactored (Good Example):

class ReportGenerator {
public:
    void generateReport() { /* logic */ }
};

class ReportPrinter {
public:
    void printReport() { /* printing logic */ }
};

class ReportSaver {
public:
    void saveToFile() { /* file handling logic */ }
};

✅ Each class has one responsibility.


---

🔹 2. Open/Closed Principle (OCP)

Classes should be open for extension, but closed for modification.

Add new behavior without changing existing code.


Example (Python – Shape Area):

class Shape:
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, r):
        self.r = r
    def area(self):
        return 3.14 * self.r * self.r

class Square(Shape):
    def __init__(self, s):
        self.s = s
    def area(self):
        return self.s * self.s

shapes = [Circle(5), Square(4)]
for shape in shapes:
    print(shape.area())

✅ If you want a new shape (Triangle), just add a new class. No need to modify old code.


---

🔹 3. Liskov Substitution Principle (LSP)

Subclasses should be substitutable for their parent class.

If B is a subclass of A, then B objects should work anywhere A is expected.


Bad Example (C++):

class Bird {
public:
    virtual void fly() {}
};

class Ostrich : public Bird {
public:
    void fly() override { throw "Can't fly!"; }
};

👉 Ostrich violates LSP because it cannot fly, but it’s forced to implement fly().

✅ Fix → Create better class hierarchy:

class Bird {};
class FlyingBird : public Bird {
public:
    virtual void fly() = 0;
};
class Ostrich : public Bird {};
class Sparrow : public FlyingBird {
public:
    void fly() override { /* logic */ }
};


---

🔹 4. Interface Segregation Principle (ISP)

Don’t force classes to implement methods they don’t use.

Better to have many small interfaces than one large interface.


Bad Example (Python):

class Worker:
    def work(self): pass
    def eat(self): pass

class Robot(Worker):
    def work(self): print("Robot working")
    def eat(self): pass  # meaningless for Robot

Good Example:

class Workable:
    def work(self): pass

class Eatable:
    def eat(self): pass

class Human(Workable, Eatable):
    def work(self): print("Human working")
    def eat(self): print("Human eating")

class Robot(Workable):
    def work(self): print("Robot working")

✅ Now Robot doesn’t need useless eat() method.


---

🔹 5. Dependency Inversion Principle (DIP)

High-level modules should not depend on low-level modules.

Both should depend on abstractions (interfaces).


Bad Example (C++):

class MySQLDatabase {
public:
    void saveData() { /* MySQL save logic */ }
};

class App {
    MySQLDatabase db;
public:
    void save() { db.saveData(); }
};

👉 App is tightly coupled to MySQL.

Good Example (C++ with Interface):

class Database {
public:
    virtual void saveData() = 0;
};

class MySQLDatabase : public Database {
public:
    void saveData() override { /* MySQL logic */ }
};

class MongoDB : public Database {
public:
    void saveData() override { /* MongoDB logic */ }
};

class App {
    Database* db;
public:
    App(Database* database) : db(database) {}
    void save() { db->saveData(); }
};

int main() {
    MySQLDatabase mysql;
    App app(&mysql);
    app.save();
}

✅ Now App can work with any database (MySQL, MongoDB, etc.).


---

🔹 Summary of SOLID

1. SRP → One class = One responsibility.


2. OCP → Open to extend, closed to modify.


3. LSP → Subclasses should work like parent classes.


4. ISP → Don’t force unused methods.


5. DIP → Depend on abstractions, not concrete classes.
