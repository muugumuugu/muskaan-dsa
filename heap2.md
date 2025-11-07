1️⃣ Heap - Real Life

Heap = ek special kind ka “priority queue”. Matlab, hamesha highest priority item ko easily access kar sakte ho.

Example 1: Leaderboard in a Game

Tumhare paas players ke scores hain:

Alice: 50
Bob: 30
Carol: 40


Tum chaahti ho ki hamesha top score dikhe.

Heap ka magic:

Root = max score (yahan 50)

Baaki scores tree ke nodes me arrange ho jaate hain.

Jab koi naya score aata hai, Tum usko insert karo aur adjust karo (heapify) → root automatically update ho jaata hai.

Visualize as tree:

      50 (Alice)
     /    \
   30(Bob) 40(Carol)


Logic:

Maximum hamesha upar, baki tree me order partially maintained.

Hume full sorting nahi chahiye, sirf “top element fast” chahiye → perfect for heap.

Example 2: Airport Boarding Queue (Min-Heap)

Passengers ke boarding priority hai: small kids first.

Queue = min-heap, jisme smallest priority number root pe

Jab passenger aata hai, insert karte ho → automatically heapify → smallest priority upar aa jaata hai.

2️⃣ Heap vs Binary Search Tree (BST)

BST me left < parent < right → in-order traversal se sorted milega

Heap me parent >= children (max heap) ya parent <= children (min heap) → sirf root guaranteed, baaki order nahi

So: Heap = fast max/min access, BST = fast search

3️⃣ Heapify – Simple analogy

Imagine:

Tumhare paas stack of books, aur Tum chaahti ho heaviest book hamesha top.

Agar koi new book insert ki jo heavier hai, aapko sirf “bubble up” karna hai → root (top) hamesha heaviest.

Yeh hi heapify hai: tree ke root ko fix karna taaki heap property maintain ho.

4️⃣ Heap in Arrays

Heap ko array me store kar sakte ho:

Root = arr[0]

Left child = arr[1]

Right child = arr[2]

Baaki automatically index se calculate

Example: Max-heap [50, 30, 40, 10, 20]

      50
     /  \
   30    40
  /  \
10    20


Array me: [50, 30, 40, 10, 20]

5️⃣ Heap Sort – Real-life analogy

Sorting a stack of papers by importance:

Stack = random order

Convert stack into heap → heaviest/top importance paper always upar

Upar wala paper nikal ke alag pile me rakho (sorted)

Repeat → sorted pile ready

Logic: Max-heap → repeatedly extract max → sorted array.

6️⃣ Nearly Sorted Array (k-inversion)

Scenario: dukaan me shelves pe items lagaye hain, lekin max k position off ho sakta hai.

Goal: Quick sort → n log k time

Method:

Heap size = k+1 (window of possible positions)

Hamesha smallest element ko pick karo → sorted order

Visual: Sliding window of k+1 items, har bar min/heapify → correct item mil jaaye
