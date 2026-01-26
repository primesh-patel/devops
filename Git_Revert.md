# 📘 Git Revert Command – Important Notes

---

## 🔹 Problem Statement (Context)
- Last video me humne **git restore** dekha tha  
- `git restore` sirf:
  - Working Directory
  - Staging Area  
  tak hi kaam karta hai  

❓ **Question:**  
Agar changes:
- commit ho chuki ho ❓  
- GitHub par push ho chuki ho ❓  

👉 Tab undo kaise karein?

✅ **Answer:** `git revert`

---

## 🔹 Git Revert kya hota hai?
- `git revert` ka use **committed changes ko undo** karne ke liye hota hai  
- Ye:
  - Local repository
  - Remote repository (GitHub)
  dono ke saath safely kaam karta hai  

👉 Simple words me:  
**Git Revert = commit ko undo karna without history delete kiye**

---

## 🔹 Git Restore vs Git Revert (Quick Difference)

| Command | Kab use hoti hai |
|------|----------------|
| `git restore` | Commit se pehle |
| `git revert` | Commit ke baad |
| `git restore` | History change nahi hoti |
| `git revert` | New commit create hota hai |

---

## 🔹 Git Revert ka main concept (Very Important ⭐)
- Jab bhi aap commit karte ho:
  - Git ek **unique hash code** generate karta hai  
- Ye hash:
  - commit message se independent hota hai  
  - hamesha unique hota hai  

👉 Isi **hash code** ke basis par revert hota hai

---

## 🔹 Commit Hash kya hota hai?
- Har commit ki ek **unique identity** hoti hai  
- Ye encrypted / hashed value hoti hai  

Example:
```text
a1b2c3d4e5f6
📌 Isi hash se Git samajhta hai:

kaunsa commit

kaunsa change

🔹 Commit history dekhna (Hash nikalna)
Full history:
git log
Short & clean history:
git log --oneline
Output example:

f3a1c2d second commit
a7b9e8f first commit
🔹 Git Revert ka syntax
git revert <commit-hash>
🔹 Practical Scenario
Situation:
Second commit me galat change ho gaya

Code already commit & push ho chuka hai

Steps:
Commit hash nikalo:

git log --oneline
Galat commit ka hash copy karo

Revert command run karo:

git revert f3a1c2d
🔹 Git Revert ke baad kya hota hai?
Git:

ek NEW commit create karta hai

jo previous commit ke changes ko undo karta hai

📌 Important:

Purani commit delete ❌ nahi hoti

History safe rehti hai ✅

🔹 Vim Editor confusion (Quick Tip)
Revert ke time Vim editor open ho sakta hai

Exit karne ke liye:
ESC
:q
Ya simply commit save hone do

🔹 Git Status check
git status
Agar output clean hai:

matlab revert commit ho chuka hai

🔹 GitHub par kya dikhega?
Pehle: 2 commits

Revert ke baad: 3 commits

Example:

First commit

Second commit (galat)

Revert commit (undo)

👉 History fully preserved 💯

🔹 Git Revert ka biggest advantage ⭐
❌ History delete nahi hoti

✅ Safe for production

✅ Team-friendly

✅ Industry recommended

🔹 Git Reset ka short intro (Next Topic)
git reset bhi commit undo karta hai

BUT:

commit history delete ho sakti hai ❌

Risky command hai

👉 Isliye:

Safe undo = git revert

Dangerous undo = git reset

🔹 Interview ke liye One-Line Summary
Git Revert committed changes ko undo karta hai
without deleting commit history

🔹 Interview Rapid Fire Q&A ⭐
Q. Commit ke baad undo kaise karte ho?
➡ git revert

Q. Git revert history delete karta hai?
➡ ❌ No

Q. Git revert kya create karta hai?
➡ Ek new commit

Q. Production me kaunsi command safe hai?
➡ git revert

🔹 Golden Rule 🧠
Before commit  → git restore
After commit   → git revert
