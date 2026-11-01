Suppose we have a list of items and routinely want to insert and find items. Using an unordered list would provide a finding time of $O(1)$ but searching would take $O(n)$. However the search takes $O(n)$ time. I

If we use a sorted list, we can use binary searches that take $O(\log(n))$ time but inserting new items may take $O(n)$. 

If both insert and search operations need to be well below O(n), then one option is to store the items in  an ordered binary tree. 

Such tree is made of cells, with each having up to two pointers to other cells. 

# Sorted Binary Tree
A tree is sorted if and only if all nodes in the left subtree have smaller keys than the node's own key. A key can only appear at most once in the tree.