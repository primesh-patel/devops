# 📘 GitHub Actions – Workflow Concept (Theory Notes in Hinglish)

> Ye notes **GitHub Actions Workflow** ke lecture ko  
> **step-by-step explain karte huye** banaye gaye hain.  
> Ye video **theory clarity** ke liye hai, taaki next videos me  
> **practical implementation** easily samajh aa sake ⭐

---

## 🔹 Ye video alag kyun banayi gayi?

Instructor ne theory ko **separate video** me isliye cover kiya hai taaki:

- Practical videos me confusion na ho  
- Terminology pehle se clear ho  
- Pure focus sirf **implementation** par rahe  

👉 Pehle **concept clear**, phir **hands-on practice**

---

## 🔹 GitHub Actions Workflow kya hota hai?

**Workflow** ek:

- Automated process hota hai
- Jo **events / triggers** ke base par run hota hai
- GitHub repository ke andar define hota hai

👉 Simple words me:  
> Workflow = “Agar ye event ho, to ye kaam automatically kar do”

---

## 🔹 Workflow kab run hota hai? (Triggers / Events)

Workflow tab run hota hai jab koi **event occur** hota hai, jaise:

- Code push hona
- Pull Request create ya merge hona
- Scheduled time (cron job)
- Manual trigger

👉 Inhi events ko:
- **Triggers** bhi bolte hain  
- **Events** bhi bolte hain  

---

## 🔹 Trigger / Event kya hota hai?

**Event / Trigger** ka matlab:

- Repository me koi action perform hua
- Jis par workflow ko react karna hai

### Examples:
- `push` → code push hua
- `pull_request` → PR create / merge hui
- `schedule` → fixed time par workflow run

👉 Event decide karta hai:
> “Workflow kab start hoga?”

---

## 🔹 Workflow ko define kahan karte hain?

Workflow hamesha define hota hai:

```

.github/workflows/

```

- Is folder ke andar **YAML file** hoti hai
- YAML file ke andar workflow ka logic likha hota hai

👉 Yahin par hum batate hain:
- Kaunsa trigger
- Kaunsa job
- Kaunse steps

---

## 🔹 YAML file ka role (Intro)

- Workflow YAML file me likha jata hai
- Isme hum define karte hain:
  - Triggers
  - Jobs
  - Steps
  - Runners

📌 YAML ko detail me **next video** me explain kiya jayega

---

## 🔹 GitHub Actions Workflow ki Important Terminology

Workflow samajhne ke liye ye terms **must-know** hain 👇

---

## 1️⃣ Event / Trigger

- Event batata hai workflow **kab run hoga**
- Workflow hamesha event ke base par start hota hai

### Common Events:
- Code push
- Pull request merge
- Schedule
- Manual trigger

👉 Event = Starting point of workflow

---

## 2️⃣ Job

**Job** kya hota hai?

- Job ek **set of steps** hota hai
- Jo ek runner ke andar execute hota hai

### Examples of Jobs:
- Build job
- Test job
- Deploy job

👉 Job batata hai:
> “Kya kaam karna hai?”

---

## 3️⃣ Step

**Step** kya hota hai?

- Job ke andar ek **single task**
- Job me multiple steps ho sakte hain

### Examples of Steps:
- Dependency install karna
- Script run karna
- Test run karna

👉 Step = Job ka chhota unit

---

## 4️⃣ Runner

**Runner** kya hota hai?

- Ek virtual machine jahan workflow run hota hai

### Runner types:
- GitHub-hosted runner
- Self-hosted runner

👉 Runner = Execution environment

---

## 🔹 Workflow Execution Flow (Most Important ⭐)

Workflow ka execution flow hamesha aise hota hai:

1. Sabse pehle **Event occur hota hai**
   - (push, PR merge, etc.)

2. Event ke baad **Workflow start hota hai**

3. Workflow check karta hai:
   - Is event par kaunse jobs defined hain

4. Defined **Jobs execute hoti hain**
   - Jobs parallel me run ho sakti hain

5. Har job ke andar:
   - Steps execute hote hain

👉 Ye pura process automatic hota hai

---

## 🔹 Parallel Execution ka concept

- Workflow ke andar multiple jobs ho sakti hain
- Jobs **parallel** execute hoti hain
- Isse execution fast hota hai

👉 GitHub Actions fast isliye hai kyunki:
- Jobs parallel run hoti hain

---

## 🔹 Workflow ka overall flow (One-glance)

```

Event occurs
↓
Workflow starts
↓
Jobs execute (parallel)
↓
Steps run inside jobs

```

---

## 🔹 Ye concepts kyun important hain?

Kyuki next videos me:

- YAML likhi jayegi
- Workflows banenge
- Jobs & steps define honge
- Real CI/CD pipelines create honge

👉 Agar ye terms clear nahi hongi  
to practical me confusion hoga ❌

---

## 🔹 Interview Perspective ⭐

### Q1. Workflow kya hota hai?
> Automated process triggered by events in GitHub Actions

### Q2. Workflow kahan define hota hai?
> `.github/workflows/*.yml`

### Q3. Event kya hota hai?
> Trigger jo workflow ko start karta hai

### Q4. Job kya hoti hai?
> Set of steps executed on a runner

### Q5. Step kya hota hai?
> Single task inside a job

### Q6. Runner kya hota hai?
> Virtual machine where workflow runs

---

## 🔹 One-Line Summary 🧠

> **Workflow is an automated process in GitHub Actions that runs on events and executes jobs and steps on runners.**

---

## 🔹 Final Note

- Ye video **foundation strong** karne ke liye hai
- Next videos me:
  - YAML
  - Real workflows
  - CI/CD pipelines
  - Practical demos

📌 Recommendation:
> Ye workflow wali video + pichhli theory wali video  
> **dono ek baar zaroor revise karo**
