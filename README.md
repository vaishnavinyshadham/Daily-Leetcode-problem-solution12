# Daily-Leetcode-problem-solution12
PROBLEM

Given two integer arrays, preorder and postorder where preorder is the preorder traversal of a binary tree of distinct values and postorder is the postorder traversal of the same tree, reconstruct and return the binary tree.
If there exist multiple answers, you can return any of them.

Intuition

Preorder Traversal (Root → Left → Right) tells us the root node first.
Postorder Traversal (Left → Right → Root) tells us the root node last.
Since the values in the tree are distinct, we can uniquely identify each subtree.
The left subtree’s root (if it exists) is always the second element in preorder (i.e., preorder[1]).
The left subtree in postorder can be found by searching for preorder[1] and taking all elements up to it.

Approach

1. Base Case: If preorder is empty, return nullptr.
   
2. Create Root Node: First element in preorder is always the root.
   
3. Find Left Subtree Size: Locate preorder[1] in postorder to determine left subtree size.
   
4. Split Arrays for Recursion:
leftPre = preorder[1:1+size]
rightPre = preorder[1+size:]
leftPost = postorder[:size]
rightPost = postorder[size:len-1]

5. Recursive Calls: Construct left and right subtrees using these subarrays.
   
6. Return Root Node: Attach the left and right subtrees to the root and return.
   
Complexity

Time complexity:
O(n^2)

Space complexity:
O(n)

 
