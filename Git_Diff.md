```md
# 📘 Git Diff Command – Explained Notes (Hinglish)

> Ye notes **lecture ko explain karte huye**, step-by-step likhe gaye hain  
> Topic: **git diff**  
> Focus: Practical + real-world understanding

---

## 🔹 Git Diff Command ka Purpose

`git diff` ka use **changes compare karne** ke liye hota hai.

Simple words me:
> **“Kya change hua hai, kahan change hua hai, aur kis level par change hua hai?”**

### Git Diff ka use hota hai:
- Working Directory ke changes dekhne ke liye
- Staging Area ke changes dekhne ke liye
- Do commits ke beech ka difference dekhne ke liye
- Local vs Remote repository ka difference dekhne ke liye
- Sirf file names ya exact words ka difference dekhne ke liye

---

## 🔹 Diff ka Matlab
- **Diff = Difference**
- Git diff batata hai:
  - Kya add hua
  - Kya remove hua
  - Kya modify hua

---

## 🔹 Initial Setup (Lecture Flow)

### Step 1: Remote Repository
- Ek remote repository banayi:
```

git-diff-command

```

### Step 2: Working Directory
- Local folder banaya:
```

git-diff

````

---

## 🔹 Git Initialize Karna

```bash
git init
````

👉 Ab:

* Git tracking start ho gayi
* Abhi tak koi commit nahi hua

---

## 🔹 File Tracking Samajhna

* File present hai
* Git abhi track nahi kar raha
* Is stage par **git diff kuch nahi dikhata**

Reason:

> Diff hamesha **do states ke beech** hota hai
> Abhi compare karne ke liye kuch hai hi nahi

---

## 🔹 Changes ko Stage Karna

```bash
git add .
```

👉 Ab:

* Changes **Staging Area** me chale gaye
* Git unhe track kar raha hai

### Ab bhi:

```bash
git diff
```

❌ Output nahi milega

Reason:

* Abhi tak **commit nahi hua**
* Diff compare karta hai:

  * working directory vs last commit
  * par last commit exist hi nahi karta

---

## 🔹 First Commit Karna

```bash
git commit -m "First commit"
```

👉 Ab:

* Ek reference point ban gaya
* Git ke paas compare karne ke liye base aa gaya

---

## 🔹 Remote Setup (Short Summary)

```bash
git branch -m main
git remote add origin <repo-url>
git push -u origin main
```

👉 Ab:

* Local
* Remote
* Dono same state me hain

---

## 🔹 No Difference Case

```bash
git diff
```

❌ Output nahi

Reason:

* Working Directory
* Local Repository
* Remote Repository
  ➡️ sab same hain

---

## 🔹 Real Diff Example (Working Directory)

### File me change:

```html
<h3>Git and GitHub</h3>
```

### Save file

### Ab run:

```bash
git diff
```

### Output samajhna:

* `+` → New line added
* `-` → Line removed

👉 Matlab:

> **Working directory me change hua hai, par abhi stage nahi hua**

---

## 🔹 Git Diff (Working Directory vs Last Commit)

```bash
git diff
```

✔️ Batata hai:

* Sirf **unstaged changes**
* Jo `git add` nahi hue

---

## 🔹 Git Diff (Staging Area ke liye)

### Changes stage karo:

```bash
git add .
```

### Ab check karo:

```bash
git diff
```

❌ Kuch nahi

### Correct command:

```bash
git diff --staged
```

✔️ Batata hai:

* Staging area me kya changes hain
* Jo commit hone wale hain

---

## 🔹 Summary till Now

| Command             | Kya Compare karta hai            |
| ------------------- | -------------------------------- |
| `git diff`          | Working directory vs Last commit |
| `git diff --staged` | Staging area vs Last commit      |

---

## 🔹 Second Commit

```bash
git commit -m "Second commit"
```

👉 Ab:

* Changes local repo me permanently store ho gaye
* Remote par abhi push nahi hue

---

## 🔹 Local vs Remote Difference

### Command:

```bash
git diff origin/main
```

✔️ Batata hai:

* Local repo me kya extra hai
* Jo remote me abhi nahi gaya

Use case:

> Push karne se pehle verify karna

---

## 🔹 Push ke Baad

```bash
git push
```

👉 Ab:

* Local aur Remote same state me

```bash
git diff origin/main
```

❌ No output

---

## 🔹 Two Commits ke Beech Difference

### Commits dekhna:

```bash
git log --oneline
```

Example:

```
a1b2c3d Second commit
x9y8z7w First commit
```

### Difference check:

```bash
git diff x9y8z7w a1b2c3d
```

✔️ Batata hai:

* In dono commits ke beech kya change hua

---

## 🔹 Sirf File Names Dekhna

```bash
git diff --name-only
```

✔️ Output:

```
index.html
```

Use case:

* Large projects
* Jaldi se dekhna: kaun-si files change hui

---

## 🔹 Exact Word-level Difference (Best Visual)

```bash
git diff --color-words
```

✔️ Fayda:

* Sirf **actual word changes** dikhata hai
* Extra space, spelling, minor changes clear dikhte hain

Example:

* `GitHub` → `Git Hub`
* Space add/remove

---

## 🔹 Real World Use Cases

### Jab `git diff` zaroori hota hai:

* Commit se pehle review
* Team work me conflicts avoid karne ke liye
* Push se pehle sanity check
* Interview me explanation ke liye

---

## 🔹 Interview One-Liners 🎯

* `git diff` working directory ke changes dikhata hai
* `git diff --staged` staged changes dikhata hai
* `git diff commit1 commit2` commits compare karta hai
* `git diff origin/main` local vs remote compare karta hai

---

## 🔹 Common Mistakes ⚠️

❌ Expecting diff without commit
❌ Confusing staged vs unstaged
❌ Push ke baad diff expect karna

---

## 🔹 Final Lecture Conclusion

> **“Git diff ek inspection tool hai jo batata hai ki actual change kya hua hai, commit se pehle aur baad dono situations me.”**

---
