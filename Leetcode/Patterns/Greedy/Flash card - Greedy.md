
## 🧠 What is a Greedy Algorithm?

A greedy algorithm builds up a solution piece by piece, always choosing the **locally optimal** option at each step, hoping that this leads to a **globally optimal** solution.

Unlike Dynamic Programming, greedy algorithms **do not revisit** past decisions or store full solution states — they make one-shot decisions.

---

## ✅ When to Use

Use greedy algorithms when:

- The problem can be broken down into **independent subproblems**
    
- A **local optimum leads to a global optimum** (this can often be proved with a greedy-choice property)
    
- You want an **efficient solution** with minimal state or memory tracking
    

---

## 🔁 Greedy vs Dynamic Programming

|Feature|Greedy|Dynamic Programming|
|---|---|---|
|Decision|Locally optimal|Explores all possibilities|
|Backtracking|❌ Not used|✅ Sometimes used|
|Memoization|❌ Not used|✅ Often used|
|Efficiency|✅ Fast and simple|🟡 Slower but guarantees optimal solution|

---

## 🔧 Examples of Greedy Algorithms

- **LC 53 – Maximum Subarray**
    
    - Kadane's Algorithm chooses between extending the current subarray or starting fresh.
        
- **LC 122 – Best Time to Buy and Sell Stock II**
    
    - Add all upward slopes to maximize profit.
        
- **LC 134 – Gas Station**
    
    - Choose starting point where cumulative gas is never negative.
        
- **LC 55 – Jump Game**
    
    - Track farthest reachable index.
        

---

## 📌 Key Insight

Greedy works when you can:

- Prove that greedy choices always lead to the optimal result
    
- Avoid comparing all combinations (unlike DP or backtracking)
    

---

## 📚 Related Flashcards

- [[Flashcard - Kadanes Algorithm]]
    

---

## 🧪 Related Problems

- [[1. LC 53. Maximum Subarray]]
    

You can add more problems here as you solve them!