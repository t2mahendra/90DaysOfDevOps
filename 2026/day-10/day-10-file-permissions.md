
**Day 10 – File Permissions & File Operations Challenge**

**Task Done**

Challenge Tasks

Task 1: Create Files (10 minutes)

Create empty file devops.txt using touch

<img width="546" height="392" alt="image" src="https://github.com/user-attachments/assets/ced95550-9aec-428f-b7f0-38ff3019dadc" />

Create notes.txt with some content using cat or echo

<img width="288" height="29" alt="image" src="https://github.com/user-attachments/assets/0c1740bc-0a21-4446-84d5-09f7eb84d1b6" />

Create script.sh using vim with content: echo "Hello DevOps"

<img width="276" height="34" alt="image" src="https://github.com/user-attachments/assets/dbd286d9-505b-4358-addf-3d8d9b0122a4" />

<img width="213" height="329" alt="image" src="https://github.com/user-attachments/assets/808a9ee2-5735-4085-869c-cb556712013d" />

Verify: ls -l to see permissions

<img width="531" height="215" alt="image" src="https://github.com/user-attachments/assets/88e8f26d-6aac-4c79-b1db-2da529c2c095" />

Task 2: Read Files (10 minutes)

Read notes.txt using cat

<img width="277" height="34" alt="image" src="https://github.com/user-attachments/assets/1524aee3-25b0-4f6e-884c-059a07a29205" />

View script.sh in vim read-only mode

<img width="277" height="46" alt="image" src="https://github.com/user-attachments/assets/7c7e2766-ef23-4c62-9a7b-f257c6ae3a88" />

Display first 5 lines of /etc/passwd using head

<img width="407" height="191" alt="image" src="https://github.com/user-attachments/assets/c26dabc2-078a-4492-a5e5-3cde95f7d6ac" />

Display last 5 lines of /etc/passwd using tail

<img width="545" height="188" alt="image" src="https://github.com/user-attachments/assets/8c3a6b0c-4cca-4d03-af78-2a459bf1804a" />

Task 3: Understand Permissions (10 minutes)
Format: rwxrwxrwx (owner-group-others)

r = read (4), w = write (2), x = execute (1)
Check your files: ls -l devops.txt notes.txt script.sh

<img width="468" height="78" alt="image" src="https://github.com/user-attachments/assets/5524d5fb-4cf0-4f37-bf03-c8493ee5a14c" />

Answer: Read/write current permissions.

