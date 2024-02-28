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
