# Time Complexity and Time 2
## Traversal of Binary Trees
* Traversal
  - Moving through all nodes of the binary tree, visiting each node in turn
  - The order of traversal should be logical
* At any given node in a binary tree, there are three tasks to do:
  - Visit the node itself (V)
  - Traverse its left subtree (L)
  - Traverse its right subtree (R)
* They are reduced to three if we always consider the left subtree before the right
  - Preorder: V L R
  - Inorder: L V R
  - Postorder: L R V
* <img width="862" alt="Screen Shot 2022-06-21 at 4 33 12 PM" src="https://user-images.githubusercontent.com/89602311/174900959-d71828b4-e065-4fce-9e7f-25a0702f9512.png">
* <img width="721" alt="Screen Shot 2022-06-21 at 4 38 32 PM" src="https://user-images.githubusercontent.com/89602311/174901622-c8744b1c-994f-4a2e-a592-07a4efa3e2ca.png">
* <img width="844" alt="Screen Shot 2022-06-21 at 4 43 28 PM" src="https://user-images.githubusercontent.com/89602311/174902196-ee2ca95a-1900-480b-897a-730e80fbe01a.png">
* <img width="447" alt="Screen Shot 2022-06-21 at 5 00 49 PM" src="https://user-images.githubusercontent.com/89602311/174904320-29edc64a-d59b-4719-b8f7-3446cbfa2c74.png">
## Linked Implementation of Binary Tree
* <img width="474" alt="Screen Shot 2022-06-21 at 5 01 21 PM" src="https://user-images.githubusercontent.com/89602311/174904377-fd6f3fe8-e0f3-4555-9ad7-aa84e16925e7.png">
* <img width="257" alt="Screen Shot 2022-06-21 at 5 01 35 PM" src="https://user-images.githubusercontent.com/89602311/174904416-acb136ee-dc53-48f3-966a-d82240db8b2e.png">
* <img width="455" alt="Screen Shot 2022-06-21 at 5 01 51 PM" src="https://user-images.githubusercontent.com/89602311/174904444-39b82a35-7f59-4c6d-80c3-a0f9b493d8e8.png">
* <img width="460" alt="Screen Shot 2022-06-21 at 5 02 03 PM" src="https://user-images.githubusercontent.com/89602311/174904467-f735dc85-3f0a-419b-9e3c-2b40583b5d71.png">
* How about iterative traversal
  - In order, post order, pre order?
  - https://en.wikipedia.org/wiki/Tree_traversal
  - Use only one stack: mimic the call stack
  - Self test: try to implement the pseudo-code 
## Binary Search Tree
* Definition
  - A binary search tree (BST) is a binary tree that has binary search tree property:  
  - <img width="304" alt="Screen Shot 2022-06-21 at 5 04 21 PM" src="https://user-images.githubusercontent.com/89602311/174904730-25f05535-3b5a-4301-ad9f-7a6006396724.png">
* The binary search tree as a data structure has the concepts of ordering, paritioning, and linking
* Assumption:
  - No two entries in a binary search tree may have equal keys 
  - What if we need duplicates?
    - add a frequency field in the node class
* Pre order traversal?
  - <img width="464" alt="Screen Shot 2022-06-21 at 5 21 34 PM" src="https://user-images.githubusercontent.com/89602311/174906596-61c9d500-99d4-4eba-90bb-bf67287a7582.png">
* Recall:
  - Binary search O(log n) is much more efficient than sequential search O(n)
* Features of BST
  - searches quickly (as with binary search on a contigous list)
    - only need to look at one sub tree
  - makes insertions and deletions quickly (as with a linked list
    - Insert: the new node is always a leaf node?
    - Delete: how to find the max value in the subtree?
## Implementation of BST
* The binary search tree class is derived from the binary tree class
  - All binary tree methods are inherited
* <img width="407" alt="Screen Shot 2022-06-21 at 5 25 12 PM" src="https://user-images.githubusercontent.com/89602311/174906985-2fb4e3e1-7355-45a8-a450-54fe71dc4228.png">
* Tree search
  - To search for the target, first compare it with the entry at the root of the tree
    - If their keys match, then search finishes
    - Otherwise, depending on whether the target is smaller than or greater than the root, search goes to the left subtree or the right subtree as appropriate and repeat the search in that subtree
  - The process is implemented by calling an auxillary recursive function
* Tree Search
  - Implementation 1: similar as pre-order tranversal
  - <img width="456" alt="Screen Shot 2022-06-21 at 5 56 59 PM" src="https://user-images.githubusercontent.com/89602311/174910210-2010a3b9-61ce-49e2-ba38-4e6cafad9ca4.png">
* Tree Search
  - Implementation 2: iterative pre-order
    - Make use of BST features
  - <img width="445" alt="Screen Shot 2022-06-21 at 5 57 55 PM" src="https://user-images.githubusercontent.com/89602311/174910286-8228fa12-fad9-4a50-b593-cebcfcc0f3e6.png">
* Tree Search
  - Implementation 4
  - <img width="484" alt="Screen Shot 2022-06-21 at 5 58 30 PM" src="https://user-images.githubusercontent.com/89602311/174910324-b9c85bcd-3b4c-4ee5-8a66-3e27bbf513d1.png">
  - Time complexity?
    - Only one brunch is exploited. Depth of the lead node?
* Insert a node
  - In the tree find the location suitable to the new record
  - <img width="465" alt="Screen Shot 2022-06-21 at 5 59 49 PM" src="https://user-images.githubusercontent.com/89602311/174910448-15454a21-cbd4-4574-837a-d94a2bf57567.png">
* Insert a node
  - Insert: the new node is always a leaf node?
  - <img width="416" alt="Screen Shot 2022-06-21 at 6 00 49 PM" src="https://user-images.githubusercontent.com/89602311/174910534-84b08f8b-6a0b-4bf2-97c2-ab620be9821d.png">
* Insert a node
  - Insert: the new node is always a leaf node?
  - Time Complexity? Only one brunch is exploited. Height of the BST ?
  - <img width="455" alt="Screen Shot 2022-06-21 at 6 01 31 PM" src="https://user-images.githubusercontent.com/89602311/174910598-7291c784-8683-40a6-8867-e65878cf38e4.png">
* Insert a node
  - Same keys may be built into BSTs of different shapes, depending on the order of keys in an input
  - Definitions: depth (for a node) v.s. height (for the tree)
  - <img width="489" alt="Screen Shot 2022-06-21 at 6 02 04 PM" src="https://user-images.githubusercontent.com/89602311/174910657-019a1fef-9618-46a3-adf0-79f4eb31cb21.png">
* Insert a node
  - Height of a tree: the length of the longest downward path to a leaf from that node
  - For tree_search() and insert(), only one brunch is exploited
    - The time complexity will be bounded by the height of the BST (best case)
      - For optimal tree: the height is O(log n)
      - This will be the focus of the next chapter: balanced tree
    - What if average case? Strong math background. Not our focus
      - Discussed in graduate-level algorithm class: theta(sqrt(n))  after n^2 insertion/delete operations
* Delete a node
  - Deletion is hard
    - Case 1: if it is a leaf it can be deleted immediately 
    - Case 2: if it has one child, the node can be deleted after the parents adjust a link to bypass the node
    - Case 3: if it has two children, replace the node with the smallest data on the right subtree and recursively delete that node. (or replace the node with the largest data on the left subtree)
  - Lazy deletion is a popular strategy
    - When an element is to deleted, it is in the left tree and merely marked as being deleted
* <img width="439" alt="Screen Shot 2022-06-21 at 6 10 55 PM" src="https://user-images.githubusercontent.com/89602311/174911460-7af70798-e322-43a9-a0b9-78d98045bb16.png">
* Delete a node
  - We will do the actual delete in the implementation
    - leave the lazy deletion for the project
    - Case 3:
      - Try the smallest data on the right subtree (immediate successor): right subtree’s leftmost child
      - Or try the largest data on the left subtree (immediate predecessor): left subtree’s rightmost child
  - <img width="333" alt="Screen Shot 2022-06-21 at 6 13 20 PM" src="https://user-images.githubusercontent.com/89602311/174911659-f17fc07c-67dc-4002-85dd-f293cdec7e7c.png">
* Delete a node
  - We will do the actual delete in the implementation
    - leave the lazy deletion for the project
    - Case 3:
      - Try the smallest data on the right subtree (immediate successor): right subtree’s leftmost child
      - Immediate successor: next node in in-order traversal (Similar for immediate predecessor)
      - Where is the smallest data in BST? First node visited in in-order, No other node on the left, Leftmost node
      - E.g., to delete 15, we can replace it with 12 (immediate predecessor) or 16 (immediate successor)
* Delete a node
  - <img width="452" alt="Screen Shot 2022-06-21 at 6 23 08 PM" src="https://user-images.githubusercontent.com/89602311/174912506-de74e204-c7c0-4356-871a-a8c37205c669.png">
  - <img width="471" alt="Screen Shot 2022-06-21 at 6 23 18 PM" src="https://user-images.githubusercontent.com/89602311/174912531-ea541c63-93ed-4587-80b6-e4f0661f5e9d.png">
* Lazy deletion 
  - Check the project for details
  - Just mark the matched node as “deleted”
    - This could be a boolean field in the tree node struct
    - Set deleted as true
  - No need to actually delete it
  - Ignore the nodes marked deleted in traversal
  - If the “deleted” node is re-inserted, just remove the mark (set deleted as false)
  - Think about how height() and empty() are influence?
# Time Complexity of BST
* Recall that the maximum height of a n-node binary tree is n
  - The worst case running time of search, insert, and delete is theta(n)
* Recall that the minimum height of a binary tree with n nodes is ceil(log2(n+1))
  - The best case running time of search, insert, and delete is theta(log n)
* Observe  that the height of the tree determines time complexity of search, insert, and delete
* The average case could be different
  - Lazy deletion could potentially save some time
  - A balanced tree is a better solution
    - Expect AVL tree in the next chapter
## Self Test
* Binary tree level traversal
  - Traverse level by level
* Zig-zag level traversal?
  - https://leetcode.com/problems/binary-tree-zigzaglevel-order-traversal/
* Lowest common ancestor?
  - https://leetcode.com/problems/lowest-commonancestor-of-a-binary-tree/
* For a given BST, can you give a possible insertion order of the nodes?
    

