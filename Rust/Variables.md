#### Tips

1. In Rust variables are **immutable** for default, so we call them Variable bindings. To make them mutable, the mut keywork is used.
2. Rist is a statically typed language; It checks data types at compile-time. In that case, the compiler checks the usage and sets a better data type for it. But for **constants and statics, you must annotate the type**. Types come after a colon(`:`).
3. Usually, constants and statics are placed at the top of the code file, outsite the functions (after module imports)
#### Variable bidings

The **`let`** keyword is used in binding expressions. We can bind a name to a value or a function. Also, because the left-hand side of a let expression is a _“pattern”_, you can bind multiple names to a set of values or function values.

The ``const`` keyword is used to define the constant. They live for the entire lifetime of a program but has no fixed address in the memory.

The ``static`` keyword is used to defined a global variable. There is only instance for each value and it's at a fixed location in memory

``💭 While you need constants, always use `const`, instead of `static`. It’s pretty rare that you actually want a memory location associated with your constant, and using a const allows for optimizations like [constant propagation](https://en.wikipedia.org/wiki/Constant_folding#Constant_propagation), not only in your crate but also in downstream crates.
``

### Variable Shadowing

Sometime we need transform a variable value in process. Rust allows us to redeclare the same variable with a diferente data type and/ or with a different mutability setting. This is ``shadowing``
EX:
```rust
fn main() {
	let x: f64 = -20.48; //float
	let x: i64 = x.floor() as i64; //int
	println!("{}", x); // -21

	let s: &str = "hello"; //&str
	let s: String = s.to_uppercase(); // String
	println!("{}", s); // HELLO
}
```

