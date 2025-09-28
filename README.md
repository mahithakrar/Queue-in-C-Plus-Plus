#  Queue in C++

##  Overview
A **Queue** is a linear data structure that follows the **FIFO (First In, First Out)** principle.  
- The element that is inserted **first** is the one that gets **removed first**.  
- It is similar to a **real-life queue** (like a line of people waiting at a ticket counter).  
- Queues are widely used in **scheduling, resource management, and buffering**.  

In C++, a queue can be implemented using:
- Arrays  
- Linked Lists  
- The built-in **`queue` container** in the Standard Template Library (STL).  

---

##  Theory 

###  Characteristics of a Queue
- **FIFO order**: First element inserted is the first to be removed.  
- **Two main operations**:  
  - `enqueue` (insertion at the rear).  
  - `dequeue` (deletion from the front).  
- **Front**: Refers to the element that will be removed first.  
- **Rear**: Refers to the element where a new item will be inserted.  

---

###  Operations on a Queue
1. **Enqueue(x):** Add an element `x` at the **rear** of the queue.  
2. **Dequeue():** Remove an element from the **front** of the queue.  
3. **Peek/Front():** Get the element at the **front** without removing it.  
4. **isEmpty():** Check if the queue is empty.  
5. **isFull():** (in case of array implementation) Check if the queue is full.  

---

###  Types of Queues
- **Simple Queue:** Basic queue following FIFO.  
- **Circular Queue:** Last position is connected back to the first to make use of empty spaces.  
- **Double-Ended Queue (Deque):** Insertion and deletion allowed at both ends.  
- **Priority Queue:** Each element is assigned a priority; higher priority elements are dequeued first.  

---

###  Queue Implementation in C++
Queues can be implemented in two ways:  

- **Using Arrays**  
  - Easy to implement.  
  - Fixed size (may lead to overflow).  

- **Using Linked List**  
  - Dynamic memory allocation.  
  - No size limitation until memory is full.  

- **Using STL (`<queue>`):**  
  ```cpp
  #include <iostream>
  #include <queue>
  using namespace std;

  int main() {
      queue<int> q;
      q.push(10); // enqueue
      q.push(20);
      q.push(30);

      cout << "Front: " << q.front() << endl; // 10
      cout << "Rear: " << q.back() << endl;   // 30

      q.pop(); // dequeue
      cout << "After one pop, Front: " << q.front() << endl; // 20

      return 0;
  }
  ```

  # 📌 Program Summary and Algorithm  

## 📖 Program Summary  
This program demonstrates the **implementation of a queue using arrays in C++**.  

- A class `Queue` is defined with:  
  - An integer array `arr[SIZE]` to store elements.  
  - Two integer variables `front` and `rear` to track the queue positions.  
- Initially, `front = -1` and `rear = -1` (empty queue).  
- **Operations supported:**  
  - `enqueue(int value)` → Inserts an element at the rear of the queue.  
  - `dequeue()` → Removes an element from the front of the queue.  
  - `display()` → Displays all elements currently in the queue.  
- In the `main()` function:  
  - A queue is created.  
  - Elements `10`, `20`, and `30` are enqueued.  
  - The queue is displayed.  
  - One element is dequeued and the updated queue is displayed.  
  - Another element `40` is enqueued, and the queue is displayed again.  

This program highlights the basic working of a **FIFO (First In First Out) queue** using arrays.  

---

## ⚙️ Algorithm  

1. **Start** the program.  
2. Define a class `Queue` with:  
   - Integer array `arr[SIZE]`.  
   - Two integers `front` and `rear` initialized to `-1`.  
3. Define `enqueue(int value)` function:  
   - If `rear == SIZE - 1`, display **"Queue Overflow!"**.  
   - Else, if `front == -1`, set `front = 0`.  
   - Increment `rear` and insert the new element at `arr[rear]`.  
   - Print confirmation of insertion.  
4. Define `dequeue()` function:  
   - If `front == -1` or `front > rear`, display **"Queue Underflow!"**.  
   - Else, print the element at `arr[front]` and increment `front`.  
5. Define `display()` function:  
   - If `front == -1` or `front > rear`, display **"Queue is empty."**.  
   - Else, print all elements from `arr[front]` to `arr[rear]`.  
6. In `main()`:  
   - Create an object `q` of class `Queue`.  
   - Call `enqueue(10)`, `enqueue(20)`, and `enqueue(30)`.  
   - Call `display()`.  
   - Call `dequeue()` and `display()`.  
   - Call `enqueue(40)` and `display()`.  
7. **End** the program.  

---

#  Conclusion

- A **Queue** is a fundamental data structure that organizes data in a **FIFO (First In, First Out)** manner.  
- It is essential in **process scheduling, CPU task management, printer queues, and buffering of data**.  
- Different types of queues (**simple, circular, deque, priority queue**) allow **flexible handling of data**.  
- In C++, queues can be implemented using **arrays, linked lists, or the STL `queue` container**, making them **practical and versatile** in real-world applications.
