# 📘 Git & GitHub Workflow – Important Notes

---

## 🔹 Git kyu important hai?
- Git **Version Control System** hai  
- Developer / Engineer ke liye **must-know skill**  
- Interviews me Git, GitHub & workflow se related questions common hote hain  

---

## 🔹 Repository (Repo) kya hoti hai?
- Repository ek **storage location** hoti hai  
- Yahan par:
  - Code store hota hai  
  - Code ki **history** maintain hoti hai:
    - kis file me  
    - kis time  
    - kis line me  
    - kya change hua  

### ➤ Repository ke 2 types:
- **Local Repository**
- **Remote Repository**

---

## 🔹 Working Directory kya hoti hai?
- System ka wo folder jahan:
  - hum code likhte hain  
  - files create / modify karte hain  
- Jab tak Git initialize nahi hota:
  - koi bhi change **track nahi hota**

👉 **Simple words me:**  
`Code likhne ki jagah = Working Directory`

---

## 🔹 Git initialize (`git init`)
- `git init` command:
  - project me Git ko activate karti hai  
  - `.git` folder create hota hai (hidden)  
- Iske baad hi Git files ko track kar sakta hai  

---

## 🔹 Local Repository kya hoti hai?
- Repository ka wo version jo:
  - **aapke computer** me hota hai  

### Kaam:
- code ki history maintain karna  
- commits store karna  
- versions dekhna  

👉 `git init` se **Local Repo** banti hai  

---

## 🔹 Remote Repository kya hoti hai?
- Online repository hoti hai  
- Hosting platforms par banti hai:
  - GitHub  
  - GitLab etc.  

### Use:
- Code share karna  
- Collaboration  
- Backup  

👉 Isse **Global Repository** bhi bol sakte hain  

---

## 🔹 Git Workflow (Most Important ⭐)

Working Directory
↓
Staging Area
↓
Local Repository
↓
Remote Repository


---

## 🔹 Staging Area kya hota hai?
- Working Directory aur Local Repo ke beech ka **temporary area**  
- Yahan par changes temporarily store hote hain  

### 👉 Command:
```bash
git add file_name
git add .
🔹 git add
Working Directory se changes ko

Staging Area me bhejta hai

git add .
➡ sab files (new + modified) stage ho jaati hain

🔹 git commit
Staging Area ke changes ko:

finalize karta hai

Local Repository me save karta hai

👉 Command:
git commit -m "meaningful message"
📌 Commit message ka role:
Documentation jaisa kaam karta hai

Batata hai kya change hua aur kyu

🔹 Branch rename (master → main)
Local Git default branch = master

GitHub default branch = main

👉 Rename command:
git branch -M main
🔹 Remote repository connect karna
Local repo ko batana hota hai:

code kahan push karna hai

👉 Command:
git remote add origin <repo_url>
🔹 git push
Local Repository se code

Remote Repository me bhejta hai

First time:
git push -u origin main
-u flag ka fayda:
Future me sirf:

git push
kaam karega

🔹 Modified vs Untracked files
Modified file:
pehle se tracked thi

code change hua

Untracked file:
nayi file

Git ko abhi nahi pata

👉 git add . dono ko stage kar deta hai

🔹 Multiple changes ka flow
File modify / new file add

git add .

git commit -m "changes done"

git push

🔹 GitHub par kya dikhai deta hai?
Files

Commit messages

Changes ka exact comparison (diff)

History (version control)

🔹 Interview ke liye One-Line Summary
Working Directory → jahan code likhte ho

Staging Area → temporary selection area

Local Repo → system me version control

Remote Repo → GitHub par hosted code

git add → stage

git commit → save locally

git push → upload to GitHub
