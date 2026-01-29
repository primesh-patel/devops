# 📘 GitHub Actions – Scheduled Workflow (Cron Jobs) Notes

> Is video me humne seekha ki **GitHub Actions workflow ko time ke basis par kaise schedule** kiya jaata hai.  
> Yaani ab workflow **sirf push / PR events par nahi**, balki **fixed time par automatically run** ho sakta hai.

---

## 🔁 Recap (Previous Video)

Last video me humne dekha tha:
- Event-based workflow
- `push` event par workflow execution
- First GitHub Actions workflow create kiya

👉 Is video ka focus:
> **Event-based → Time-based automation**

---

## 🎯 Is Video ka Objective

- Workflow ko **schedule karna**
- `schedule` trigger ka use samajhna
- `cron` expression ko samajhna
- Daily / Weekly automation ka concept

---

## 🔹 Scheduling ka Concept kya hota hai?

Scheduling ka matlab:
- Kisi **specific time** par workflow execute karwana  
- Bina code push / PR ke

### 🔁 Real-life examples:
- Daily backup (raat 12 baje)
- Weekly report generate karna
- Nightly system updates
- Logs cleanup

📌 Yahan **event (push / PR)** ka koi role nahi hota  
👉 Sirf **time** important hota hai

---

## 🔹 Step 1: New Repository Create karna

1. GitHub → **Repositories**
2. Click **New**
3. Repository name:
```

schedule-workflow

```
4. Public repository
5. ✔️ Add README file
6. Click **Create repository**

---

## 🔹 Step 2: Workflow Create karna

1. Repository → **Actions tab**
2. Click:
```

Set up a workflow yourself

```

GitHub automatically create karega:
```

.github/
└── workflows/
└── main.yml

````

---

## 🔹 Step 3: Workflow ka Name

```yaml
name: Schedule Job
````

👉 Ye naam Actions tab me dikhega

---

## 🔹 Step 4: Schedule Trigger (`on: schedule`)

### ❌ Event-based (old)

```yaml
on: push
```

### ✅ Time-based (new)

```yaml
on:
  schedule:
    - cron: "0 0 * * *"
```

---

## 🔹 Cron kya hota hai? ⭐

* **Cron = Time-based Job Scheduler**
* Automation ke liye use hota hai
* Interview me poocha jaata hai

### Cron Full Form:

> **CRON = Command Run ON time**

---

## 🔹 Cron Expression Format

```text
MINUTE  HOUR  DATE  MONTH  DAY-OF-WEEK
```

| Field      | Range |
| ---------- | ----- |
| Minute     | 0–59  |
| Hour       | 0–23  |
| Date       | 1–31  |
| Month      | 1–12  |
| Day (Week) | 0–6   |

---

## 🔹 Cron Example Used in Video

```yaml
cron: "0 0 * * *"
```

### Meaning:

* `0` → Minute = 0
* `0` → Hour = 0 (12:00 AM)
* `*` → Any date
* `*` → Any month
* `*` → Any day

📌 Result:

> **Workflow roz raat 12:00 baje execute hoga**

---

## 🔹 `*` (Asterisk) ka Matlab

* `*` = **Any value**
* Koi restriction nahi

Example:

* Any day
* Any month
* Any week

---

## 🔹 Step 5: Jobs Define karna

```yaml
jobs:
  run-script:
```

* `run-script` = job ka naam
* Aap kuch bhi rakh sakte ho

---

## 🔹 Step 6: Runner Define karna

```yaml
    runs-on: ubuntu-latest
```

👉 Runner = virtual machine
👉 `ubuntu-latest` = GitHub-hosted Linux VM

---

## 🔹 Step 7: Steps Define karna

```yaml
    steps:
      - name: Print Message
        run: echo "Schedule workflow executed"
```

📌 Is example me:

* Ek simple message print ho raha hai
* Real use case me:

  * backup
  * update
  * script execution
  * reports

---

## 🔹 Complete Scheduled Workflow Example

```yaml
name: Schedule Job

on:
  schedule:
    - cron: "0 0 * * *"

jobs:
  run-script:
    runs-on: ubuntu-latest
    steps:
      - name: Print Message
        run: echo "Schedule workflow executed"
```

---

## 🔹 Step 8: Commit Workflow

* Commit message:

  ```
  schedule workflow
  ```

📌 Commit ke baad:

* Workflow **immediately run nahi hoga**
* Ye **sirf scheduled time par** run karega

---

## 🔹 Actions Tab me kya dikhega?

* Workflow name visible hoga
* ❌ Abhi koi run nahi dikhega
* ✔️ Run tab dikhega **raat 12 baje ke baad**

Reason:

> Workflow scheduled hai, event-based nahi

---

## 🔹 Workflow Code dekhna

* Code tab → `.github/workflows/main.yml`
* Ya Actions → Workflow → View file

---

## 🔹 Important Points ⭐

* Scheduled workflows:

  * Push / PR par run nahi hote
  * Sirf cron time par run hote hain
* Cron time **UTC** me hota hai (GitHub standard)
* Indentation YAML me **bahut important**

---

## 🔹 Interview Questions ⭐

**Q1. GitHub Actions me scheduling kaise hoti hai?**
➡ `on: schedule` + `cron`

**Q2. Cron kya hota hai?**
➡ Time-based job scheduler

**Q3. `"0 0 * * *"` ka matlab?**
➡ Roz raat 12:00 baje workflow run

**Q4. Event aur schedule me difference?**
➡ Event = action-based
➡ Schedule = time-based

---

## 🔹 One-Line Summary 🧠

> **GitHub Actions me `schedule` trigger aur `cron` ka use karke hum workflows ko specific time par automatically run kar sakte hain.**

---

## 🔚 Conclusion

* Aapne seekh liya:

  * Scheduled workflow kaise banate hain
  * Cron ka format
  * Time-based automation
* Aage ki videos me:

  * Advanced cron examples
  * Real-world scheduled jobs
  * Complex CI/CD pipelines

👉 Next topic = **Advanced GitHub Actions Concepts**

---
