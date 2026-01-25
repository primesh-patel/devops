# 📘 Git Restore Command – Important Notes

---

## 🔹 Git Restore kya hoti hai?
- `git restore` ek **undo / rollback command** hai  
- Iska use tab hota hai jab:
  - aapne galti se changes kar diye ho  
  - ya galti se file stage kar di ho  
- Ye command **working directory** aur **staging area** dono ke saath kaam karti hai

👉 Simple words me:  
**Git Restore = galti se hue changes ko wapas lena**

---

## 🔹 Git Restore kyu important hai?
- `Ctrl + Z`:
  - IDE close hone ke baad kaam nahi karta  
- Git Restore:
  - Git history ke basis par kaam karta hai  
  - reliable & professional way hai changes undo karne ka  

---

## 🔹 Git Restore kis-kis stage par kaam karta hai?
Git Restore ka use ho sakta hai:

1. **Working Directory** (sirf modified file)
2. **Staging Area** (file stage ho chuki ho)
3. ❌ **Committed changes** (yahan restore kaam nahi karta)

---

## 🔹 Scenario 1: Working Directory ke changes undo karna

### Situation:
- File modify ki  
- `git add` nahi kiya  
- Ab last commit par wapas jana hai  

### Command:
```bash
git restore file_name
All files ke liye:
git restore .
📌 Result:

File last committed version par wapas aa jaati hai

🔹 Scenario 2: Galti se file stage ho gayi (Unstage karna)
Situation:
File ko stage area me bhej diya (git add)

Ab commit nahi karna chahte

Command:
git restore --staged file_name
📌 Result:

File staging area se nikal kar

wapas working directory me aa jaati hai

🔹 Working Directory + Staging Area ka flow
Working Directory
        ↓ (git add)
Staging Area
        ↓ (git commit)
Local Repository
git restore:

Working Directory se changes hata sakta hai

Staging Area se files unstage kar sakta hai

🔹 Example Summary
Modified file ko undo:
git restore index.html
Stage ki hui file ko unstage:
git restore --staged app.js
Sab staged files unstage:
git restore --staged .
🔹 git status (best friend command)
Hamesha check karo:

git status
Ye batata hai:

Modified files

Staged files

Untracked files

🔹 Important Limitation ⚠️
Agar aapne:

git commit
kar diya hai

❌ git restore kaam nahi karega

👉 Committed changes ke liye:

alag commands hoti hain

git reset

git revert
(ye topics next videos me cover hote hain)

🔹 Interview ke liye One-Line Summary
git restore ka use:

working directory ke changes undo karne ke liye

staged files ko unstage karne ke liye

Commit ke baad restore kaam nahi karta

🔹 Interview Rapid Fire Q&A ⭐
Q. git restore ka use kab karte hain?
➡ Jab commit se pehle changes undo karne ho

Q. staged file ko kaise unstage karte ho?
➡ git restore --staged file_name

Q. commit ke baad restore chalega?
➡ ❌ No

🔹 One-Line Yaad Rakhne Wala Rule 🧠
Commit se pehle = git restore
Commit ke baad = git reset / git revert

