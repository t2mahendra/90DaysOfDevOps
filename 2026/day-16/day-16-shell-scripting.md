
# Shell Scripting Basics

## Task Done
Start your shell scripting journey — learn the fundamentals every script needs.

You will:
- Understand **shebang** (`#!/bin/bash`) and why it matters
- Work with **variables**, **echo**, and **read**
- Write basic **if-else** conditions

---

## Challenge Tasks

### Task 1: Your First Script
1. Create a file `hello.sh`
2. Add the shebang line `#!/bin/bash` at the top
3. Print `Hello, DevOps!` using `echo`
4. Make it executable and run it

```bash
chmod +x hello.sh
./hello.sh
```

<img width="464" height="258" alt="image" src="https://github.com/user-attachments/assets/e379ce05-cb01-4cb4-b1cd-a3458526831a" />

---

### Task 2: Variables
1. Create `variables.sh` with:
   - A variable for your `NAME`
   - A variable for your `ROLE` (e.g., "DevOps Engineer")
   - Print: `Hello, I am <NAME> and I am a <ROLE>`
2. Try using single quotes vs double quotes — what's the difference?

<img width="419" height="156" alt="image" src="https://github.com/user-attachments/assets/e1621129-d0cc-4e90-a118-25190b59d50e" />

---

### Task 3: User Input with read
1. Create `greet.sh` that:
   - Asks the user for their name using `read`
   - Asks for their favourite tool
   - Prints: `Hello <name>, your favourite tool is <tool>`

<img width="417" height="291" alt="image" src="https://github.com/user-attachments/assets/e68becd1-fbdd-440f-874d-346ba1058ef5" />


---

### Task 4: If-Else Conditions
1. Create `check_number.sh` that:
   - Takes a number using `read`
   - Prints whether it is **positive**, **negative**, or **zero**

2. Create `file_check.sh` that:
   - Asks for a filename
   - Checks if the file **exists** using `-f`
   - Prints appropriate message

<img width="386" height="376" alt="image" src="https://github.com/user-attachments/assets/3356c58e-3ebc-4bd7-b848-4e695ad692ff" />


---

### Task 5: Combine It All
Create `server_check.sh` that:
1. Stores a service name in a variable (e.g., `nginx`, `sshd`)
2. Asks the user: "Do you want to check the status? (y/n)"
3. If `y` — runs `systemctl status <service>` and prints whether it's **active** or **not**
4. If `n` — prints "Skipped."
sudo

<img width="667" height="675" alt="image" src="https://github.com/user-attachments/assets/0d5e8720-4f6d-4b8a-8ee2-f15fb72aeb82" />

---


Happy Learning!
**Mahendra Singh**
