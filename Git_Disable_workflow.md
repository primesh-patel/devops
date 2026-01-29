# 📘 GitHub Actions – Workflow Disable & Enable Notes

> Is video me humne seekha ki **GitHub Actions workflows ko temporarily disable aur phir enable kaise karte hain**, aur **kyon kabhi-kabhi workflow disable karna zaroori hota hai**.

---

## 🔁 Recap (Previous Videos)

Pichhle videos me humne cover kiya:
- Event-based workflows (`push`, `pull_request`)
- Scheduled workflows (`cron`)
- Automation ka full flow

👉 Is video ka focus:
> **Existing workflow ko temporarily STOP (disable) karna**

---

## ❓ Workflow ko Disable kyon karna padta hai?

Normally workflows ka purpose hota hai:
- Automation
- Time save
- Manual work kam karna

Phir bhi kuch scenarios me workflow **disable karna smart decision hota hai** 👇

### 🔹 Common Scenarios

- 🔧 Project maintenance chal rahi ho
- 🔐 Security-related changes ho rahe ho
- 🐞 Sirf small bug fixes / minor changes
- 🚫 Unnecessary build, test, deploy avoid karna
- 💸 CI/CD cost bachana
- ⚠️ Half-baked changes pe deployment nahi chahiye

📌 Simple words me:
> **Jab tak kaam complete & stable na ho, workflow run nahi karwana**

---

## 🔹 Workflow Disable ka Effect

- Code push karoge → ❌ workflow run nahi hoga
- PR merge karoge → ❌ workflow run nahi hoga
- Scheduled workflow → ❌ execute nahi hoga

👉 Jab tak manually **Enable** na karo

---

## 🔹 Step 1: New Repository Create karna

1. GitHub → **Repositories**
2. Click **New**
3. Repository name:
```

disable-workflow

```
4. ✔️ Add README
5. Click **Create repository**

---

## 🔹 Step 2: Workflow Create karna

1. Repository → **Actions tab**
2. Click:
```

Set up a workflow yourself

```

GitHub structure automatically create karega:
```

.github/
└── workflows/
└── main.yml

````

---

## 🔹 Step 3: Basic Workflow Define karna

### Workflow Name
```yaml
name: Disable Workflow Video
````

### Trigger (Event-based)

```yaml
on:
  push:
    branches:
      - main
```

---

## 🔹 Step 4: Job & Steps Define karna

```yaml
jobs:
  disable:
    runs-on: ubuntu-latest
    steps:
      - name: Furzan
        run: echo "Disable workflow video devops"
```

📌 Iska matlab:

* `main` branch me push hoga
* Workflow run hoga
* Ek simple message print karega

---

## 🔹 Step 5: Commit Workflow

* Commit changes in `main` branch
* Result:

  * Workflow **automatically execute** hoga
  * Actions tab me:

    * 🟡 Pending
    * 🟢 Success

---

## 🔹 Step 6: Workflow Disable karna ⭐

### Disable karne ke steps:

1. Repository → **Actions**
2. Workflow select karo
3. Top-right corner me **three dots (⋮)** par click
4. Click:

   ```
   Disable workflow
   ```

---

## 🔹 Disable hone ke baad kya hota hai?

* Workflow ke naam ke aage:

  ```
  Disabled
  ```
* Code push karoge → ❌ koi yellow dot nahi
* Actions tab → ❌ koi new run nahi

📌 Workflow completely paused ho jata hai

---

## 🔹 Test: Disable Workflow Verify karna

1. `.github/workflows/main.yml` edit karo
2. Koi random change add karo
3. Commit karo

👉 Result:

* ❌ Workflow run nahi hoga
* ❌ Actions tab me koi activity nahi

---

## 🔹 Workflow Enable kaise karein?

### Enable steps:

1. Actions → Disabled workflow open karo
2. Three dots (⋮) par click
3. Click:

   ```
   Enable workflow
   ```

✔️ Ab workflow wapas active ho gaya

👉 Next code push par:

* Workflow fir se execute hoga

---

## 🔹 Disable vs Enable Summary

| Action                 | Workflow Run |
| ---------------------- | ------------ |
| Enabled                | ✅ Yes        |
| Disabled               | ❌ No         |
| Push during disable    | ❌ No run     |
| Re-enable ke baad push | ✅ Run        |

---

## 🔹 Important Points ⭐

* Workflow disable karna **temporary hota hai**
* Code delete karne ki zarurat nahi
* YAML file same rehti hai
* Disable/Enable **UI se hota hai**, code se nahi
* Scheduled workflows bhi disable ho jaate hain

---

## 🔹 Interview Questions ⭐

**Q1. Workflow disable kyon karte hain?**
➡ Maintenance, security, unnecessary CI/CD avoid karne ke liye

**Q2. Disable workflow ka effect kya hota hai?**
➡ Koi event ya schedule workflow trigger nahi hota

**Q3. Disable workflow kaise karte hain?**
➡ Actions → Workflow → Three dots → Disable

**Q4. YAML file delete hoti hai?**
➡ ❌ No, sirf execution rukta hai

---

## 🔹 One-Line Summary 🧠

> **GitHub Actions me workflow disable karke hum automation ko temporarily pause kar sakte hain bina code ya configuration delete kiye.**

---

## 🔚 Conclusion

* Aapne seekha:

  * Workflow disable kyon & kaise
  * Disable hone ke baad behavior
  * Enable karke wapas automation start karna
* Next videos me:

  * Advanced workflow control
  * Conditional workflows
  * Real DevOps use-cases

👉 **Next Topic: Advanced GitHub Actions Concepts**

---

```
::contentReference[oaicite:0]{index=0}
```
