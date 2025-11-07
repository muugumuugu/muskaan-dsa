Problem Reminder

Array: [6, 5, 3, 2, 8, 10, 9]

k = 3 → matlab har element max 3 positions off ho sakta hai

Goal: O(n log k) me sort karna

💡 Idea: Min-heap of size k+1

Kyun? Kyunki smallest element hamesha apni correct position me ho within the window of size k+1

Step 1: Initialize Min-Heap

Take first k+1 elements → [6,5,3,2]

Build min-heap: smallest element on top (root)

Heap looks like this (tree view):

        2
      /   \
    5       3
   /
  6


Array form: [2,5,3,6]

Root = 2 → smallest in first 4 elements

Step 2: Extract Min & Slide Window

Pop root (2) → place in sorted array

Sorted array so far: [2]

Push next element in array (8) → heapify → min-heap maintain

Heap now (after inserting 8):

        3
      /   \
    5       6
   /
  8


Array form: [3,5,6,8]

Step 3: Repeat Extraction

Pop root (3) → add to sorted array [2,3]

Push next element 10 → heapify

Heap:

        5
      /   \
    10      6
   /
  8


Sorted array: [2,3]

Step 4: Continue

Pop root (5) → [2,3,5]

Push next element 9 → heapify

Heap:

        6
      /   \
    10      9
   /
  8


Sorted array: [2,3,5]

Step 5: Finish Remaining Heap

Pop remaining elements one by one:

Pop 6 → [2,3,5,6]
Pop 8 → [2,3,5,6,8]
Pop 9 → [2,3,5,6,8,9]
Pop 10 → [2,3,5,6,8,9,10]


✅ Final sorted array: [2,3,5,6,8,9,10]

Visual Takeaways
Window = k+1 elements → kyunki element max k distance off ho sakta hai

Min-Heap → smallest element hamesha root pe → hum extract karte hi correct sorted position me dalte hain

Insertion + extraction = log(k) → total time O(n log k)

Ye heap ka real life analogy hai: imagine supermarket shelf pe products thode shuffled hain (max k distance off), aap basket of size k+1 leke minimum price wala product hamesha pick karte jao → sorted checkout
