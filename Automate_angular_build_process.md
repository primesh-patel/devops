# 📘 GitHub Actions – Angular Application Build Workflow (Detailed Notes)

> Is lecture me humne **GitHub Actions ka use karke Angular application ki automatic build kaise banate hain** – step by step, bilkul scratch se, practical example ke saath samjha.

---

## 🔁 Lecture Context (Background)

- Angular application already created hai
- Code **local machine → GitHub repository** me push ho chuka hai
- Ab goal ye hai ki:
  👉 **Jab bhi main branch me code push ho**
  👉 **Angular app ki build automatically ban jaye**
- Manual build (`npm run build`) avoid karna hai
- Pure process ko **CI automation** banana hai

👉 Is automation ke liye hum **GitHub Actions Workflow** use karte hain

---

## 🎯 Objective of This Workflow

✔️ Angular app ka code checkout karna  
✔️ Node.js environment setup karna  
✔️ Dependencies install karna  
✔️ Angular app ki build banana  
✔️ Ye sab **automatically on every push (main branch)**

---

## 🔹 Step 1: Actions Tab me Workflow Create karna

1. GitHub Repository open karo
2. **Actions** tab pe jao
3. Built-in templates use nahi karne
4. Click:
```

Set up a workflow yourself

```

GitHub automatically ye structure bana deta hai:

```

.github/
└── workflows/
└── main.yml

````

---

## 🔹 Step 2: Workflow Name Define karna

```yaml
name: Build My Angular App
````

📌 Ye naam Actions tab me visible hota hai

---

## 🔹 Step 3: Workflow Trigger (Event)

```yaml
on:
  push:
    branches:
      - main
```

📌 Matlab:

* Jab **main branch** me code push hoga
* Workflow automatically execute hoga

---

## 🔹 Step 4: Job Define karna

```yaml
jobs:
  build-angular-app:
```

📌 Job ka naam kuch bhi ho sakta hai
Yahan job ka kaam: **Angular app build karna**

---

## 🔹 Step 5: Runner (Virtual Machine)

```yaml
runs-on: ubuntu-latest
```

📌 GitHub ek **Ubuntu-based virtual machine** provide karta hai
Isi machine par:

* Node.js install hoga
* npm commands run hongi
* Angular build banegi

---

## 🔹 Step 6: Steps Define karna (Most Important ⭐)

### ✅ Step 1: Code Checkout

```yaml
- name: Checkout code
  uses: actions/checkout@v4
```

📌 Kya karta hai?

* GitHub repository ka latest code
* Runner machine me copy karta hai

➡️ Without checkout, build possible nahi

---

### ✅ Step 2: Node.js Setup

```yaml
- name: Setup Node.js
  uses: actions/setup-node@v4
  with:
    node-version: 22.1
```

📌 Kyun zaroori hai?

* Angular = Node.js based framework
* npm commands Node ke bina run nahi hoti

📌 `with` ka use:

* Node.js ka **specific version** define karne ke liye

---

### ✅ Step 3: Install Dependencies

```yaml
- name: Install dependencies
  run: npm install
```

📌 Ye command:

* `package.json` read karti hai
* Required libraries install karti hai
* `node_modules` folder banata hai

---

### ✅ Step 4: Build Angular Application

```yaml
- name: Build Angular App
  run: npm run build
```

📌 Ye step:

* Angular app ki production build banata hai
* `dist/` folder generate hota hai

---

## 🔹 Complete Workflow YAML (Final)

```yaml
name: Build My Angular App

on:
  push:
    branches:
      - main

jobs:
  build-angular-app:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 22.1

      - name: Install dependencies
        run: npm install

      - name: Build Angular App
        run: npm run build
```

---

## ⚠️ YAML Indentation – Very Important

* YAML **space sensitive** hota hai
* Galat indentation = ❌ workflow fail
* `steps` → `runs-on` ke **andar** aate hain
* Har `-` ek naya step hota hai

---

## 🔹 Step 7: Commit Workflow

* File save karo
* Commit message:

  ```
  Build Angular workflow
  ```
* Commit directly in `main` branch

---

## 🔹 Step 8: Workflow Execution Observe karna

1. Actions tab open karo
2. Workflow **Processing / Running** dikhega
3. Steps execution order:

   * Job setup
   * Checkout
   * Node.js setup
   * npm install
   * npm run build
4. End me:

   * ✅ Green success icon

📌 Matlab:

> Angular app ki build successfully ban chuki hai

---

## 🔹 Output me kya dikhai deta hai?

* Runner image details
* Node.js version
* npm logs
* Build logs
* Success status

---

## 🔹 Real-Life Benefit ⭐

❌ Manual build bar-bar nahi
❌ Human error kam
✔️ Consistent builds
✔️ CI process ready
✔️ Easy deployment integration

---

## 🔹 Interview Ready Points 🧠

**Q1. Angular build automation ke liye GitHub Actions kyu?**
➡ CI/CD automate karne ke liye

**Q2. actions/checkout ka role?**
➡ Repository code runner me lana

**Q3. setup-node kyu use hota hai?**
➡ Node.js environment setup ke liye

**Q4. npm install kyu zaroori?**
➡ Dependencies install karne ke liye

**Q5. Workflow kab run hota hai?**
➡ Main branch me push hone par

---

## 🧾 One-Line Summary

> **GitHub Actions workflow ka use karke hum Angular application ki build ko fully automate kar sakte hain jo har main-branch push par automatically generate hoti hai.**

---

## 🔚 Conclusion

* Aapne seekha:

  * Angular build workflow create karna
  * GitHub Actions Marketplace actions use karna
  * Node.js + npm automation
* Next level:

  * Build artifacts upload
  * Deployment workflows
  * CI + CD pipelines

👉 **Next Video: Angular Build + Deployment using GitHub Actions 🚀**

```
::contentReference[oaicite:0]{index=0}
```
