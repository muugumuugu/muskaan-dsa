Heap Visualization – Step by Step
Step 0: Array

Array = [4, 10, 3, 5, 1]

We want to heap sort this.

Step 1: Build Max Heap

Rule: Parent >= Children

Start from last non-leaf node → Heapify

Initial Tree (array as binary tree):
      4
     / \
   10   3
   / \
  5   1


Root 4 < left child 10 → swap

      10
     /  \
    4    3
   / \
  5   1


Node 4: 4 < 5 → swap

      10
     /  \
    5    3
   / \
  4   1


✅ Max-heap ready. Root = 10

Array representation: [10,5,3,4,1]

Step 2: Extract Max & Place at End

Swap root with last element:

Array: [1,5,3,4,10]   (10 placed at end, sorted)


Heapify root (size = 4):

Root 1 < left 5 → swap

      5
     / \
    1   3
   /
  4


Node 1 < child 4 → swap

      5
     / \
    4   3
   /
  1


Array now: [5,4,3,1,10]

Step 3: Repeat Extraction

Swap root with last of heap (size = 3):

Array: [1,4,3,5,10]


Heapify root:

Root 1 < left 4 → swap

      4
     / \
    1   3


Array: [4,1,3,5,10]

Step 4: Repeat

Swap root with last (size = 2):

Array: [1,4,3,5,10]


Heapify root:

Root 1 < child 4 → swap

      4
     /
    1


Array: [4,1,3,5,10]

Step 5: Last Element

Swap root with last (size = 1) → done

✅ Final sorted array: [1,3,4,5,10]

Visual Takeaways

Heapify = “bubble down”: Parent moves down to maintain heap property

Max element always at root → easy extraction

Heap sort = repeatedly extract root → sorted order

💡 Real-life analogy: Stack of papers

Each time, heaviest paper (max) upar

Pick it, place on separate pile → sorted pile grows

Bubble down remaining papers to maintain top-heavy stack
