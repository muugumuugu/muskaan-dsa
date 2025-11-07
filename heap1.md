## **1️⃣ Heap Basics**

### **Heap kya hota hai?**

* Heap ek **complete binary tree** hota hai jisme **parent-child relationship maintain hota hai**.
* **Max-Heap**: Parent >= children
* **Min-Heap**: Parent <= children
* **Complete binary tree** ka matlab: Tree ke sare levels filled honge, except last level left-to-right filled hoga.

#### **Real-life example for heapify**

* Imagine **a leaderboard in a game**, jisme tumhe hamesha top score dekhna hai.

  * Jab naya score aata hai, tum usko insert karte ho aur fir **heapify** karte ho taaki top score **root pe** rahe.
  * Example:
    Scores = `[50, 30, 40, 10, 20]`

    * Max-heap banate hi root = 50, aur baki elements tree structure maintain karte hue place ho jaate hain.

---

### **Heapify kya hota hai?**

* Heapify = Ek node aur uske subtree ko heap property maintain karte hue arrange karna.
* Agar node violate kar rahi hai (child > parent in max-heap), swap karke niche ya upar bubble karna.

**Example:**
Array = `[10, 50, 20]` (root = 10)

* Max-heap ke liye root should be max. 10 < 50 → swap → `[50, 10, 20]`
* Heap property satisfied.

---

### **Array representation of heap**

Heap ko array me is tarah store karte hain:

```
Index i:
Left child = 2*i + 1
Right child = 2*i + 2
Parent = floor((i-1)/2)
```

**Example:**
Heap array `[50, 10, 20]` → Tree:

```
      50
     /  \
   10    20
```

---

## **2️⃣ Heap Sort Concept**

### **Heap sort ka idea**

1. Array ko **max-heap** me convert karo (`buildHeap` O(n))
2. Root (max element) ko array ke end me swap karo
3. Heap size reduce karo aur root ko heapify karo
4. Repeat till heap empty

* Time complexity: **O(n log n)**
* In-place sorting: Extra space O(1)

**Visualization (step-by-step)**:

Array = `[4, 10, 3, 5, 1]`

1. Build max heap → `[10, 5, 3, 4, 1]`
2. Swap root with last → `[1, 5, 3, 4, 10]`, heapify root → `[5, 4, 3, 1, 10]`
3. Swap root with last of reduced heap → `[1, 4, 3, 5, 10]`, heapify → `[4, 1, 3, 5, 10]`
4. Repeat → `[3, 1, 4, 5, 10]` … till sorted `[1, 3, 4, 5, 10]`

---

## **3️⃣ NlogK Sorting with k-Inversions**

### **Problem**

* Array me **har element max k-inversion** ke distance par hai.

  * Matlab, element apni correct sorted position se maximum `k` distance par ho sakta hai.
* Approach: **Min-heap of size k+1**

#### **Idea**

* Window of k+1 elements pe min-heap maintain karo
* Root ko remove karke sorted array me dalte jao
* Next element push karo heap me
* Kyunki heap size `k+1`, **insertion & deletion O(log k)** → Overall **O(n log k)**

#### **Example**

Array: `[6, 5, 3, 2, 8, 10, 9]`, k=3

1. First 4 elements heap → `[6,5,3,2]` → min-heap `[2,5,3,6]`
2. Pop 2 → sorted array `[2]`
3. Push next element 8 → heap `[3,5,6,8]`
4. Pop 3 → `[2,3]`
5. Continue → Final sorted `[2,3,5,6,8,9,10]`

✅ Yeh hi approach **“nearly sorted array”** sorting me use hoti hai.

---

## **4️⃣ Heap Sort in JavaScript**

```javascript
// Heapify function
function heapify(arr, n, i) {
    let largest = i;
    let left = 2 * i + 1;
    let right = 2 * i + 2;

    if (left < n && arr[left] > arr[largest]) {
        largest = left;
    }

    if (right < n && arr[right] > arr[largest]) {
        largest = right;
    }

    if (largest !== i) {
        [arr[i], arr[largest]] = [arr[largest], arr[i]]; // Swap
        heapify(arr, n, largest); // Recursive heapify
    }
}

// Heap sort function
function heapSort(arr) {
    let n = arr.length;

    // Build max heap
    for (let i = Math.floor(n / 2) - 1; i >= 0; i--) {
        heapify(arr, n, i);
    }

    // Extract elements from heap
    for (let i = n - 1; i > 0; i--) {
        [arr[0], arr[i]] = [arr[i], arr[0]]; // Move current root to end
        heapify(arr, i, 0); // heapify reduced heap
    }

    return arr;
}

// Example
let arr = [4, 10, 3, 5, 1];
console.log(heapSort(arr)); // [1,3,4,5,10]
```

✅ Variable names clear hain: `largest`, `left`, `right`, `n`

* Heapify recursively parent-child comparison karta hai.

---

### **5️⃣ K-Inversion Sorting (Min-Heap Approach)**

```javascript
function sort
```
