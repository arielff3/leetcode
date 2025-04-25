---
up: Read and Write
parent: Read and Write
type: flashcard
---
## ✅ When to Use
Use when you want to **filter, deduplicate or overwrite an array in-place**, maintaining order, without using extra space.

## 🔧 Pattern Structure
```js
let write = 0;
for (let read = 0; read < nums.length; read++) {
  if (/* nums[read] is valid */) {
    nums[write] = nums[read];
    write++;
  }
}
return write; // new length
```

## 🔍 Practical Example – LeetCode 26 (Remove Duplicates)
**Input:** `[1,1,2,3]`  
**Expected Output:** `[1,2,3]`, return `3`

### Step-by-step:

| read | write | Action                        | Resulting array |
|------|-------|-------------------------------|-----------------|
| 0    | 0     | write 1                       | `[1,1,2,3]`     |
| 1    | 1     | skip (1 is duplicate)         | `[1,1,2,3]`     |
| 2    | 1     | write 2                       | `[1,2,2,3]`     |
| 3    | 2     | write 3                       | `[1,2,3,3]`     |

## ⏱️ Time & Space Complexity

- **Time:** O(n) – one pass over the array
- **Space:** O(1) – in-place modification

---

## 💡 Key Insight
- `read` moves forward scanning all values
- `write` only advances when a valid value is found
- Everything to the left of `write` is already "clean"

---

## 🧠 Bonus
This pattern also applies in:
- Remove Duplicates II (LC 80)
- Move Zeroes (LC 283)
- Compacting valid values in-place
