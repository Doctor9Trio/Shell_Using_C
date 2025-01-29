**Description:**  
This project is a basic UNIX shell implementation written in C, designed to handle command execution, process management, and input/output redirection. It demonstrates core operating system concepts such as forking processes, executing commands, and handling signals.

**Features:**  
- **Command Execution:** Run standard commands (e.g., `ls`, `echo`, `gcc`).  
- **Built-in Commands:**  
  - `cd <directory>`: Change the current working directory.  
  - `exit`: Terminate the shell.  
- **Parallel Execution:** Use `&&` to run commands concurrently (e.g., `cmd1 && cmd2`).  
- **Sequential Execution:** Use `##` to run commands one after another (e.g., `cmd1 ## cmd2`).  
- **Output Redirection:** Redirect command output to a file using `>` (e.g., `ls > output.txt`).  
- **Dynamic Prompt:** Displays the current working directory in the prompt (e.g., `/home/user$`).  

**Implementation Details:**  
- **Process Management:** Uses `fork()`, `execvp()`, and `wait()` to execute commands and manage processes.  
- **Input Parsing:** Splits input into tokens using `strtok()` and handles delimiters (`&&`, `##`, `>`).  
- **I/O Redirection:** Achieved via file descriptor manipulation (`dup2()`, `open()`).  
- **Error Handling:** Reports incorrect commands and handles directory changes.  

**How to Compile & Run:**  
1. Compile with:  
   ```bash
   gcc shell.c -o myshell
   ```  
2. Run the shell:  
   ```bash
   ./myshell
   ```  

**Example Usage:**  
- Run sequentially: `sleep 5 ## echo "Done!"`  
- Run in parallel: `sleep 5 && echo "Done!"`  
- Redirect output: `ls > files.txt`  

---

**GitHub README.md Snippet:**  
```markdown
# Simple UNIX Shell in C

A minimal UNIX shell supporting command execution, parallel/sequential processes, and I/O redirection.

## Features
- Execute commands (`ls`, `echo`, etc.)
- Built-in `cd` and `exit`
- Parallel (`&&`) and sequential (`##`) execution
- Output redirection (`>`)
- Dynamic prompt with current directory

## Build & Run
```bash
gcc shell.c -o myshell && ./myshell
```

Explore process management and shell internals with this educational project!
```
