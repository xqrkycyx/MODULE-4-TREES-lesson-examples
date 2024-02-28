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
