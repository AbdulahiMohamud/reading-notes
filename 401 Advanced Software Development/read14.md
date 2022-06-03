# Trees

## Common Terminology

- **Node** - A Tree node is a component which may contain it’s own values, and references to other nodes
- **Root** - The root is the node at the beginning of the tree
- **K** - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
- **Left** - A reference to one child node, in a binary tree
- **Right** - A reference to the other child node, in a binary tree
- **Edge** - The edge in a tree is the link between a parent and child node
- **Leaf** - A leaf is a node that does not have any children
- **Height** - The height of a tree is the number of edges from the root to the furthest leaf

## Binary Tree

### Depth First Traversal for a Binary tree

1. Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root. Here are three methods for depth first traversal:

- **Pre-order**: root >> left >> right
- **In-order**: left >> root >> right
- **Post-order**: left >> right >> root

- Big O for Additional space = O(h) which is O(n) and Time = O(n)
  
- Uses call stack recursive Traversal

### Breadth First Traversal Binary tree

2. Breadth first traversal iterates through the tree by going through each level of the tree node-by-node.

- Big O for Additional space = O(w) which is O(n) and time = O(n)

- breadth first traversal uses a queue (instead of the call stack via recursion) to traverse the width/breadth of the tree

## K-ary Trees

- If Nodes are able have more than 2 child nodes, we call the tree that contains them a K-ary Tree.
- In this type of tree we use K to refer to the maximum number of children that each Node is able to have.

### Breadth First Traversal for a K-ary tree

- Traversing a K-ary tree requires a similar approach to the breadth first traversal. We are still pushing nodes into a queue, but we are now moving down a list of children of length k, instead of checking for the presence of a left and a right child.

#### Note

- Because there are no structural rules for where nodes are “supposed to go” in a binary tree, it really doesn’t matter where a new node gets placed.

- One strategy for adding a new node to a binary tree is to fill all “child” spots from the top down. To do so, we would leverage the use of breadth first traversal.

- In the event you would like to have a node placed in a specific location, you need to reference both the new node to create, and the parent node upon which the child is attached to.

### Big O

- The Big O time complexity for inserting a new node is O(n)

- Searching for a specific node will also be O(n).

- The Big O space complexity for a node insertion using breadth first insertion will be O(w).where w is the largest width of the tree.

## Binary Search Trees

- A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.

### Searching a BST

- Searching a BST can be done quickly, because all you do is compare the node you are searching for against the root of the tree or sub-tree. If the value is smaller, you only traverse the left side. If the value is larger, you only traverse the right side.

- The best way to approach a BST search is with a while loop.We cycle through the while loop until we hit a leaf, or until we reach a match with what we’re searching for

### Big O for BST

- The Big O time complexity of a Binary Search Tree’s insertion and search operations is O(h), or O(height)

- In the worst case, we will have to search all the way down to a leaf, which will require searching through as many nodes as the tree is tall. In a balanced (or “perfect”) tree, the height of the tree is log(n).

- In an unbalanced tree, the worst case height of the tree is n.

- The Big O space complexity of a BST search would be O(1). During a search, we are not allocating any additional space.


## Reference and Citation

> Hambalieu Jallow <