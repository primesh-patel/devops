# 📘 Git Reset Command – Important Notes

---

## 🔹 Context (Previous Video Recap)
- Last video me humne **git revert** command dekhi thi  
- `git revert`:
  - committed changes ko undo karti hai  
  - **commit history delete nahi karti**  

❓ Ab sawal:
> Agar main commit ko **permanently hataana** chahta hoon to?

👉 **Answer:** `git reset`

---

## 🔹 Git Reset kya hoti hai?
- `git reset` ek **powerful & dangerous** command hai  
- Ye:
  - commit ko undo karti hai  
  - aur **commit history se permanently remove** kar deti hai  

👉 Simple words me:  
**Git Reset = commit + history ko peeche le jaana**

---

## 🔹 Git Revert vs Git Reset (Very Important ⭐)

| Feature | git revert | git reset |
|------|-----------|-----------|
| Commit undo | ✅ Yes | ✅ Yes |
| New commit create | ✅ Yes | ❌ No |
| History delete | ❌ No | ✅ Yes |
| Team safe | ✅ Yes | ❌ No |
| Production safe | ✅ Yes | ❌ No |

📌 **Rule:**  
- Team / Production → `git revert`  
- Solo / Experimental → `git reset`

---

## 🔹 Git Reset ka core concept
- Git har commit ko ek **unique hash code** deta hai  
- Reset:
  - HEAD pointer ko peeche move karta hai  
  - aur commits ko history se hata deta hai  

---

## 🔹 Commit history dekhna
```bash
git log --oneline
Example:

c3d9a12 third commit
a7b9e8f second commit
f1a2b3c first commit
👉 HEAD = latest commit

🔹 Git Reset ke 3 modes (Most Important ⭐⭐⭐)
1️⃣ Soft Reset (--soft)
git reset --soft HEAD~1
Kya karta hai?
✅ Commit undo

✅ Changes staging area me rehte hain

❌ Working directory safe

Use case:
Commit message galat likh diya

Code sahi hai

👉 Re-commit with correct message

2️⃣ Mixed Reset (Default)
git reset HEAD~1
OR

git reset --mixed HEAD~1
Kya karta hai?
✅ Commit undo

✅ Changes unstaged ho jaate hain

❌ Working directory safe

Use case:
Commit + staging dono undo chahiye

📌 Agar koi flag na do → by default mixed

3️⃣ Hard Reset (⚠️ Dangerous)
git reset --hard HEAD~1
Kya karta hai?
✅ Commit undo

✅ Staging area clean

❌ Working directory se bhi changes delete

🚨 Permanent deletion

Wapas lana almost impossible

Use case:
Project ko bilkul zero se start karna ho

🔹 HEAD~1 ka matlab
HEAD = current commit

HEAD~1 = ek commit peeche

HEAD~2 = do commit peeche

🔹 Specific commit tak reset karna
git reset --soft <commit-hash>
git reset --mixed <commit-hash>
git reset --hard <commit-hash>
🔹 Practical Observation
git reset ke baad:

git log --oneline
➡ Removed commit history se gayab ho jaata hai

📌 Ye revert se sabse bada difference hai

🔹 Team Work me Git Reset ❌
Team collaboration me:

kabhi bhi git reset use nahi karte

Kyunki:

commit history sabke liye change ho jaati hai

conflicts + confusion create hota hai

👉 Best practice:

Team project → git revert
Solo project → git reset
🔹 Interview ke liye One-Line Summary
Git Reset committed changes ko undo karta hai
aur commit history se permanently delete kar deta hai

🔹 Interview Rapid Fire Q&A ⭐
Q. Git reset dangerous kyu hai?
➡ Kyunki ye commit history delete kar deta hai

Q. Default git reset mode kaunsa hai?
➡ --mixed

Q. Commit message change karna ho to?
➡ git reset --soft HEAD~1

Q. Production me kaunsa use karein?
➡ ❌ Git Reset
➡ ✅ Git Revert

🔹 Golden Rules 🧠
Before commit      → git restore
After commit safe → git revert
After commit risky→ git reset
🔹 Final Advice ⭐
Jab tak 100% sure na ho
tab tak git reset --hard use mat karo
