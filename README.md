# Undefined Behavior with Raw Pointers and Vectors in Rust

This repository demonstrates a common mistake when working with raw pointers and vectors in Rust: modifying memory after the vector has gone out of scope.

The `bug.rs` file shows the problematic code. The `bugSolution.rs` file shows a corrected version using safe Rust techniques.

## Problem

The original code obtains a mutable raw pointer to the vector's data.  After the vector goes out of scope, it's deallocated. If you still access that memory pointed to by the raw pointer, you get undefined behavior, which could lead to crashes or seemingly random errors. This is a key reason why Rust emphasizes safe memory management.

## Solution

The solution demonstrates using safe methods for modifying the vector content. Instead of raw pointers, it directly utilizes the vector's indexing capability. This ensures the vector's memory is properly managed by Rust’s ownership system.