# Stacks and Queues

## Stacks 

- A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous

###  Common terminology for a stack

1. **Push** - Nodes or items that are put or added into the stack are pushed.
2. **Pop** - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
3. **Top** - This is the top of the stack.
4. **Peek** - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.
5. **IsEmpty** - returns true when stack is empty otherwise returns false.

#### Note 

- Always check if its empty before you peek or pop into a stack.
- Pushing a Note into a Stack will always be an O(1) operation.it takes the same amount of time no matter how many Nodes (n) you have in the stack
- When adding a Node, you push it into the stack by assigning it as the new top, with its next property equal to the original top
- Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node is returned to the user.
- Typically, you would check isEmpty before conducting a pop. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.
- We do not re-assign the next property when we peek because we want to keep the reference to the next Node in the stack. This will allow the top to stay the top until we decide to pop.

> ALOGORITHM push(value)
// INPUT <-- value to add, wrapped in Node internally
// OUTPUT <-- none
node = new Node(value)
node.next <-- Top
top <-- Node

> ALGORITHM pop()
// INPUT <-- No input
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty
Node temp <-- top
top <-- top.next
temp.next <-- null
return temp.value

### LIFO OR FILO:

Stack follows these Concepts 
- LIFO - Last In First Out - This means that the last item added to the stack will be the first item popped out of the stack.

## QUEUE

- ###  Common terminology for a stack
1. Enqueue - Nodes or items that are added to the queue.
2. Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
3. Front - This is the front/first Node of the queue.
4. Rear - This is the rear/last Node of the queue.
5. Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
6. IsEmpty - returns true when queue is empty otherwise returns false.

### FIFO OR LILO

FIFO- First in First Out


## citation

- Hambalieu Jallow