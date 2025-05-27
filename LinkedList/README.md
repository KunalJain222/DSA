# 🔗 Linked Lists in Python

This repository provides an in-depth explanation of **Linked Lists**—a fundamental data structure in computer science. You’ll learn **what a linked list is**, **its types**, how to **implement each type in Python**, and the **advantages, disadvantages, and real-world use cases** of linked lists.

---

## 📘 What is a Linked List?

A **Linked List** is a linear data structure in which elements (nodes) are not stored in contiguous memory locations. Each node contains two parts:

1. **Data**: The value stored in the node.
2. **Pointer**: A reference to the next node in the sequence.

Unlike arrays, linked lists do not require pre-defined size and allow dynamic memory allocation.

A linked list is a data structure containing two crucial pieces of information, the first being the data and the other being the pointer to the next element. The ‘head’ is the first node, and the ‘tail’ is the last node in a linked list.

<img width="276" alt="image" src="https://github.com/user-attachments/assets/646097d8-5b43-4229-9d9f-7d6fa532b119" />


---

## 📂 Types of Linked Lists

1. **Singly Linked List**  
   Each node points to the next node.

   <img width="274" alt="image" src="https://github.com/user-attachments/assets/34de666c-ff2e-49a6-a98d-0f310ce447fe" />

3. **Doubly Linked List**  
   Each node points to both the next and the previous node.

   <img width="307" alt="image" src="https://github.com/user-attachments/assets/2b3f94c4-3bb7-45c4-94aa-895997b4bd9a" />
   
5. **Circular Linked List**  
   The last node points back to the first node to form a circle.

   <img width="269" alt="image" src="https://github.com/user-attachments/assets/94045e39-f60d-4b7b-b18c-55a36aa1ca18" />
   
7. **Circular Doubly Linked List**  
   Similar to a doubly linked list, but the last node links to the first and vice versa.

---
## Understanding Pointers
A pointer is a variable that stores the memory address of another variable. In simpler terms, it "points" to the location in memory where data is stored. This allows you to indirectly access and manipulate data by referring to its memory address.

---
## 🛠️ How to Implement Linked Lists in Python
### 1. Singly Linked List
class Node:
    def __init__(self, data=None, next=None):
        self.data = data
        self.next = next
        
class LinkedList:
    def __init__(self):
        self.head = None
    
    def insert_at_beginning(self,data):
        node = Node(data, self.head) # You're creating a new Node.
        self.head = node #  this means the new node will point to the current head of the list.
    
    def print(self):
        if Node is None:
            print("Linked List is empty")
            return 
        
        itr = self.head
        llstr = ''

        while itr:
            llstr += str(itr.data) + '-->'
            itr = itr.next

        print(llstr)
    def insert_at_end(self, data):
        if self.head is None:
            self.head = Node(data, None)
            return 

        itr = self.head
        while itr.next:
            itr = itr.next
        
        itr.next = Node(data, None)

if __name__ == '__main__':
    ll = LinkedList()
    ll.insert_at_beginning(5)
    ll.insert_at_beginning(19)
    ll.insert_at_end(77)
    ll.print()
### 2. Doubly Linked List

class Node:
    def __init__(self, data=None, next=None, prev=None):
        self.data = data
        self.next = next
        self.prev = prev

class DoublyLinkedList:
    def __init__(self):
        self.head = None
    
    def insert_at_beginning(self, data):
        node = Node(data, self.head, None)
        if self.head:
            self.head.prev = node
        self.head = node
    
    def insert_at_end(self, data):
        if self.head is None:
            self.head = Node(data, None, None)
            return

        itr = self.head
        while itr.next:
            itr = itr.next

        new_node = Node(data, None, itr)
        itr.next = new_node

    def print_forward(self):
        if self.head is None:
            print("Doubly Linked List is empty")
            return

        itr = self.head
        dll_str = ""
        while itr:
            dll_str += str(itr.data) + " <--> "
            itr = itr.next
        print("Forward:", dll_str.rstrip(" <--> "))

    def print_backward(self):
        if self.head is None:
            print("Doubly Linked List is empty")
            return

        # Go to the last node
        itr = self.head
        while itr.next:
            itr = itr.next

        dll_str = ""
        while itr:
            dll_str += str(itr.data) + " <--> "
            itr = itr.prev
        print("Backward:", dll_str.rstrip(" <--> "))

    if __name__ == '__main__':
        dll = DoublyLinkedList()
        dll.insert_at_beginning(5)
        dll.insert_at_beginning(19)
        dll.insert_at_end(77)
        dll.print_forward()
        dll.print_backward()
