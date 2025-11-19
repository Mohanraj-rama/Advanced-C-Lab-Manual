EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>

int stack[50];
int top = -1;

void display() {
    int i;
    if (top == -1) {
        printf("Stack is empty");
        return;
    }
    for (i = top; i >= 0; i--) {
        printf("%d ", stack[i]);
    }
}

void push(int x) {
    stack[++top] = x;
}

void pop() {
    if (top != -1) top--;
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

<img width="895" height="986" alt="image" src="https://github.com/user-attachments/assets/c9e2daef-b221-47d0-a963-4f76d192be55" />

Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>

int size = 50;
int top = -1;
float stack[50];

void push(float x) {
    if (top == size - 1) {
        printf("Stack Overflow");
        return;
    }
    stack[++top] = x;
}

int main() {
    float n;
    scanf("%f", &n);
    push(n);
    printf("%.2f", stack[top]);
    return 0;
}

```
Output:

<img width="875" height="896" alt="image" src="https://github.com/user-attachments/assets/9673fe7f-fb15-4961-9f72-e1b5a1fe6e1c" />


Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>

int queue[50];
int front = -1;
int rear = -1;

void display() {
    int i;
    if (front == -1) {
        printf("Queue is empty");
        return;
    }
    for (i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
}

void enqueue(int x) {
    if (rear == 49) return;
    if (front == -1) front = 0;
    queue[++rear] = x;
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

<img width="685" height="913" alt="image" src="https://github.com/user-attachments/assets/81f99c0c-ecd1-4b18-aeee-4dc3bc36f8cd" />

Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```
#include <stdio.h>

int size = 50;
int front = -1;
int rear = -1;
float queue[50];

void enqueue(float x) {
    if (rear == size - 1) {
        printf("Queue Overflow");
        return;
    }
    if (front == -1) front = 0;
    queue[++rear] = x;
}

int main() {
    float n;
    scanf("%f", &n);
    enqueue(n);
    printf("%.2f", queue[rear]);
    return 0;
}

```
Output:

<img width="756" height="909" alt="image" src="https://github.com/user-attachments/assets/1111a02f-5cb8-4100-a323-d592f2834d8f" />

Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```
#include <stdio.h>

int front = -1;
int rear = -1;
float queue[50];

void dequeue() {
    if (front == -1) {
        printf("Queue is empty");
        return;
    }
    front++;
    if (front > rear) {
        front = -1;
        rear = -1;
    }
}

void enqueue(float x) {
    if (rear == 49) return;
    if (front == -1) front = 0;
    queue[++rear] = x;
}

int main() {
    enqueue(100.5);
    enqueue(10.5);
    dequeue();
    enqueue(20.5);
    
    if (front != -1) printf("%.2f", queue[front]);
    return 0;
}


```
Output:

<img width="706" height="912" alt="image" src="https://github.com/user-attachments/assets/ff024827-3643-4a89-9e25-106504b02951" />

Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
