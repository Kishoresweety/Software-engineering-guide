# 🏗️ System Design for Scalability & Fault Tolerance

🔹 What is System Design?

System design is about designing software systems that can:

Scale → Handle more users & data as the system grows.

Be Fault Tolerant → Continue working even if parts fail.

Perform Well → Fast response times.

Be Maintainable → Easy to update, extend, debug.



---

🔹 Key Concepts

1. Scalability

Vertical Scaling (Scale Up) → Add more power to one machine (CPU, RAM).

Horizontal Scaling (Scale Out) → Add more machines (distributed system).
👉 Example: Instead of one big server, use 10 smaller servers handling requests.



---

2. Load Balancing

Distributes traffic across multiple servers.

Prevents one server from overloading.

Example: Nginx, HAProxy, AWS Elastic Load Balancer.



---

3. Caching

Store frequently used data in fast memory (RAM).

Example:

User profile fetched once → cache it in Redis.

Next time, load from cache instead of database.




---

4. Database Scaling

Read Replicas → Multiple DB copies for read-heavy apps.

Sharding → Split large DB into smaller parts (e.g., users A–M on one server, N–Z on another).

NoSQL (MongoDB, Cassandra) → For flexible schema & high scale.



---

5. Fault Tolerance

Redundancy → Multiple copies of components (backup servers, DB replicas).

Failover → If one system fails, traffic switches to another.

Retries & Timeouts → Handle temporary failures gracefully.



---

6. High Availability (HA)

Systems designed to run 24/7 with minimal downtime.

Achieved by:

Load balancers

Replication

Monitoring & auto-restart (Kubernetes, AWS Auto Scaling).




---

7. Microservices Architecture

Instead of one monolith, split system into smaller independent services.

Example:

Auth Service

Payment Service

Notification Service


Benefits: Independent scaling, fault isolation, faster development.



---

8. Monitoring & Logging

Use tools like Prometheus, Grafana, ELK Stack.

Detect failures early & fix quickly.



---

🔹 Example: Scalable E-Commerce System

Imagine Amazon-like system:

1. Load Balancer → Distributes traffic to multiple app servers.


2. App Servers (Microservices) → Handle authentication, cart, orders.


3. Database →

Sharded user/order DB

Redis cache for popular products



4. Message Queue (Kafka, RabbitMQ) → For order processing asynchronously.


5. CDN → Serve images, videos fast.


6. Monitoring → Detect failures, auto-scale servers.




---

🔹 Fault Tolerance Example

👉 Say one database replica fails:

Load balancer redirects requests to another replica.

Auto-healing system (Kubernetes) restarts the failed DB.

Users don’t notice downtime.



---

🔹 Tools & Technologies

Load Balancing: Nginx, HAProxy, AWS ELB

Caching: Redis, Memcached

Databases: PostgreSQL, MongoDB, Cassandra, DynamoDB

Queues: Kafka, RabbitMQ, SQS

Containers: Docker, Kubernetes

Monitoring: Grafana, Prometheus, ELK



---

✅ Summary:

Scalability = Handle more users.

Fault Tolerance = Survive failures.

Use Load Balancing, Caching, DB Sharding, Microservices, Monitoring.

