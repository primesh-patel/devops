# 📘 GitHub Actions – Caching & Artifacts (Next.js / JS Application Build)

> Is lecture me humne **JavaScript / Next.js application** ke liye GitHub Actions workflow banaya jisme:
> - Application build hoti hai  
> - Workflow execution **fast** hota hai using **caching**  
> - Build output ko **artifacts** me store kiya jata hai  

---

## 🎯 Lecture Objective

Is video ka main goal tha:

- JS / Next.js app ki **automatic build**
- **Caching** use karke workflow ko fast banana
- **Artifacts** use karke build ko store & reuse karna

👉 Angular nahi, balki **Next.js (JS app)** par kaam kiya gaya

---

## 🔁 Why Caching & Artifacts?

### ❓ Problem Without Caching
- Har workflow run me:
  - `npm install` dobara hota hai
  - `node_modules` bar-bar install hota hai
- Result:
  - Workflow slow
  - Time & resources waste

### ❓ Problem Without Artifacts
- Har deploy ke liye:
  - Build dobara banana padti hai
- Result:
  - Unnecessary rebuilds
  - Debug / reuse difficult

---

## 🚀 Solution

| Concept | Purpose |
|------|--------|
| **Caching** | Workflow execution fast karna |
| **Artifacts** | Build output ko store & reuse karna |

---

## 🔹 What is Caching?

- Heavy files ko **cache** me store kar leta hai
- Example:
  - `node_modules`
- Next run me:
  - Same dependencies dobara install nahi hoti
  - Workflow **fast execute** hota hai

📌 Mostly used for:
- `npm`
- `yarn`
- `pip`
- `maven`

---

## 🔹 What are Artifacts?

- Workflow ke output files
- Example:
  - Build folder
- Use cases:
  - Download build
  - Debug
  - Deploy later
  - Reuse in another workflow

📌 Artifact = **Saved result of workflow**

---

## 🔹 Step 1: Workflow Create karna

1. Repository → **Actions**
2. Click:
```

Set up a workflow yourself

```
3. File create hoti hai:
```

.github/workflows/main.yml

````

---

## 🔹 Step 2: Workflow Name

```yaml
name: NextJS Build with Caching and Artifacts
````

---

## 🔹 Step 3: Trigger Event

```yaml
on:
  push:
    branches:
      - main
```

📌 Jab bhi `main` branch me code push hoga

---

## 🔹 Step 4: Job & Runner

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
```

📌 GitHub hosted Ubuntu VM use hogi

---

## 🔹 Step 5: Steps Breakdown ⭐

---

### ✅ Step 1: Checkout Repository

```yaml
- name: Checkout repository
  uses: actions/checkout@v4
```

📌 Repository ka code runner machine par laata hai

---

### ✅ Step 2: Setup Node.js + Enable Caching ⭐

```yaml
- name: Setup Node.js
  uses: actions/setup-node@v4
  with:
    node-version: 22
    cache: 'npm'
```

📌 Important points:

* Node.js version set ki
* `cache: npm`:

  * `node_modules` ko cache karega
  * Next runs me install fast ho jayega

---

### ✅ Step 3: Install Dependencies

```yaml
- name: Install dependencies
  run: npm install
```

📌 Dependencies:

* `package.json` se install hoti hain
* Cache hone ki wajah se fast execution

---

### ✅ Step 4: Build Next.js Application

```yaml
- name: Build NextJS App
  run: npm run build
```

📌 Build output:

* `.next/`
* `out/` (depending on config)

---

### ✅ Step 5: Upload Build as Artifact ⭐

```yaml
- name: Upload build artifacts
  uses: actions/upload-artifact@v4
  with:
    name: nextjs-build
    path: out/
```

📌 Explanation:

* `name`: Artifact ka naam
* `path`: Build folder ka path

👉 Build output GitHub par safely store ho jata hai

---

## 🔹 Complete Workflow YAML (Final)

```yaml
name: NextJS Build with Caching and Artifacts

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 22
          cache: 'npm'

      - name: Install dependencies
        run: npm install

      - name: Build NextJS App
        run: npm run build

      - name: Upload build artifacts
        uses: actions/upload-artifact@v4
        with:
          name: nextjs-build
          path: out/
```

---

## ⚠️ YAML Indentation Reminder

* YAML **space sensitive** hota hai
* `steps` → `runs-on` ke andar
* Galat indentation = ❌ workflow fail

---

## 🔹 Workflow Execution Flow

1. Code push on `main`
2. Runner start
3. Repository checkout
4. Node.js setup + cache restore
5. Dependencies install
6. App build
7. Build upload as artifact
8. ✅ Success

---

## 🔹 Benefits Summary ⭐

### 🚀 Caching

* Fast builds
* Less time waste
* CI optimized

### 📦 Artifacts

* Build reuse
* Easy download
* Deployment ready
* Debug friendly

---

## 🔹 Interview Ready Points 🧠

**Q1. Caching ka use kyon karte hain?**
➡ Workflow execution fast karne ke liye

**Q2. npm caching kaise hoti hai?**
➡ `actions/setup-node` ke `cache: npm` se

**Q3. Artifacts kya hote hain?**
➡ Workflow ke output files jo GitHub me store hote hain

**Q4. Artifacts ka use kahan hota hai?**
➡ Deploy, debug, reuse, download

**Q5. Cache aur Artifact me difference?**

| Cache         | Artifact        |
| ------------- | --------------- |
| Speed ke liye | Storage ke liye |
| Temporary     | Persistent      |
| node_modules  | build output    |

---

## 🧾 One-Line Summary

> **Caching workflow ko fast banata hai aur Artifacts build output ko store karke future reuse aur deployment ke liye ready rakhta hai.**

---

## 🔚 Conclusion

* Aapne seekha:

  * JS / Next.js build automation
  * npm caching
  * Artifact upload
* Ye concepts:

  * CI/CD ka backbone hote hain
  * Production-level DevOps me mandatory hote hain

👉 **Next Video: Artifact download & Deployment workflows 🚀**

```
```
