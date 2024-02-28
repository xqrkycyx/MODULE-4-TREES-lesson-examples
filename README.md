# 1.4.3 Implementation and Runtime

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

## Insertion

When you're inserting a new node into a tree, there are two base cases that you should consider:

- If there is no existing tree, then the first item that you insert will be inserted as the root of the tree.

- If you start with an existing tree, then you have to find the right place for the item that you want to insert and then insert it.

Suppose that you have an existing tree, as shown below, and you want to insert the key 10 into this existing tree.

![Example of a binary tree.](https://images.ctfassets.net/c7lxnbtvvcxm/oHuhpfohwgnSwnLFLa12s/40e1c69c5157e82dd72042f7e9786f98/Eng-BST-insert1.png)

Here is an algorithm that you might follow:

- Starting at the root, which is 5, compare the root with 10 (the key to insert) to see if 10 should be the left or the right child of 5. 10 is greater than 5. So, as you may recall from the definition of BST, it will be a right child of 5.

- 5 already has a right child, which is 19. So now you have to check to see if 10 should be on the left or the right side of 19. Because 10 is less than 19, it should be a left child of 19, so you follow the left path of 19.

- 19 already has a left child, 15, so now you have to check to see if 10 should be on the left or the right side of 15. Because 10 is less than 15, and 15 doesn't have a left child, you can insert 10 as a left child of 15.

This creates a tree that looks like this:

![Binary tree resulting from algorithm.](https://images.ctfassets.net/c7lxnbtvvcxm/1LB05nWFbSP0NPpLEaiSYy/4a98cd00b54330c62630b32faed7da43/Eng-BST-insert2.png)

## Retrieval

Retrieval of nodes follows a similar pattern as insertion. You check the value of the key against the key stored in a node in the BST and recursively follow the left or right branch.

Suppose you want to know if the key 18 is in the following tree:

Diagram illustrating question of whether 18 is in the binary tree.
You would use this process:

Starting at the root, you have to decide which path to follow to find 18. You check and see that 18 isn't the root. You see that 18 is greater than the root, so you follow the right child of the root, which is 19.

You compare 18 with the right child. Because 18 is less than the right child (19), you follow the left child of 19 (15).

You compare 18 with the left child. Because 18 is greater than the left child, you follow the right path of 15 and find 18.

The find() operation described above is implemented next.

## Removal

Removing items from a binary search tree is a little more tricky. First, use the find process described above to find the item that you want to remove. At this point, the removal process will differ depending on how many children that item has. The item that you want to remove will fit into one of the following three categories:

- No children (a leaf node)

- One child (left or right, doesn't matter)

- Two children (left and right)

### [](https://github.com/Thinkful-Ed/web-dev-programs/blob/master/library/zid-dsa-trees-02-implementation-and-runtime/content.md#node-with-no-children)Node with no children

If you find the item that you want to remove and it has no children, this will be the simplest case of removal. The idea is to detach this node from the parent. Suppose in the following example, you want to delete the item 18.

![Diagram showing intent to delete 18 from binary tree.](https://images.ctfassets.net/c7lxnbtvvcxm/6BFJFDOdJNcCeceUeUnU9Y/fb3c4afb2450613c7cf434fbcace9607/Eng-BST-remove1.png)

After you find 18, and see that 18 has no children, you remove it from the BST by breaking the link to the parent.

![Diagram showing removal of 18 from the BST by breaking the link to the parent.](https://images.ctfassets.net/c7lxnbtvvcxm/5jbPZMbgXxMzgf18ysnNte/c2633ea8019be436985909e8dd8b0728/Eng-BST-remove2.png)

The resulting tree looks as follows:

![Diagram showing the resulting binary tree with 18 removed.](https://images.ctfassets.net/c7lxnbtvvcxm/3P7RrtLSiM7yBf5JY5HEjI/e75baabdfecfb168830210e6eab883dc/Eng-BST-remove3.png)

### [](https://github.com/Thinkful-Ed/web-dev-programs/blob/master/library/zid-dsa-trees-02-implementation-and-runtime/content.md#node-with-one-child)Node with one child

Consider the following tree, and say that you want to remove the key 28 from it. The key 28 has one child, a left child: 21.

![Diagram showing the intent to remove 28 from the binary tree.](https://images.ctfassets.net/c7lxnbtvvcxm/6QhCtQxmAqkNz72MlzWCRt/0f42855f2e4e10269f665078ca4b93bd/Eng-BST-oneChild1.png)

If the item that you want to remove has one child, then you make the parent of the item that you are removing point to this one child. Then you detach the item that you want to remove from the parent. You will make 21 the right child of 19 and detach 28 from being the right child of 19.

This way, the child of the node that you removed (21) has a new parent (19), which was the parent of the node that you just removed.

![Diagram showing that the child (21) of the removed node (28) has a new parent (19), which was the parent of the removed node.](https://images.ctfassets.net/c7lxnbtvvcxm/44IKkVJKoxMMAsXvFtaSZW/f0d7dcf39e37109b18e40c162e643789/Eng-BST-oneChild2.png)

The resulting tree looks as follows:

![Diagram showing the resulting binary tree with 28 removed](https://images.ctfassets.net/c7lxnbtvvcxm/7z7h04KXvIdAxyJcueTW3h/257535b891f457bfa2ace80dfa219b02/Eng-BST-oneChild3.png)

Similarly, if you were to remove 15, which has one child (10), you would make 10 the left child of 19 and detach 15 from the tree.

### [](https://github.com/Thinkful-Ed/web-dev-programs/blob/master/library/zid-dsa-trees-02-implementation-and-runtime/content.md#node-with-two-children)Node with two children

The trickiest part of removal from a BST occurs when an item that you want to remove has both a left and a right child.

Imagine that you want to delete the root node of a BST. You are faced with the decision of which should replace the root. Each left and right child can have subtrees. And more importantly, you must retain the properties of the BST after you remove the node.

To delete a node from a BST that has two children, you must find a successor that will replace the removed node. To do so, follow these steps:

1.  Find the minimum value in the right subtree.

2.  Replace the value of the node to be removed with the found minimum. Now, the right subtree contains a duplicate.

3.  Apply remove() to the right subtree to remove the duplicate.

Suppose that you have the following BST. You will remove the node 19 from it. Notice that 19 has both a left and a right child.

![Diagram showing intent to remove 19 from the binary tree.](https://images.ctfassets.net/c7lxnbtvvcxm/2bCBjVJWInceYT04VQc3oA/83de308edc1f970d168210b9b17c6b81/Eng-BST-twoChilden1.png)

Start by finding a successor to replace 19. Find the minimum element in the right subtree of 19, which is 20. (Remember, according to the definition of a BST, the minimum value on the right side of a BST is the node in its leftmost subtree.)

![Diagram showing how to find a successor to replace 19 before removing it.](https://images.ctfassets.net/c7lxnbtvvcxm/2r57hOOsY3KG5NGMgcfqWi/94c7eec9cbe4406c23c2a515f3b2de3c/Eng-BST-twoChilden2.png)

Replace 19 with 20. In this case, only the values are replaced, not the nodes. You now have two nodes with the same value.

![Diagram showing two nodes with the same value.](https://images.ctfassets.net/c7lxnbtvvcxm/1X9MEoU8eApD7GguwDovga/4928b5b2aa28bc991810f006e85f7f0b/Eng-BST-twoChilden3.png)

Remove 20 from the left subtree. The resulting BST looks as follows:

![Resulting BST after removing 20.](https://images.ctfassets.net/c7lxnbtvvcxm/2eRWmSoSH4TcBZvyfKzP6n/2cb5ae1fb3ffee9f67d0a07b381141b0/Eng-BST-twoChilden4.png)
