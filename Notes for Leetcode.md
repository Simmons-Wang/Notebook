# Notes for Leetcode

## Linked List

### 707

1. Setting the initial cur node at dummy_node instead of dummy_node.next is better,because we do not to discuss the operation for the head node seperately.
2. Compared the operation get, the operation deleteatindex and addatindex should fix the cur node at one node in front of the indexth node.

