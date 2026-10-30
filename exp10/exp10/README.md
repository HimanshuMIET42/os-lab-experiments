# Experiment 10: Process Management in Linux Using C

## 📌 Project Overview

This experiment demonstrates the fundamental concepts of **Process Management in Linux** using the C programming language. It focuses on understanding how processes are created, identified, executed, synchronized, and terminated in a Linux operating system.

The experiment consists of three C programs that use Linux system calls such as `getpid()`, `fork()`, `wait()`, `sleep()`, and `exit()` to demonstrate process management operations.

## 🎯 Objectives

- To understand the concept of processes in Linux.
- To retrieve the Process ID (PID) of a running process.
- To create child processes using the `fork()` system call.
- To understand the relationship between parent and child processes.
- To implement process synchronization using `wait()`.
- To understand process termination and child process reaping.

## 🛠️ Technologies and Tools Used

| Component | Technology |
|---|---|
| Programming Language | C |
| Operating System | Ubuntu Linux |
| Compiler | GCC |
| Text Editor | GNU Nano |
| Environment | Linux Terminal / VirtualBox |

## 📂 Project Structure

```text
Experiment-10/
│
├── exp10.c
├── exp10a.c
├── exp10b.c
└── README.md
```

## 💻 Programs Description

### Program 1: Display Current Process ID (`exp10.c`)

**Objective:** To display the Process ID (PID) of the currently executing process.

**Concept Used:**
- `getpid()` – Returns the unique Process ID of the currently running process.
- `printf()` – Displays the process ID on the terminal.

**Working:**

1. The program starts execution through the `main()` function.
2. The `getpid()` system call retrieves the current process ID.
3. The PID is displayed using `printf()`.
4. The program terminates by returning 0.

**Expected Output:**

```text
Current PID: 1234
```

*Note: The PID will vary each time the program runs.*

---

### Program 2: Parent-Child Process Synchronization (`exp10a.c`)

**Objective:** To create a child process and demonstrate synchronization between parent and child processes.

**Concept Used:**
- `fork()` – Creates a new child process.
- `wait()` – Makes the parent process wait for its child to terminate.
- `exit()` – Terminates the child process.

**Working:**

1. The `fork()` system call creates a child process.
2. If `fork()` returns 0, the child process executes.
3. The child displays the message "Child working..." and terminates using `exit(0)`.
4. The parent process executes the `wait(NULL)` system call.
5. The parent waits until the child process terminates.
6. The child's PID is returned by `wait()` and displayed by the parent.

**Expected Output:**

```text
Child working...
Child 1235 reaped successfully!
```

*Note: The PID will vary depending on the system.*

---

### Program 3: Parent Waiting for Child Termination (`exp10b.c`)

**Objective:** To demonstrate process creation, execution, and termination using Linux system calls.

**Concept Used:**
- `fork()` – Creates a child process.
- `getpid()` – Retrieves the current process ID.
- `sleep()` – Suspends process execution for a specified duration.
- `wait()` – Makes the parent wait for child termination.
- `exit()` – Terminates the child process.

**Working:**

1. The `fork()` system call creates a child process.
2. The child process identifies itself using `getpid()`.
3. The child displays its PID.
4. The `sleep(0)` statement executes without introducing any delay.
5. The child displays an exit message and terminates using `exit(0)`.
6. Meanwhile, the parent displays a waiting message.
7. The parent calls `wait(NULL)` and waits for the child to terminate.
8. After termination, the parent displays the PID of the terminated child.

**Expected Output (illustrative):**

```text
Parent Waiting for child to terminate...
Child Running with PID: 1236
Child Exiting...
Parent Terminated Child PID: 1236
```

*Note: The execution order of parent and child output may vary because both processes execute independently.*

## 📖 Important System Calls Explained

| System Call | Description |
|---|---|
| `getpid()` | Returns the PID of the current process. |
| `fork()` | Creates a new child process. |
| `wait()` | Waits for a child process to terminate. |
| `sleep()` | Suspends execution for a specified number of seconds. |
| `exit()` | Terminates the calling process. |

## ⚙️ Compilation and Execution

### Prerequisites

Make sure GCC is installed on your Linux system.

To install GCC, execute:

```bash
sudo apt update
sudo apt install gcc
```

### Step 1: Navigate to the Project Directory

```bash
cd Experiment-10
```

### Step 2: Compile the Programs

**Program 1:**

```bash
gcc exp10.c -o exp10
```

**Program 2:**

```bash
gcc exp10a.c -o exp10a
```

**Program 3:**

```bash
gcc exp10b.c -o exp10b
```

### Step 3: Execute the Programs

**Run Program 1:**

```bash
./exp10
```

**Run Program 2:**

```bash
./exp10a
```

**Run Program 3:**

```bash
./exp10b
```

## 📚 Key Learning Outcomes

After completing this experiment, the following concepts are understood:

1. Process identification using Process IDs.
2. Process creation using the `fork()` system call.
3. Execution of parent and child processes.
4. Process synchronization using `wait()`.
5. Child process termination using `exit()`.
6. Reaping of terminated child processes by their parent.
7. Basic understanding of Linux process management.

## ✅ Conclusion

This experiment provides practical knowledge of process management in Linux using the C programming language. Through the three programs, we explored process identification, process creation, parent-child relationships, synchronization, and termination.

The experiment helped develop a better understanding of how Linux handles multiple processes and manages their execution using system calls.

---

**Experiment:** 10  
**Subject:** Operating Systems  
**Platform:** Ubuntu Linux  
**Language:** C
