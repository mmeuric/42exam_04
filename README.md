# **microshell – 42 Exam Rank 04**

A minimal shell implementation written in C as part of **42’s Exam Rank 04**.
The goal is to reproduce a very small subset of Bash by handling command execution, pipes, semicolons, and the built-in `cd`.
This project tests process management, file descriptors, error handling, and the fundamentals of shell design — all under strict constraints.

---

## 🚀 **Exam Overview**

`microshell` executes commands directly from its program arguments:

* Supports **pipes** (`|`) to chain commands
* Supports **command separators** (`;`)
* Implements the **cd** built-in (with strict error messages)
* Executes commands using **absolute or relative paths only**
* Manages processes using fork, execve, dup2, and pipe
* Handles dozens/hundreds of pipes despite limited file descriptors
* Respects all required error messages and exact output/behavior

No PATH lookup, no wildcards, no environment variable expansion — extremely bare-bones by design.

---


## 📌 **What’s Implemented**

* ✔️ Parsing of arguments into commands
* ✔️ Multiple pipes in a row (`cmd1 | cmd2 | cmd3 | ...`)
* ✔️ Semicolons to separate sequences
* ✔️ Built-in `cd path`
* ✔️ Error handling identical to the subject:

  * `error: cd: bad arguments`
  * `error: cd: cannot change directory to <path>`
  * `error: cannot execute <binary>`
  * `error: fatal`
* ✔️ No leaks of file descriptors
* ✔️ Proper handling of environment variables passed to `execve`

---

## 🧠 **What This Exam Demonstrates**

* Think clearly under time pressure
* Linux process creation & synchronization
* Pipe chaining and redirection logic
* Manual command parsing under strict constraints
* Error-safe file descriptor handling
* How shells fundamentally work internally
