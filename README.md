# Kth-Smallest-Element-in-a-BST
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def kthSmallest(self, root: TreeNode | None, k: int) -> int:
        r=[]
        def bst(root,r):
            if root is None:
                return 
            r.append(root.val)
            bst(root.left,r)
            bst(root.right,r)
        bst(root,r)
        n=len(r)
        r.sort()
        for i in range(n):
            if i==k-1:
                return r[i]
