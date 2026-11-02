A tree is a non-empty set with an element that is designated as the root of the tree while the remaining elements are partitioned. ^[2]

The depth of a node is the length of the path or number of edges from root to that node.  

The height of a node is the longest path from that node to its leaves. The height of a tree is the height of the root. A leaf node has no children, its only path is up to its parent. 
# Binary Trees
Suppose we have a list of items and routinely want to insert and find items. Using an unordered list would provide a finding time of $O(1)$ but searching would take $O(n)$. However the search takes $O(n)$ time. ^[1]

If we use a sorted list, we can use binary searches that take $O(\log(n))$ time but inserting new items may take $O(n)$. ^[1]

If both insert and search operations need to be well below O(n), then one option is to store the items in a binary tree. ^[1]

Such tree is made of cells, with each having up to two pointers to other cells. 

A binary tree is tree that only has zero, one or two children. This assertion makes many tree operations simple and efficient.

# Sorted Binary Tree (Binary Search Tree)
A tree is sorted if and only if all nodes in the left subtree have smaller keys than the node's own key. A key can only appear at most once in the tree.

# Searching
To search for an item in a binary tree
1. Start at the root node
2. If the item you are searching for is less than current node move to the left child, other wise move to the right
3. Repeat this process until you have found the item you are looking for or until the node is a leaf. In this case the tree doesn't contain the item being searched. 

Searching takes $O(\log n)$. 

# Adding an Item
To add an item, you must first search through the tree until you find a leaf. Once at the leaf add the item as child on the leaf
# Deleting an Item
To delete an item, you must first search for an item and then remove the item form the parent node. 

# Traversal
Many problems require visiting the nodes of a tree in a systematic way: Tasks such as counting how many nodes exist or finding the maximum element.

There are three different methods possible for binary trees. Preorder, postorder and in-order.

- Preorder: Current node, left subtree, right subtree
- Postorder: Left subtree, right subtree, current node
- In-order: Left subtree, current node, right sutbree. 


--- 
[^1]: https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS10016_2026_TB-1/content/imperative/COMS10016_16_OR.pdf
[^2]: https://en.wikibooks.org/wiki/Data_Structures/Trees
[^3]: https://www.geeksforgeeks.org/dsa/introduction-to-tree-data-structure/


