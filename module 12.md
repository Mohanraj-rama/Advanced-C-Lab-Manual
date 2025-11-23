

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
} *head = NULL;

void push(int x) {
    struct Node *newnode = malloc(sizeof(struct Node));
    newnode->data = x;
    newnode->next = head;
    head = newnode;
}

void display() {
    struct Node *p = head;
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
}

int main() {
    push(10);
    push(20);
    push(30);

    display();
    return 0;
}

```
Output:

<img width="1149" height="914" alt="image" src="https://github.com/user-attachments/assets/bc9c7ade-ccfb-428c-849e-e151e2619842" />


Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
} *head = NULL;

void push(int x) {
    struct Node *newnode = (struct Node*)malloc(sizeof(struct Node));
    newnode->data = x;
    newnode->next = head;
    head = newnode;
}

void pop() {
    if (head == NULL) {
        printf("Stack is empty");
        return;
    }
    struct Node *temp = head;
    head = head->next;
    free(temp);
}

void display() {
    struct Node *p = head;
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
}

int main() {
    push(10);
    push(20);
    push(30);

    pop();

    display();
    return 0;
}

```
Output:

<img width="1137" height="924" alt="image" src="https://github.com/user-attachments/assets/c1d8d54d-61d5-4ce2-b078-bdbc24cc39d5" />



Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int x) {
    struct Node *newnode = malloc(sizeof(struct Node));
    newnode->data = x;
    newnode->next = NULL;
    if (front == NULL) {
        front = rear = newnode;
    } else {
        rear->next = newnode;
        rear = newnode;
    }
}

void display() {
    if (front == NULL) {
        printf("Queue is empty");
        return;
    }
    struct Node *temp = front;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    return 0;
}

```
Output:

<img width="1141" height="956" alt="image" src="https://github.com/user-attachments/assets/72b27ad1-45e9-4121-94b5-e1dddf659de9" />

Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int x) {
    struct Node *p = (struct Node*)malloc(sizeof(struct Node));
    p->data = x;
    p->next = NULL;
    if (front == NULL) {
        front = p;
        rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void display() {
    struct Node *temp = front;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    return 0;
}

```
Output:

<img width="1139" height="905" alt="image" src="https://github.com/user-attachments/assets/b8604ee8-bc5d-477a-b9b1-2b303a9bacd8" />

Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

int peek() {
    if (front == NULL) {
        printf("Queue is empty");
        return -1;
    }
    return front->data;
}

int main() {
    struct Node *p1 = (struct Node*)malloc(sizeof(struct Node));
    p1->data = 10;
    p1->next = NULL;
    front = rear = p1;

    int val = peek();
    if (val != -1)
        printf("Peek element = %d", val);

    return 0;
}

```
Output:

<img width="1145" height="895" alt="image" src="https://github.com/user-attachments/assets/04ef3897-01b9-4e25-accc-11f43e846ef5" />



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


