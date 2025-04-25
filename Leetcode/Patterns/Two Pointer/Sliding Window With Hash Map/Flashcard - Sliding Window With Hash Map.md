# 🔍 Pattern: Sliding Window with Hash Map

## 📌 When to Use
Use when you need to:
- Find the longest/shortest subarray or substring that meets a constraint
- Track seen elements dynamically as you move through a sequence
- Handle problems involving **non-repeating elements** or **element frequency** in a window

---

## 🧠 Core Idea

Maintain a **moving window** (`start` to `end`) over the input:

- Use a **Map (or Set)** to track information about the current window (like last seen index)
- If a constraint is violated (e.g., duplicate found), **shrink the window from the left**
- At each step, calculate the current window size: `end - start + 1`
- Keep track of the **maximum or minimum size** as needed

---

## 🔧 Code Example – LeetCode 3: Longest Substring Without Repeating Characters

```js
var lengthOfLongestSubstring = function (s) {
    let map = new Map();     // char -> last seen index
    let max = 0;
    let start = 0;

    for (let end = 0; end < s.length; end++) {
        let char = s[end];

        if (map.has(char) && map.get(char) >= start) {
            start = map.get(char) + 1;
        }

        map.set(char, end);
        max = Math.max(max, end - start + 1);
    }

    return max;
};
```

---

## 🧠 Explanation

- `start` marks the beginning of the current valid window
- `end` iterates through the string
- `map` tracks the **last index** where each character was seen
- If a repeated character is found **within the current window**, `start` jumps past it
- `max` keeps the length of the largest valid window found

---

## 🔢 Example

Input: `"abcabcbb"`

Step-by-step:

| end | char | seen          | start | maxLen | Explanation        |
| --- | ---- | ------------- | ----- | ------ | ------------------ |
| 0   | a    | a:0           | 0     | 1      | new char           |
| 1   | b    | a:0, b:1      | 0     | 2      | new char           |
| 2   | c    | a:0, b:1, c:2 | 0     | 3      | new char           |
| 3   | a    | a:3           | 1     | 3      | repeat → start = 1 |
| 4   | b    | b:4           | 2     | 3      | repeat → start = 2 |
| 5   | c    | c:5           | 3     | 3      | repeat → start = 3 |
| 6   | b    | b:6           | 5     | 3      | repeat → start = 5 |
| 7   | b    | b:7           | 7     | 3      | repeat → start = 7 |

---

## ⏱️ Complexity

- **Time:** O(n) – each character is visited at most twice
- **Space:** O(k) – where `k` is the number of unique characters in the input

---

## 💡 Key Insight

You don't need to build substrings — just track the window **by indices**.  
Update `start` only when a **duplicate within the window** is found.  
The sliding window grows and shrinks as needed, always maintaining the constraint.

---

## 🔗 Related Problems

- Longest Substring with At Most K Distinct Characters
- Minimum Window Substring
- Longest Repeating Character Replacement
- Longest Subarray with Equal Number of 0 and 1