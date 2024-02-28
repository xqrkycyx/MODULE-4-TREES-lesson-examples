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
