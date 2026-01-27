````md
# 📘 GitHub Pages – Static Website Deployment (Explained Lecture Notes)

> Ye notes **lecture ko explain karte huye**, step-by-step flow me banaye gaye hain.  
> Language intentionally **simple Hinglish** me rakhi gayi hai, bilkul lecture jaise.

---

## 🔹 Lecture ka Objective
Is lecture ka main aim ye samajhna hai:

- **Static website kya hoti hai**
- Static websites ko **GitHub par FREE kaise deploy karte hain**
- **GitHub Pages** kya hota hai
- Deployment ke baad **automatic update (CI/CD)** kaise kaam karta hai

---

## 🔹 Static Website kya hoti hai?
Static website wo hoti hai jisme:
- ❌ Backend nahi hota
- ❌ Database nahi hota
- ✅ Sirf frontend hota hai

Examples:
- HTML
- CSS
- JavaScript
- React (frontend only build)

👉 Jaise:
- Portfolio website
- Todo app
- Landing pages

---

## 🔹 Static Website Deploy kyu karein?
Lecture me bataya gaya:

- Apna **portfolio** live dikhane ke liye
- Interview me project share karne ke liye
- FREE hosting ke liye (no server cost)
- GitHub profile ko strong banane ke liye

---

## 🔹 Deployment ka High-Level Flow
```text
Local Project
   ↓
GitHub Repository
   ↓
GitHub Pages
   ↓
Live Website (Public URL)
````

---

# 🔹 Step 1: GitHub par New Repository Banana

1. GitHub → **New Repository**
2. Repository name (example):

   ```
   deploy-demo / todo-app
   ```
3. Description (optional)
4. **Public** repository select karna (mandatory)

   * Kyunki website public hogi
5. Click **Create Repository**

👉 Ab ek remote repository ready hai

---

## 🔹 Step 2: Local Project Ready Hona

Local project structure (example):

```text
index.html
style.css
script.js
```

* HTML → structure
* CSS → styling
* JS → logic

---

## 🔹 Step 3: Git Initialize (Local)

Terminal open karo (Git Bash / VS Code terminal):

```bash
git init
```

👉 Ab version tracking start ho gayi

---

## 🔹 Step 4: Stage & Commit Project

```bash
git add .
git commit -m "Project done"
```

👉 Project ab **local repository** me save ho gaya

---

## 🔹 Step 5: Branch Rename (Important)

Local branch default hoti hai:

```text
master
```

GitHub default branch hoti hai:

```text
main
```

Isliye rename zaroori hai:

```bash
git branch -m main
```

---

## 🔹 Step 6: Remote Repository Connect Karna

```bash
git remote add origin <repo-url>
```

👉 Ab:

* Local repo
* Remote repo
  dono connect ho gaye

---

## 🔹 Step 7: Code Push to GitHub

```bash
git push -u origin main
```

👉 Ab:

* Code GitHub par upload ho gaya
* Repository me files dikhne lagengi

---

# 🔹 Step 8: GitHub Pages Enable Karna (Deployment)

### GitHub Repository → Settings

1. Settings open karo
2. Sidebar me **Pages** option par jao

---

### Pages Configuration

* **Source**:

  ```
  Branch: main
  Folder: /root
  ```
* Click **Save**

👉 Bas itna hi kaam hai

---

## 🔹 Deployment Status Samajhna

* 🟡 Yellow icon → Deployment **pending**
* ✅ Green tick → Deployment **successful**

GitHub automatically:

* Build karta hai
* Deploy karta hai

---

## 🔹 Live Website URL

Pages section me aapko ek URL milega, jaise:

```text
https://username.github.io/repo-name/
```

👉 Is link ko:

* Share kar sakte ho
* Interview me dikha sakte ho
* Portfolio me use kar sakte ho

---

# 🔹 CI/CD Concept (Lecture ka Important Part)

## 🔹 CI/CD kya hota hai?

### CI – Continuous Integration

* Code changes ko baar-baar integrate karna
* Small commits

### CD – Continuous Deployment

* Jaise hi code push ho
* Website **automatically update** ho jaati hai

---

## 🔹 Practical CI/CD Example (Lecture Flow)

### Step 1: Code Change

```html
Todo App  →  Todo List
```

### Step 2: Git Status

```bash
git status
```

### Step 3: Add & Commit

```bash
git add .
git commit -m "Title change"
```

### Step 4: Push

```bash
git push
```

👉 Bas itna hi!

---

## 🔹 Magic Kya Hua?

* Push ke baad:

  * GitHub Pages automatically rebuild
  * Website auto-deploy
* ❌ Dobara Pages settings me jaane ki zarurat nahi

---

## 🔹 Website Refresh Karne Par

* Live website refresh karoge
* Latest changes reflect ho jaayenge

👉 Ye hi **real CI/CD** hai

---

# 🔹 Important Points (Exam / Interview)

* GitHub Pages sirf **static websites** ke liye hota hai
* Backend / database supported nahi
* React app ke liye:

  * build folder deploy hota hai (next lecture)
* Deployment FREE hoti hai

---

## 🔹 One-Line Summary (Interview Ready)

* GitHub Pages static websites ko free deploy karta hai
* Code push → automatic deploy (CI/CD)
* Best for portfolios and frontend projects

---

## ⭐ Final Lecture Conclusion

> **“Ek baar Pages enable karo, uske baad sirf code push karo — deployment apne aap hoti rahegi.”**

---
