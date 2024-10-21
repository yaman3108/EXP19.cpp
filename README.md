# Experiment 19



## Aim:
To study and implement Queue implementation using array


## Apparatus:
Vs Code, Github


## Theory:

A queue is a linear data structure that follows the First In, First Out (FIFO) principle, meaning the first element added to the queue is the first one to be removed. Queues are commonly used in scenarios such as scheduling tasks, managing requests in a network, or any situation where items need to be processed in the order they arrive.

### Basic operations:
1: Enqueue: Adds an element to the end (rear) of the queue.

2: Dequeue: Removes an element from the front of the queue.

3: Front/Peek: Returns the front element without removing it.


## Explanation:

### Class Definition (Queue):

A class named Queue encapsulates the queue operations and attributes.
An array arr[] is used to store the queue elements.
Two integer variables, front and rear, track the front and rear positions in the array.
An integer size keeps track of the current number of elements in the queue.

### Constructor (Queue()):

Initializes front to 0, rear to -1, and size to 0, indicating that the queue is initially empty.
Enqueue Method (enqueue(int value)):
Checks if the queue is full. If so, it displays an error message.
Otherwise, increments rear in a circular manner and stores the value at arr[rear], then increments the size.

### Dequeue Method (dequeue()):

Checks if the queue is empty. If so, it displays an error message.
Otherwise, it increments front in a circular manner and decrements the size.

### Peek Method (peek()):

Returns the value at arr[front] without removing it.
If the queue is empty, it returns an error value.

## Code:

### Stack using array: 
```
#include<iostream>
using namespace std;
#define size 5
#define ERROR -9999

class Queue{
    int rear, front, ar[size];
    public:
    Queue(){
        rear= -1;
        front=-1;
        ar[0]=0;
    }
    void enqueue(int);
    int dequeue();
    void disp();
};
void Queue::enqueue(int num){
    if(rear==(size+1)){
        cout<<"Queue is full"<<endl;
    }
    else{
        if(front==-1){
            ar[++front]=num;
            rear++;
        }
        else{
            ar[++rear]=num;
        }
    }
}
int Queue::dequeue(){
    if(front==-1||front==(rear+1)){
        cout<<"Queue is empty"<<endl;
        return ERROR;
    }
    else{
        int val=ar[front++];
        return val;
    }
}
void Queue::disp(){
    if(front==-1||front==(rear+1)){
        cout<<"Queue is empty"<<endl;
        return;
    }
    else{
        int i=front;
        while(i!=(rear+1)){
            cout<<ar[i]<<"  ";
            i++;
        }
    }
}

int main(){
    Queue q1;
    q1.enqueue(4);
    q1.enqueue(8);
    q1.enqueue(3);
    int val=q1.dequeue();
    cout<<val<<endl;
    q1.disp();
```
### Output:
<img width="1040" alt="Screenshot 2024-10-21 at 2 01 51 PM" src="https://github.com/user-attachments/assets/f03e0305-e294-4343-85de-1122a211920b">


## Conclusion:
This program helps us understand how queue can be implemented using arrays. We learnt the different commands/keywords used in queue such as push, pop and peek.
