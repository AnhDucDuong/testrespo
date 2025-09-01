
# CptS 223 – Homework 2 Solutions

---

## 1. Reverse a Singly Linked List (5 pts)

### Pseudocode:
```
function reverseList(head)
    prev ← null
    pCur ← head

    while pCur ≠ null do
        pNext ← pCur.next
        pCur.next ← prev
        prev ← pCur
        pCur ← pNext
    end while

    return prev
```

### Explanation:
- We keep track of the previous node and reverse the links as we traverse.
- The final `prev` pointer is the new head of the reversed list.

---

## 2. Detect Cycle in Singly Linked List (5 pts)

### Pseudocode (Floyd’s Cycle Detection Algorithm):
```
function hasCycle(head)
    if head = null then return false

    slow ← head
    fast ← head

    while fast ≠ null and fast.next ≠ null do
        slow ← slow.next
        fast ← fast.next.next

        if slow = fast then
            return true
    end while

    return false
```

### Explanation:
- Two pointers move at different speeds. If a cycle exists, they will eventually meet.

---

## 3. Asymptotic Classification (3 pts)

Given: `f(n) = n^3 / 100 + 10n^2 + n + 3`

Correct options:
- ✅ (a) `O(n^3)`
- ✅ (b) `Ω(n^2)`
- ❌ (c) `Θ(n^2)`
- ✅ (d) `Θ(n^3)`
- ❌ (e) `o(n^2)`
- ❌ (f) `ω(n^2)`

### Reason:
The dominant term is `n^3`, so the function is in `Θ(n^3)`. It grows faster than `n^2`, so it is not `Θ(n^2)` or `o(n^2)`.

---

## 4. Sort by Growth Rate (6 pts)

```
{2/N}, 37, log log N, log N, log²N, log(N²), √N, N, N log log N, N log N,
{N log²N, N log(N²)}, N¹·⁵, N², N² log N, N³, 2^(N/2), 2^N
```

Group equal rates inside `{}`.

---

## 5. Asymptotic Proofs (8 pts)

### (i) Prove `5 lg n = o(n lg n)`

We want to show:
```
lim (n→∞) [5 lg n / (n lg n)] = 0
```
This simplifies to:
```
lim (n→∞) [5 / n] = 0 ✅
```
Hence, `5 lg n = o(n lg n)` is true.

---

### (ii) Prove `2 lg n = O(√n)`

We want constants `c > 0` and `n₀` such that:
```
2 lg n ≤ c√n for all n ≥ n₀
```

Try c = 5. For n = 16:
- LHS = 2 × 4 = 8
- RHS = 5 × 4 = 20 → LHS ≤ RHS ✅

So `2 lg n = O(√n)`.

---

## 6. Sorting Algorithm Complexity (8 pts)

Described algorithm is **Selection Sort**.

### Worst-case:
- Still compares every pair → `Θ(n²)`

### Best-case:
- No optimization for sorted input → also `Θ(n²)`

✅ Answer: `Θ(n²)` for both best and worst case.
