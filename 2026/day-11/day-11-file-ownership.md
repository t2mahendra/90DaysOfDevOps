
**Day 11 – File Ownership Challenge (chown & chgrp)**

**Task Done**

Task 1: Understanding Ownership 

Run ls -l in your home directory

<img width="507" height="155" alt="image" src="https://github.com/user-attachments/assets/50f8b992-d45a-43f7-8d5d-390c084b3950" />

Identify the owner and group columns
Check who owns your files
Format: -rw-r--r-- 1 owner group size date filename

Task 2: Basic chown Operations 
Create file devops-file.txt
Check current owner: ls -l devops-file.txt
Change owner to tokyo (create user if needed)
Change owner to berlin
Verify the changes

<img width="445" height="160" alt="image" src="https://github.com/user-attachments/assets/4ef20f51-5cf5-4ff3-8ec7-eb964e8dc7dc" />

Task 3: Basic chgrp Operations 
Create file team-notes.txt
Check current group: ls -l team-notes.txt
Create group: sudo groupadd heist-team
Change file group to heist-team
Verify the change

<img width="441" height="150" alt="image" src="https://github.com/user-attachments/assets/73e9e7ab-4230-4623-b9b0-49441400a7c6" />

Task 4: Combined Owner & Group Change 
Using chown you can change both owner and group together:

Create file project-config.yaml
Change owner to professor AND group to heist-team (one command)
Create directory app-logs/
Change its owner to berlin and group to heist-team

<img width="578" height="427" alt="image" src="https://github.com/user-attachments/assets/638a57c3-a63e-44af-841b-9874f60efdad" />

Task 5: Recursive Ownership 
Create directory structure:

mkdir -p heist-project/vault
mkdir -p heist-project/plans
touch heist-project/vault/gold.txt
touch heist-project/plans/strategy.conf
Create group planners: sudo groupadd planners

Change ownership of entire heist-project/ directory:

Owner: professor
Group: planners
Use recursive flag (-R)
Verify all files and subdirectories changed: ls -lR heist-project/

<img width="553" height="336" alt="image" src="https://github.com/user-attachments/assets/fb86d7d5-676f-4c58-b7ed-415eb1a00d85" />

Task 6: Practice Challenge 
Create users: tokyo, berlin, nairobi (if not already created)

Create groups: vault-team, tech-team

Create directory: bank-heist/

Create 3 files inside:

touch bank-heist/access-codes.txt
touch bank-heist/blueprints.pdf
touch bank-heist/escape-plan.txt
Set different ownership:

access-codes.txt → owner: tokyo, group: vault-team
blueprints.pdf → owner: berlin, group: tech-team
escape-plan.txt → owner: nairobi, group: vault-team
Verify: ls -l bank-heist/

<img width="825" height="313" alt="image" src="https://github.com/user-attachments/assets/d4b78943-8c3d-4949-b824-1c50bc88b24e" />

Happy Learning 

Mahendra Singh


