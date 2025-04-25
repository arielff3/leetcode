## 🧠 What is the Stack Pattern?

The stack pattern is used when solving problems that require:

- **Tracking state in a last-in, first-out (LIFO) order**
    
- **Matching opening and closing elements** (like brackets or tags)
    
- **Backtracking or rollback behavior**
    
- **Simulating recursion or nested structures**
    

---

## ✅ When to Use

Use stack when:

- You need to match or validate pairs (e.g., parentheses)
    
- The problem involves **nesting or layering**
    
- You need to remember the **last item** to act upon it later
    

---

## 🔧 Typical Operations

```js
stack.push(item);    // Add to top
stack.pop();         // Remove from top
stack[stack.length - 1]; // Peek at top
```

---

## 🔁 Common Applications

- Validating balanced parentheses or HTML/XML tags
    
- Converting or evaluating expressions (e.g. postfix notation)
    
- Simulating recursion (DFS, backtracking)
    
- Parsing strings or maintaining scopes (loops, calls, etc.)
    

---

## 🔗 Related Problems

- [[1. LC 20. Valid Parentheses]]
    
- LC 150 – Evaluate Reverse Polish Notation
    
- LC 155 – Min Stack
    
- LC 394 – Decode String
    
- LC 844 – Backspace String Compare