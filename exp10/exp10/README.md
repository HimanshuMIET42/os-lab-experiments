# Linux Process Management using C

## Overview

This project demonstrates basic process management concepts in Linux using the C programming language. It consists of three programs that demonstrate process identification, process creation, parent-child synchronization, and process termination.

The programs use Linux system calls to understand how the operating system manages processes.

## Programs Included

### 1. exp10.c – Display Current Process ID

This program displays the Process ID (PID) of the currently executing process.

**System calls used:**
- `getpid()` – Returns the PID of the current process.

### 2. exp10a.c – Process Creation and Synchronization

This program creates a child process using `fork()` and demonstrates how the parent process waits for the child to finish using `wait()`.

**System calls used:**
- `fork()` – Creates a child process.
- `wait()` – Waits for the child process to terminate.
- `exit()` – Terminates the child process.

### 3. exp10b.c – Parent and Child Process Termination

This program demonstrates the execution of parent and child processes. The child displays its PID, executes its instructions, and terminates. Meanwhile, the parent waits for the child to complete its execution.

**System calls used:**
- `fork()` – Creates a child process.
- `getpid()` – Retrieves the current process ID.
- `sleep()` – Suspends execution for a specified duration (zero seconds in this program).
- `wait()` – Makes the parent wait for child termination.
- `exit()` – Terminates the child process.

## Technologies Used

- **Programming Language:** C
- **Operating System:** Linux (Ubuntu)
- **Text Editor:** GNU Nano
- **Compiler:** GCC

## How to Compile and Run

### Step 1: Open the Linux Terminal

Navigate to the directory containing the C files.

### Step 2: Compile the Programs

Compile the first program:

```bash
gcc exp10.c -o exp10
```

Compile the second program:

```bash
gcc exp10a.c -o exp10a
```

Compile the third program:

```bash
gcc exp10b.c -o exp10b
```

### Step 3: Execute the Programs

Run the first program:

```bash
./exp10
```

Run the second program:

```bash
./exp10a
```

Run the third program:

```bash
./exp10b
```

## Expected Learning Outcomes

After completing these programs, we understand:

1. How to retrieve the PID of a process.
2. How to create a child process using `fork()`.
3. How parent and child processes execute.
4. How to synchronize processes using `wait()`.
5. How to terminate a process using `exit()`.
6. How Linux handles child process termination and reaping.

## Conclusion

This project provides practical knowledge of Linux process management. It demonstrates the use of important system calls and explains how parent and child processes interact during execution.

These concepts form the foundation of process management in operating systems.
