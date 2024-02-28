# Module 4 Lesson Summaries: Trees

## 1.4.3 Implementation and Runtime

Branch: implementation-runtime-complete

1.  Binary Search Tree (BST) Implementation:

    - A BST is a hierarchical data structure consisting of nodes, where each node has a key, a value, and pointers to left and right children.
    - Nodes are inserted, retrieved, and removed in a BST according to certain rules, maintaining the BST properties.

2.  Insertion:

    - Insertion involves recursively finding the correct position for a new node based on its key.
    - Best case: O(1) when inserting the root node.
    - Average case: O(log n) for balanced trees.
    - Worst case: O(n) when the tree is heavily skewed.

3.  Retrieval:

    - Retrieval follows a similar process to insertion, recursively searching for a node based on its key.
    - Best case: O(1) when the node to find is the root node.
    - Average case: O(log n) for balanced trees.
    - Worst case: O(n) when the tree is heavily skewed.

4.  Removal:

    - Removal involves finding the node to remove and handling three cases: no children, one child, and two children.
    - For nodes with two children, a successor is found to maintain the BST properties.
    - Removal complexity follows similar patterns to insertion and retrieval.

5.  Complexity Analysis:

    - Best case: O(1) when operations are performed at the root node.
    - Average case: O(log n) for balanced trees due to the recursive nature.
    - Worst case: O(n) when the tree is heavily skewed, resulting in linear time complexity.

Understanding these operations and their runtime complexities is essential for effectively working with binary search trees.

## 1.4.4 Depth-First Search (DFS)

Branch: tree-dfs-complete

1.  Overview:

    - Searching through trees can be accomplished using depth-first search (DFS), which explores as far as possible in a subtree before backtracking and moving to the next subtree.
    - The lesson focuses on implementing in-order, pre-order, and post-order traversals using depth-first search.

2.  Key Terms:

    - Depth-first search (DFS): A tree-traversal algorithm that explores as far as possible in a subtree before backtracking and moving to the next subtree.
    - In-order traversal: Left branch of the node is visited, then the current node is handled, and finally the right branch is visited.
    - Pre-order traversal: Current node is handled first, then the left branch is visited, and finally the right branch is visited.
    - Post-order traversal: Left branch of the node is visited, then the right branch is visited, and finally the current node is handled.

3.  Implementation:

    - In-order Traversal: Implemented using a `dfsInOrder()` method which recursively processes the left node, then the current node, and finally the right node.
    - Pre-order Traversal: Implemented using a `dfsPreOrder()` method which recursively processes the current node, then the left node, and finally the right node.
    - Post-order Traversal: Implemented using a `dfsPostOrder()` method which recursively processes the left node, then the right node, and finally the current node.

4.  Complexity Analysis:

    - Since each node in the BST is visited, the time complexity in the worst case for all traversals is O(n), where n is the number of nodes in the tree.

## 1.4.5 Breadth-First Search (BFS)

Branch: tree-bfs-complete

1.  Overview:

    - In this lesson, learners explore another tree-traversal algorithm called breadth-first search (BFS), which traverses the tree level by level.
    - BFS starts at the root node and proceeds to explore each level of the tree before moving to the next level.

2.  Key Terms:

    - Breadth-first search (BFS): A tree-traversal algorithm that starts at the root node and explores the tree level by level.

3.  Implementation:

    - BFS is implemented using a first-in, first-out (FIFO) queue data structure.
    - The algorithm starts by enqueueing the root node into the queue and then dequeues nodes one by one, processing each node and enqueueing its children.
    - This process continues until all nodes in the tree have been visited.

4.  Complexity Analysis:

    - The runtime complexity of BFS is O(n), where n is the number of nodes in the tree.
    - Each node in the tree needs to be visited once, making it a linear time complexity algorithm.

5.  Code Implementation:

    - A `bfs()` method is added to the `BinarySearchTree` class, which initializes a queue, enqueues the root node, and then processes nodes level by level using a while loop.
    - Nodes are dequeued, their values are added to an array, and their children are enqueued for further exploration.

## 1.4.6 Solving Problems with Trees

Branch: solving-problems-with-trees-complete

1.  Overview:

    - This lesson delves into solving common coding challenges related to binary search trees (BSTs), leveraging the knowledge gained from implementing and traversing BSTs.

2.  Challenges:

    - Challenge 1: Height of a BST:

      - Objective: Write an algorithm to find the height of a BST.
      - Approach: Utilize a recursive approach to calculate the height of each subtree, propagating the height upward.
      - Method Added: `getHeight()` method to the `BinarySearchTree` class.
      - Complexity: Time - O(n), Space - O(h), where n is the number of nodes and h is the height of the tree.

    - Challenge 2: Is it a BST?:

      - Objective: Write an algorithm to check whether an arbitrary binary tree is a BST.
      - Approach: Perform an in-order traversal and check if the resulting array is sorted.
      - Method Added: `isBST()` method to the `BinarySearchTree` class.
      - Complexity: Time - O(n), Space - O(n).

    - Challenge 3: Third-largest node:

      - Objective: Write an algorithm to find the third-largest node in a BST.
      - Approach: Utilize an in-order traversal to generate a sorted array and find the kth largest node.
      - Method Added: `findKthLargestValue()` method to the `BinarySearchTree` class.
      - Complexity: Time - O(n), Space - O(n).

3.  Optimization:

    - Discussion on optimizing space complexity for the second and third challenges by avoiding the creation of an auxiliary array.

4.  General Notes:

    - Encouragement to explore alternative solutions and consider time-space complexity trade-offs.
    - Emphasis on leveraging traversal techniques learned earlier to tackle diverse algorithmic problems involving trees.
