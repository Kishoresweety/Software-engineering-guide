# 🏗️ Step 7 → Domain-Driven Design (DDD)

🔹 Concept

Domain = the core business problem you’re solving.

Domain-Driven Design (DDD) is a way of designing software that focuses on the business domain, not the technical details.

Instead of starting with “What database do we use?”, DDD starts with “What problem are we solving?”


👉 In short:

Talk to business experts → understand the problem deeply.

Model the domain in code using entities, value objects, aggregates.

Let the domain drive the design, not frameworks.



---

🔹 Building Blocks of DDD

1. Entity → An object with an identity (e.g., User, Order).


2. Value Object → No identity, defined only by values (e.g., Address, Money).


3. Aggregate → A group of related entities and value objects treated as one unit.

Example: Order (aggregate root) contains OrderItems.



4. Repository → Abstraction for retrieving/saving aggregates.


5. Service → Encapsulates domain logic that doesn’t fit into an entity.


6. Domain Events → Things that happen in the domain (e.g., OrderPlaced).


7. Ubiquitous Language → Shared language between developers and business experts.




---

🔹 Example → E-commerce (Order System)

1️⃣ Entity (Order & OrderItem)

import uuid

class OrderItem:
    def __init__(self, product_name, quantity, price):
        self.product_name = product_name
        self.quantity = quantity
        self.price = price

class Order:
    def __init__(self, customer_name):
        self.id = str(uuid.uuid4())
        self.customer_name = customer_name
        self.items = []

    def add_item(self, product_name, quantity, price):
        item = OrderItem(product_name, quantity, price)
        self.items.append(item)

    def total_price(self):
        return sum(item.quantity * item.price for item in self.items)


---

2️⃣ Value Object (Money)

class Money:
    def __init__(self, amount, currency="USD"):
        self.amount = amount
        self.currency = currency

    def __repr__(self):
        return f"{self.amount} {self.currency}"


---

3️⃣ Aggregate (Order is Root)

Order is the aggregate root.

All changes to OrderItem must go through Order.



---

4️⃣ Repository

class OrderRepository:
    def __init__(self):
        self.orders = {}

    def save(self, order):
        self.orders[order.id] = order

    def get(self, order_id):
        return self.orders.get(order_id)


---

5️⃣ Service (Place Order)

class OrderService:
    def __init__(self, repo):
        self.repo = repo

    def place_order(self, customer_name, items):
        order = Order(customer_name)
        for name, qty, price in items:
            order.add_item(name, qty, price)
        self.repo.save(order)
        print(f"Order placed for {customer_name}, Total: {order.total_price()}")
        return order


---

6️⃣ Usage Example

repo = OrderRepository()
service = OrderService(repo)

order = service.place_order("Kishore", [
    ("Laptop", 1, 50000),
    ("Mouse", 2, 500),
])

print("Fetched:", repo.get(order.id).total_price())

✅ This structure ensures the domain rules (Order, OrderItem, Money) are at the center, not the database or API.


---

🔹 Benefits of DDD

Keeps code aligned with business needs.

Handles complex domains easily.

Improves communication between developers & business experts.

Works great with Clean Architecture (DDD = what to build, Clean Arch = how to structure it).



---

💡 Quick Difference:

Clean Architecture = organizing code into layers.

DDD = modeling the business problem correctly.



---
