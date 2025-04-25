
## 🧠 What is it?

The **Boyer-Moore Voting Algorithm** is a clever technique used to find the **majority element** in a list (the element that appears more than ⌊n / 2⌋ times), assuming one always exists.

It operates in **O(n)** time and **O(1)** space using a simple counting mechanism — no sorting or extra memory required.

---

## ✅ When to Use

Use this algorithm when:

- The input guarantees that a **majority element exists**
    
- You need a **space-efficient** solution
    
- The problem involves finding a value that dominates in frequency
    

---

## 🔧 Code Example

```js
var majorityElement = function(nums) {
  let candidate = null;
  let count = 0;

  for (let num of nums) {
    if (count === 0) {
      candidate = num;
    }
    count += (num === candidate) ? 1 : -1;
  }

  return candidate;
};
```

---

## 🔁 How it Works

1. Start with `candidate = null` and `count = 0`
    
2. Traverse the array:
    
    - If `count === 0`, choose a new `candidate`
        
    - If the current number equals the candidate, `count++`
        
    - Otherwise, `count--`
        
3. At the end, `candidate` will be the majority element
    

The key idea: majority element survives the "vote balancing" process

---

## 📊 Example

Array: `[2,2,1,1,1,2,2]`

|num|candidate|count|
|---|---|---|
|2|2|1|
|2|2|2|
|1|2|1|
|1|2|0|
|1|1|1|
|2|1|0|
|2|2|1|

Final output: `2`

---

## ⏱️ Complexity

- **Time:** O(n)
    
- **Space:** O(1)
    

---

## 🧠 Key Insight

Boyer-Moore treats the problem like a **voting game** — opposing values cancel each other out. The one that remains at the end is the majority (if one exists).

---

## 🔗 Related Problems

- LC 169 – Majority Element
    
- LC 229 – Majority Element II (modified version)
    

---

## 🧭 Pattern Tags

- [[Flash card - Greedy]]