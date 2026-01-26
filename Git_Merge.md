````md
# 📘 Git Branches – Complete & Detailed Notes (Beginner to Practical)

---

## 🔹 Git Branch kya hoti hai?
- **Branch** ka matlab hota hai:
  - Project ke code ki **copy**
  - Jisme aap freely experiments / changes kar sakte ho  
  - bina **original (main) code** ko affect kiye

👉 Simple words me:  
**Branch = Project ki alag copy jahan safely kaam hota hai**

---

## 🔹 Branch ka concept itna important kyu hai?
- Team work me:
  - Multiple log ek hi project par kaam karte hain
- Feature development me:
  - Naya feature try karna hota hai
- Testing me:
  - Risky changes ko safe jagah test karna hota hai

👉 Isliye **Git ka sabse powerful concept = Branches**

---

## 🔹 Default Branch
- Local Git:
  - pehle `master`
- GitHub:
  - `main`

👉 Best practice:
```bash
git branch -M main
````

---

## 🔹 Branch ka Real-Life Example (Manager wala)

* Manager ke paas:

  * Final project → **main branch**
* Team members:

  * apni-apni branch me kaam karte hain
* Best kaam:

  * main branch me **merge**
* Baaki branches:

  * **delete**

👉 Fayda:

* Original code safe
* No conflicts
* Easy comparison

---

## 🔹 Branch ka Technical Concept

* Jab aap branch banate ho:

  * Git **code ki copy** bana deta hai
* Har branch:

  * apna alag history
  * apni commits
* Ek branch ka change:

  * dusri branch ko affect nahi karta

---

# 🔹 Initial Setup (Common Steps)

```bash
git init
git add .
git commit -m "first commit in main"
git branch -M main
git remote add origin <repo_url>
git push -u origin main
```

---

## 🔹 Branch list kaise dekhein?

```bash
git branch
```

👉 Output:

* `*` wali branch = current branch

---

# 🔹 New Branch banana

## 🔹 Method 1: Sirf branch create karna

```bash
git branch second
```

👉 Branch ban jayegi
👉 Switch nahi hogi

---

## 🔹 Method 2: Branch me switch karna (checkout)

```bash
git checkout second
```

---

## 🔹 Method 3: Modern way (recommended)

```bash
git switch second
```

👉 Beginner-friendly
👉 Sirf branch switching ke liye

---

# 🔹 Branch create + switch (Single command)

## 🔹 Old way (checkout)

```bash
git checkout -b third
```

## 🔹 New way (switch)

```bash
git switch -c fourth
```

👉 Dono ka matlab:

* Agar branch exist nahi karti:

  * create bhi hogi
  * switch bhi ho jaoge

---

## 🔹 Checkout vs Switch

| Command  | Purpose               |
| -------- | --------------------- |
| checkout | multiple purposes     |
| switch   | sirf branch switching |

👉 Modern Git me:

* **switch preferred**

---

# 🔹 Branch me kaam karna

### Example:

* `second` branch me:

  * new file
  * changes
  * commits

```bash
git add .
git commit -m "work done in second branch"
```

👉 Ye changes **sirf second branch** me rahenge

---

## 🔹 Branch switch karne par kya hota hai?

* Branch change = working directory change
* Files:

  * appear / disappear according to branch

👉 Proof:

* second branch → file visible
* main branch → file invisible

---

# 🔹 Branch delete kaise karein?

## 🔹 Safe delete

```bash
git branch -d second
```

👉 Tabhi delete hogi:

* jab branch merge ho chuki ho

---

## 🔹 Force delete (dangerous)

```bash
git branch -D second
```

👉 Commit history delete ho jati hai

---

⚠️ Rule:

* Current branch delete **nahi hoti**
* Pehle switch karo:

```bash
git switch main
```

---

# 🔹 Branch GitHub par push karna

```bash
git push -u origin second
```

👉 Ab branch GitHub par visible hogi

---

# 🔹 GitHub par branches

* Multiple branches dikhengi
* Har branch ka:

  * code
  * commits
  * history

---

# 🔹 Branch merge ka concept

* Branch me kaam complete ho gaya
* Approval mil gaya
* Ab changes ko **main** me lana hai

👉 Is process ko kehte hain:
**Merge**

---

## 🔹 Branch merge kaise karein?

### Step 1: Main branch me aao

```bash
git switch main
```

### Step 2: Merge command

```bash
git merge second
```

👉 second branch ke changes:

* main branch me aa jayenge

---

## 🔹 Merge ke baad push

```bash
git push origin main
```

---

## 🔹 Merge ke baad kya hota hai?

* Code combine ho jata hai
* History preserved rehti hai
* GitHub par updated code dikhta hai

---

# 🔹 Branch delete (after merge)

```bash
git branch -d second
```

👉 Clean repository
👉 Best practice

---

# 🔹 Team Workflow (Standard)

1. main branch = stable code
2. Feature branch create
3. Work + commit
4. Push to GitHub
5. Review
6. Merge to main
7. Delete feature branch

---

# 🔹 Important Commands – Quick List

```bash
git branch                 # list branches
git branch <name>          # create branch
git switch <name>          # switch branch
git checkout <name>        # old switch method
git switch -c <name>       # create + switch
git checkout -b <name>     # create + switch (old)
git branch -d <name>       # delete branch
git merge <branch>         # merge branch
git push origin <branch>  # push branch
```

---

# 🔹 Interview One-Line Summary ⭐

> **Branch Git ka feature hai jo code ki copy banakar
> safe development aur team collaboration allow karta hai**

---

# 🔹 Interview Q&A 🔥

**Q. Branch kya hoti hai?**
➡ Code ki copy jisme safe changes hote hain

**Q. Branch ka main use?**
➡ Team work & feature development

**Q. Checkout vs Switch?**
➡ Switch branch-specific & beginner friendly

**Q. Merge kya karta hai?**
➡ Branch changes ko main me add karta hai

---

# 🔹 Golden Rules 🧠

* Main branch hamesha stable rakho
* Har feature ke liye new branch
* Merge ke baad branch delete
* Team me `reset` avoid karo

---

## ✅ Final Summary

* Branch = Copy of project
* Changes isolated
* Safe testing
* Easy merge
* Best for teamwork

---
