
## 🧠 What is it?

Kadane's Algorithm is a dynamic programming-inspired greedy technique used to find the **maximum subarray sum** in linear time. It avoids brute-force by **only tracking the current subarray** and restarting it if the sum becomes disadvantageous (negative).

It’s most famously applied in **Leetcode 53 – Maximum Subarray**.

---

## ✅ When to Use

Use Kadane's when:

- You need to find the **maximum sum of a continuous subarray**
    
- The array contains both negative and positive integers
    
- You want to solve the problem in **O(n)** time
    

---

## 📦 Core Logic

At every index, decide:

> Is it better to **extend the previous subarray**, or **start fresh from here**?

```js
currentSum = Math.max(nums[i], currentSum + nums[i]);
```

Then update the global max:

```js
maxSum = Math.max(maxSum, currentSum);
```

---

## 🔧 Implementation

```js
var maxSubArray = function(nums) {
  let currentSum = nums[0];
  let maxSum = nums[0];

  for (let i = 1; i < nums.length; i++) {
    currentSum = Math.max(nums[i], currentSum + nums[i]);
    maxSum = Math.max(maxSum, currentSum);
  }

  return maxSum;
};
```

---

## 🔍 Optional: Track Start/End Indices

```js
let start = 0, end = 0, tempStart = 0;

for (let i = 1; i < nums.length; i++) {
  if (nums[i] > currentSum + nums[i]) {
    currentSum = nums[i];
    tempStart = i;
  } else {
    currentSum += nums[i];
  }

  if (currentSum > maxSum) {
    maxSum = currentSum;
    start = tempStart;
    end = i;
  }
}

// nums.slice(start, end + 1) is the max subarray
```

---

## ⏱️ Complexity

- **Time:** O(n)
    
- **Space:** O(1)
    

---

## 🔗 Related Problems

- LC 53 – Maximum Subarray
    
- LC 918 – Maximum Sum Circular Subarray
    
- LC 152 – Maximum Product Subarray (variant)
    

---

## 🧠 Key Insight

Kadane’s is a greedy strategy that solves a DP-style problem **without extra space**. It works because **a negative running sum is never helpful** for future elements.