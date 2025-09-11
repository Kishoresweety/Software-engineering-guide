# 📚 Data Structures & Algorithms (DSA)

🔹 What are Data Structures?

Data Structure = A way to store and organize data so that operations can be performed efficiently.

Example:

A list/array → stores items in order.

A stack → Last In First Out (like a plate stack).

A queue → First In First Out (like people in line).




---

🔹 What are Algorithms?

Algorithm = A step-by-step procedure to solve a problem.

Example: Recipe for cooking → instructions to achieve a result.



---

🔹 Why DSA is Important?

Makes you a better problem solver.

Essential for coding interviews (Zoho, Google, Microsoft, etc.).

Helps in efficient software design (fast, optimized).



---

🔹 Learning Roadmap (One by One)

Step 1: Basics of Complexity

Time Complexity = how fast algorithm runs.

Big-O Notation:

O(1) → Constant time

O(log n) → Logarithmic (Binary Search)

O(n) → Linear (Loop through array)

O(n log n) → Sorting algorithms

O(n²) → Nested loops




---

Step 2: Arrays

Store items in a contiguous memory block.

Example (C++):


#include <iostream>
using namespace std;

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    for(int i = 0; i < 5; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}


---

Step 3: Strings

Sequence of characters.

Example (Python):


name = "Kishore"
print(name.upper())   # KISHORE
print(name[::-1])     # erohsiK (reverse)


---

Step 4: Linked List

Elements (nodes) connected with pointers.

Example (C++ simple linked list):


#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

int main() {
    Node* head = new Node{10, nullptr};
    head->next = new Node{20, nullptr};
    head->next->next = new Node{30, nullptr};

    Node* temp = head;
    while(temp) {
        cout << temp->data << " ";
        temp = temp->next;
    }
}


---

Step 5: Stacks & Queues

Stack (LIFO): Undo in text editor.

Queue (FIFO): Printing jobs in printer.


Python Example (Stack using list):

stack = []
stack.append(1)   # push
stack.append(2)
print(stack.pop())  # pop → 2

Python Example (Queue using collections):

from collections import deque
queue = deque([1, 2, 3])
queue.append(4)   # enqueue
print(queue.popleft())  # dequeue → 1


---

Step 6: Trees & Graphs

Tree: Hierarchical structure (family tree, file system).

Graph: Nodes + edges (social networks, maps).



---

Step 7: Algorithms

Searching (Linear Search, Binary Search)

Sorting (Bubble, Merge, Quick)

Recursion (function calls itself)

Dynamic Programming (optimize overlapping problems)

Graph Algorithms (DFS, BFS, Dijkstra’s)



---

🔹 Practice Strategy

1. Start with Arrays, Strings, Linked Lists.


2. Then move to Stacks, Queues, Trees, Graphs.


3. Learn Searching + Sorting.


4. Finally, Dynamic Programming & Advanced Graphs.




---

✅ Summary:

DSA = foundation of efficient coding.

Start from Arrays → Strings → Linked List → Stack → Queue → Trees → Graphs → Algorithms.

Focus on time complexity + practice problems.


