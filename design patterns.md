# 🧑‍💻 Step 4 → Design Patterns

🔹 Concept

Design Patterns are standard solutions to common software problems.

They are like blueprints → you don’t copy-paste them directly, but you adapt them to your problem.

They make code reusable, organized, and easier to maintain.



---

🔹 Types of Design Patterns

1. Creational Patterns → How objects are created.

Example: Singleton, Factory.



2. Structural Patterns → How classes/objects are arranged.

Example: Adapter, Decorator.



3. Behavioral Patterns → How objects communicate.

Example: Observer, Strategy.





---

🔹 Common Patterns (Beginner Friendly)

1️⃣ Singleton Pattern

Ensures only one instance of a class exists.

Example: Database connection, Logger.


C++ Example (Singleton Logger):

#include <iostream>
using namespace std;

class Logger {
private:
    static Logger* instance;  // single instance
    Logger() {}               // private constructor

public:
    static Logger* getInstance() {
        if (!instance) {
            instance = new Logger();
        }
        return instance;
    }

    void log(const string& message) {
        cout << "Log: " << message << endl;
    }
};

Logger* Logger::instance = nullptr;

int main() {
    Logger* logger1 = Logger::getInstance();
    Logger* logger2 = Logger::getInstance();

    logger1->log("App started");
    logger2->log("App running");

    cout << (logger1 == logger2 ? "Same instance" : "Different instances") << endl;
}

✅ Only one Logger exists even if called multiple times.


---

2️⃣ Factory Pattern

Hides object creation logic → useful when creating different types of objects.


Python Example (Shape Factory):

class Shape:
    def draw(self):
        pass

class Circle(Shape):
    def draw(self):
        print("Drawing Circle")

class Square(Shape):
    def draw(self):
        print("Drawing Square")

class ShapeFactory:
    def create_shape(self, shape_type):
        if shape_type == "circle":
            return Circle()
        elif shape_type == "square":
            return Square()
        else:
            return None

# Usage
factory = ShapeFactory()
shape1 = factory.create_shape("circle")
shape2 = factory.create_shape("square")

shape1.draw()
shape2.draw()

✅ Advantage: Adding new shapes later won’t break existing code.


---

3️⃣ Observer Pattern

One object (subject) notifies multiple objects (observers) when something changes.

Example: YouTube → when a creator uploads a video, all subscribers are notified.


C++ Example (Observer Pattern):

#include <iostream>
#include <vector>
using namespace std;

class Observer {
public:
    virtual void update(const string& message) = 0;
};

class Subscriber : public Observer {
    string name;
public:
    Subscriber(string n) : name(n) {}
    void update(const string& message) override {
        cout << name << " received: " << message << endl;
    }
};

class YouTubeChannel {
    vector<Observer*> subscribers;
public:
    void subscribe(Observer* obs) {
        subscribers.push_back(obs);
    }
    void notify(const string& message) {
        for (auto obs : subscribers) {
            obs->update(message);
        }
    }
};

int main() {
    YouTubeChannel channel;
    Subscriber s1("Kishore"), s2("Rahul");

    channel.subscribe(&s1);
    channel.subscribe(&s2);

    channel.notify("New Video Uploaded!");
}

✅ Multiple subscribers automatically get notified.


---

🔹 Why Patterns Are Important

You don’t reinvent the wheel.

Your code becomes familiar to other developers (they know the pattern).

Better scalability and maintainability.



---

✅ You just learned 3 important patterns:

Singleton (one instance)

Factory (object creation)

Observer (notification system)


