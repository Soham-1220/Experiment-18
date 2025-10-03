# Experiment-18

##  AIM
The aim of this program is to **implement a linear queue using arrays in C++**.  
The program provides basic queue operations such as:
- **Enqueue (Insertion)**: Adding an element at the rear end of the queue.  
- **Dequeue (Deletion)**: Removing an element from the front end of the queue.  
- **Display**: Showing the current elements present in the queue.  

This implementation helps us understand how a queue works internally, how memory is allocated in arrays, and how queue operations are executed using pointers (front and rear).



##  THEORY

### 1. Introduction to Queue
A **Queue** is a linear data structure that follows the **FIFO (First In, First Out)** principle. This means:
- The element that is **inserted first** will be the **first one to be removed**.  
- Think of it like a **real-life queue at a ticket counter**: the person who comes first gets served first.  

Queues are widely used in operating systems, scheduling algorithms, data buffering, and resource management.



### 2. Characteristics of a Queue
1. **Linear Order** – Elements are stored sequentially.  
2. **Two Pointers** –  
   - **Front** → Points to the first element.  
   - **Rear** → Points to the last element.  
3. **FIFO Principle** – Oldest element removed first.  
4. **Fixed Size (Array Implementation)** – Limited by the size of the array.  
5. **Overflow/Underflow Conditions** –  
   - **Overflow** occurs when the queue is full and a new element cannot be added.  
   - **Underflow** occurs when the queue is empty and a delete operation is attempted.



### 3. Operations on Queue
1. **Enqueue (Insertion)**  
   - Adds an element at the **rear**.  
   - Requires incrementing the `rear` pointer.  
   - If `rear` reaches the maximum size, the queue is full.  

2. **Dequeue (Deletion)**  
   - Removes an element from the **front**.  
   - Requires incrementing the `front` pointer.  
   - If `front > rear`, the queue becomes empty.  

3. **Display**  
   - Prints all elements from `front` to `rear`.  
   - Helps visualize the current state of the queue.



### 4. Limitations of Array-Based Queue
- **Wasted Space**: Once the front moves forward due to deletions, the empty spaces at the beginning cannot be reused.  
- To overcome this limitation, we use **circular queues** or **linked list queues**.  



### 5. Real-Life Examples of Queue
1. **Ticket Counter Queue** – First person in line is served first.  
2. **Printer Spooling** – Print jobs are executed in order they are received.  
3. **CPU Scheduling (FCFS)** – Processes are executed in the order they arrive.  
4. **Call Center Systems** – Calls are answered in order of arrival.  


##  ALGORITHM

### Step-by-Step Procedure
#### **1. Initialization**
- Start with an array of size `SIZE` (predefined).  
- Initialize two integer pointers:  
  - `front = -1` (no element yet).  
  - `rear = -1` (no element yet).  

#### **2. Enqueue (Insertion)**
1. Check if the queue is full:  
   - Condition: `rear == SIZE - 1`.  
   - If true → Print **Queue Overflow**.  
2. If the queue is empty:  
   - Set `front = 0`.  
3. Increment `rear` by 1.  
4. Insert the new element at `arr[rear]`.  
5. Print a message showing insertion.  

#### **3. Dequeue (Deletion)**
1. Check if the queue is empty:  
   - Condition: `front == -1 || front > rear`.  
   - If true → Print **Queue Underflow**.  
2. Print the element being deleted (`arr[front]`).  
3. Increment `front` by 1.  
4. If after deletion, `front > rear`, reset both to `-1` (queue becomes empty).  

#### **4. Display**
1. Check if the queue is empty:  
   - If yes → Print "Queue is empty".  
2. Otherwise, print elements from `front` to `rear`.  





##  CONCLUSION

The implementation of a **queue using arrays in C++** provides a practical understanding of how queue operations are executed at the programming level. By performing enqueue, dequeue, and display operations, we learned the following important lessons:

1. **Queue Basics in Action**  
   - The **FIFO principle** was successfully demonstrated.  
   - The first element inserted (`10`) was the first element to be deleted.  

2. **Role of Front and Rear Pointers**  
   - `front` always tracks the beginning of the queue.  
   - `rear` always tracks the end.  
   - Proper maintenance of these two variables ensures correctness.  

3. **Handling Overflow and Underflow**  
   - Overflow occurs when `rear == SIZE - 1`.  
   - Underflow occurs when `front > rear`.  
   - Both situations were tested and handled gracefully with error messages.  

4. **Efficiency Observed**  
   - Insertion (`enqueue`) is done in **O(1)** time.  
   - Deletion (`dequeue`) is also **O(1)**.  
   - Display requires **O(n)** time for traversing from `front` to `rear`.  

5. **Limitations Identified**  
   - Since this is a **linear queue**, once elements are dequeued, the empty spaces at the beginning cannot be reused.  
   - Example: If `SIZE = 5`, after inserting and deleting 5 elements, the queue will be considered "full" even though memory slots may be free at the front.  
   - This limitation motivates the use of **circular queues** or **linked lists**.  

6. **Practical Importance**  
   - Queues are widely applied in:  
     - CPU scheduling algorithms.  
     - Printer job scheduling.  
     - Call center systems.  
     - Data buffering in communication.  
   - By mastering basic queue operations, we are prepared to explore advanced structures like **priority queues, circular queues, and double-ended queues (deque)**.  

7. **Conceptual Clarity Achieved**  
   - Arrays provide a simple, static memory representation of queues.  
   - This project highlights both the strengths (simplicity, constant-time operations) and weaknesses (fixed size, wasted space).  
   - It establishes the foundation for exploring **dynamic queue implementations** using linked lists.  
