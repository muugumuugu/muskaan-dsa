1️⃣ Heap Sort Visualization (Max-Heap)

Array = [4, 10, 3, 5, 1]

Step 0: Initial Tree
      4
     / \
   10   3
   / \
  5   1

Step 1: Build Max Heap (Heapify)

Root 4 < left child 10 → swap

      10
     /  \
    4    3
   / \
  5   1


Node 4 < child 5 → swap

      10
     /  \
    5    3
   / \
  4   1


Array representation: [10,5,3,4,1]

Step 2: Extract Max (Swap with Last)

Swap root 10 with last element 1 → [1,5,3,4,10]

Heapify root: 1 < 5 → swap → 1 < 4 → swap

      5
     / \
    4   3
   /
  1


Array: [5,4,3,1,10]

Step 3: Repeat Extraction

Swap root 5 with last in heap → [1,4,3,5,10]

Heapify root: 1 < 4 → swap

      4
     / \
    1   3


Array: [4,1,3,5,10]

Step 4: Continue

Swap 4 with last → [1,4,3,5,10]

Heapify root: 1 < 3 → swap

      3
     /
    1


Array: [3,1,4,5,10]

Swap 3 with last → [1,3,4,5,10] → done

✅ Final Sorted Array: [1,3,4,5,10]

2️⃣ k-Inversion / Nearly Sorted Array (Min-Heap)

Array = [6, 5, 3, 2, 8, 10, 9], k=3

Step 0: Build Initial Min-Heap (first k+1 elements)
Elements: [6,5,3,2] → Min-Heap:
        2
      /   \
    5       3
   /
  6

Step 1: Extract Min & Push Next

Pop 2 → sorted array [2]

Push 8 → heapify

        3
      /   \
    5       6
   /
  8

Step 2: Repeat

Pop 3 → [2,3]

Push 10 → heapify

        5
      /   \
    10      6
   /
  8


Pop 5 → [2,3,5]

Push 9 → heapify

        6
      /   \
    10      9
   /
  8


Pop remaining: [2,3,5,6,8,9,10]

✅ Sorted!

Visual Takeaways / Mind Tricks

Heap = priority tree → max/min hamesha root

Heapify = “bubble down / up”” → parent-child property maintain karna

Heap sort = extract root repeatedly → sorted

k-inversion = sliding min-heap → small window of k+1 → extract min → sorted in O(n log k)

Real-life analogies:

Heap Sort: Stack of papers → heaviest (or highest priority) paper always upar → pick & place on separate sorted pile

k-Inversion: Supermarket shelf → max k positions off → basket of size k+1 → pick cheapest (min) → checkout sorted
