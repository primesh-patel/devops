# 📘 GitHub Actions – Job Concurrency (Latest Commit Only)

> Is lecture me humne **Job Concurrency** ka concept detail me samjha aur dekha ki kaise GitHub Actions workflow me implement karke  
> **sirf latest commit ka workflow run** karaya ja sakta hai aur **purane running workflows cancel** kiye ja sakte hain.

---

## 🎯 Lecture Objective

Is video ka main purpose tha:

- **Job Concurrency** kya hota hai samajhna  
- Rapid / multiple commits ke case me:
  - Purane workflows cancel karna
  - Sirf **latest commit** par build / deploy chalana  
- GitHub Actions workflow me `concurrency` use karna

---

## ❓ Problem Without Job Concurrency

### Real-life Scenario
- Ek hi project par:
  - Aap code push karte ho
  - Friend 1 code push karta hai
  - Friend 2 code push karta hai

### Default GitHub Actions Behavior
- Har commit ke liye:
  - Workflow queue me chala jata hai
  - Pehle commit ka build
  - Phir second commit ka build
  - Phir third commit ka build

### ❌ Problem
- Time waste
- Resources waste
- Deploy hona chahiye **sirf last commit**
- Purane commits ka build / deploy meaningless hota hai

---

## ✅ Solution: Job Concurrency

**Job Concurrency** ensure karta hai:

- Agar koi workflow already run ho raha hai
- Aur uske beech me naya commit aa jaye
- To:
  - Purana workflow ❌ cancel
  - Naya (latest commit) workflow ✅ run

📌 Result:
> **Always deploy/build latest code only**

---

## 🔹 What is Job Concurrency?

- GitHub Actions ka feature
- Multiple workflow runs ko **control** karta hai
- Prevents:
  - Unnecessary workflow queue
  - Old builds from running

---

## 🔹 Key Concept

> **Latest commit wins. Old workflows get cancelled.**

---

## 🔹 When to Use Job Concurrency?

- CI/CD pipelines
- Deployment workflows
- Build pipelines
- Rapid commits environment
- Production deploys

---

## 🔹 Workflow Creation Steps

### 1️⃣ Go to Repository → Actions  
### 2️⃣ Click **Set up a workflow yourself**  
Creates:
```

.github/workflows/main.yml

````

---

## 🔹 Step 1: Workflow Name

```yaml
name: Job Concurrency Example
````

---

## 🔹 Step 2: Trigger Event

```yaml
on:
  push:
    branches:
      - main
```

📌 Jab bhi `main` branch me commit hoga

---

## 🔹 Step 3: Job & Runner

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
```

📌 Ubuntu-based GitHub runner

---

## 🔹 Step 4: Job Concurrency ⭐ (MOST IMPORTANT)

```yaml
    concurrency:
      group: deploy
      cancel-in-progress: true
```

### 🔍 Explanation

| Property             | Meaning                                     |
| -------------------- | ------------------------------------------- |
| `group`              | Logical group name (same workflows grouped) |
| `cancel-in-progress` | Old running workflows cancel                |

📌 `true` ka matlab:

> Agar same group ka koi workflow already run ho raha ho
> to usko cancel kar do aur new workflow run karo

---

## 🔹 Step 5: Workflow Steps

### ✅ Step 1: Checkout Repository

```yaml
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4
```

📌 Latest commit ka code runner pe aata hai

---

### ✅ Step 2: Install Dependencies

```yaml
      - name: Install dependencies
        run: npm install
```

---

### ✅ Step 3: Build Next.js App

```yaml
      - name: Build Next.js App
        run: npm run build
```

---

### ✅ Step 4: Deploy (Demo Step)

```yaml
      - name: Deploy Application
        run: echo "Deploying application..."
```

📌 Real deployment (Vercel, AWS, etc.) yahan hota

---

## 🔹 Complete Workflow YAML

```yaml
name: Job Concurrency Example

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    concurrency:
      group: deploy
      cancel-in-progress: true

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Install dependencies
        run: npm install

      - name: Build Next.js App
        run: npm run build

      - name: Deploy Application
        run: echo "Deploying application..."
```

---

## 🔹 Practical Demo Summary

1. Commit #1 → Workflow started (Pending)
2. Commit #2 → New workflow triggered
3. Result:

   * Commit #1 workflow ❌ cancelled
   * Commit #2 workflow ✅ running
4. Commit #3 → Commit #2 cancelled, Commit #3 runs

📌 **Only latest commit survives**

---

## 🔹 Why This is Important?

### ❌ Without Concurrency

* Multiple builds
* Slow CI
* Wrong deploy versions

### ✅ With Concurrency

* Faster pipelines
* Correct deploy
* Clean CI/CD

---

## 🔹 Interview Questions 🧠

**Q1. Job concurrency ka use kyon karte hain?**
➡ Latest commit ke liye sirf ek workflow run karne ke liye

**Q2. `cancel-in-progress: true` ka matlab?**
➡ Old running workflows cancel ho jaate hain

**Q3. `group` ka role kya hai?**
➡ Same group ke workflows ko ek saath manage karta hai

**Q4. CI/CD me concurrency kahan useful hoti hai?**
➡ Deployment pipelines, build pipelines

---

## 🔹 One-Line Summary

> **Job Concurrency ensures that only the latest commit’s workflow runs and all older running workflows are automatically cancelled.**

---

## 🔚 Conclusion

* Job concurrency:

  * Production-grade CI/CD ka essential feature
  * Time & resources save karta hai
* Best practice:

  * Deploy workflows me hamesha use karein

👉 **Next Video: Advanced deployment & environment strategies 🚀**

```
```
