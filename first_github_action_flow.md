```md
# 📘 GitHub Actions – First Workflow (Practical Explained Notes)

> Ye notes **GitHub Actions ka pehla practical workflow**  
> ko **step-by-step explain karte huye** banaye gaye hain.  
> Is video ka main goal hai:  
> 👉 **Theory → Practical transition**

---

## 🔁 Recap (Previous Videos)

Pichhli 2 videos me humne cover kiya tha:
- GitHub Actions kya hota hai
- Workflow ka concept
- Important terminologies:
  - Event / Trigger
  - Job
  - Step
  - Runner

📌 **Important:**  
Agar pichhli 2 videos nahi dekhi, to pehle wo zaroor dekho  
kyunki aaj ka video **purely practical** hai.

---

## 🎯 Is Video ka Objective

- GitHub Actions me **first workflow create karna**
- Ek **basic workflow** banana
- Samajhna:
  - Workflow kaise trigger hota hai
  - Kaise execute hota hai
  - Output kahan dikhta hai

---

## 🔹 Step 1: New Repository Create karna

1. GitHub → **Repositories**
2. Click on **New**
3. Repository name (example):
```

first-github-actions-workflow

```
4. Repository ko **Public** rakha
5. ✔️ `Add a README file` (checked)

👉 Repository ready ho gayi

---

## 🔹 Step 2: Workflow create karne ke 2 tareeke

### ❌ Manual (Lengthy)
- `.github/`
- `workflows/`
- `.yml` file banana

### ✅ Easy Way (Recommended)
- Repository ke **Actions tab** me jao
- GitHub khud templates + editor de deta hai

👉 Hum **easy way** use kar rahe hain

---

## 🔹 Step 3: Actions Tab → Setup Workflow

1. Repository → **Actions**
2. Click on:
```

Set up a workflow yourself

```
3. GitHub automatically bana deta hai:
```

.github/workflows/<file>.yml

````

📌 Workflow file **YAML format** me hoti hai

---

## 🔹 YAML (Quick Intro)

- YAML = **YAML Ain’t Markup Language**
- Human-readable format
- JSON jaisa, but simpler

⚠️ **Most Important Rule**  
> YAML me **indentation** bohot important hota hai  
> Space galat = workflow fail ❌

---

## 🔹 Step 4: Workflow ka Basic Structure

### 1️⃣ Workflow ka Name

```yaml
name: Farzan
````

👉 Ye naam **Actions tab** me dikhega

---

### 2️⃣ Event (Trigger) define karna

```yaml
on:
  push:
    branches:
      - main
```

📌 Meaning:

* Jab bhi **main branch** me code push hoga
* Workflow automatically start ho jayega

---

### 3️⃣ Jobs define karna

```yaml
jobs:
  demo:
```

* `demo` = job ka naam
* Aap kuch bhi naam rakh sakte ho

---

### 4️⃣ Runner define karna

```yaml
    runs-on: ubuntu-latest
```

👉 Runner = virtual machine
👉 `ubuntu-latest` = GitHub-hosted Linux machine

---

### 5️⃣ Steps define karna

```yaml
    steps:
      - name: Greetings
        run: echo "Hello from Apun"
```

📌 Explanation:

* Step ka naam: `Greetings`
* Kaam: terminal me message print karna

---

## 🔹 Complete Basic Workflow Example

```yaml
name: Farzan

on:
  push:
    branches:
      - main

jobs:
  demo:
    runs-on: ubuntu-latest
    steps:
      - name: Greetings
        run: echo "Hello from Apun"
```

---

## 🔹 Step 6: Workflow Commit karna

* Commit message:

  ```
  first workflow
  ```
* Commit **main branch** me hua

📌 Kyunki trigger `push on main` tha
👉 Workflow turant execute ho gaya

---

## 🔹 Step 7: Workflow Execution dekhna

1. Go to **Actions tab**
2. Workflow dikhega:

   * ⏳ Yellow dot = running / pending
   * ✅ Green tick = success

---

## 🔹 Workflow Details samajhna

### Workflow name

* Jo `name:` me likha → wahi dikhega

### Job name

* `demo` → job ka naam

### Runner info

* OS: Ubuntu
* Version: LTS
* Runner image details

### Step execution

* Step name: `Greetings`
* Output:

  ```
  Hello from Apun
  ```

---

## 🔹 Output kahan dikhta hai?

* Actions tab
* Workflow → Job → Step
* Terminal output clearly visible hota hai

---

## 🔹 Real-Life Use Case (Why this matters?)

Example:

* Next.js / React app
* Har push ke baad:

  * Build
  * Test
  * Deploy

❌ Manual way:

* Har baar commands chalani padti hain

✅ GitHub Actions:

* Ek baar workflow define
* Har push par sab **automatic**

👉 Ye hi hai **CI/CD**

---

## 🔹 Runners Tab (Intro)

* GitHub-hosted runners
* Self-hosted runners

📌 Detail me aage ki videos me cover hoga

---

## 🔹 Important Observations

* Workflow file → `.github/workflows/*.yml`
* Event trigger → `push`
* Job → `demo`
* Step → `Greetings`
* Output clearly visible

---

## 🔹 Interview Perspective ⭐

### Q1. Workflow kaise trigger hota hai?

> Event ke base par (push, PR, etc.)

### Q2. Workflow file kahan hoti hai?

> `.github/workflows/*.yml`

### Q3. Runner kya hota hai?

> Virtual machine jahan job execute hoti hai

### Q4. YAML me sabse important cheez?

> Indentation

---

## 🔹 One-Line Summary 🧠

> **GitHub Actions workflow ek automated process hai jo events ke base par jobs aur steps ko runner par execute karta hai.**

---

## 🔚 Conclusion

* Aapne apna **first GitHub Actions workflow** bana liya
* Ye sirf beginning hai
* Aage:

  * Build workflows
  * Test pipelines
  * Deployment automation
  * Advanced CI/CD

📌 Agar kuch clear na ho:

* Comments / Social media pe pooch sakte ho

🚀 Next Video: **Advanced GitHub Actions Workflows**

```
::contentReference[oaicite:0]{index=0}
```
