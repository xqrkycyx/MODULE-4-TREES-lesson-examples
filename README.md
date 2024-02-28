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
