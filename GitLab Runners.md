# 🏃 GitLab Runners – Detailed Interview Notes

> Is lecture me humne **GitLab Runners** ka concept detail me samjha  
> Ye topic **DevOps interviews + CI/CD understanding** ke liye bahut important hai.

---

## 🎯 Lecture Objective

Is lecture ke baad aap samajh paoge:

- GitLab Runner kya hota hai
- CI/CD pipeline me iska role
- gitlab-ci.yml ka use
- GitLab Runner ke types:
  - Shared Runner
  - Group Runner
  - Specific Runner
- Real-life use cases

---

## 🔹 GitLab Runner Kya Hota Hai?

### ✅ Definition
GitLab Runner =  
👉 Lightweight executor  
👉 Jo CI/CD jobs ko run karta hai

---

### 📌 Simple Words Me

- Aap pipeline banate ho
- Pipeline me jobs hoti hain:
  - Build
  - Test
  - Deploy

👉 In jobs ko execute kaun karega?  
➡ GitLab Runner

---

## 🔹 CI/CD Flow Me Runner Ka Role

### Step Flow:

```

Developer Code Push karta hai
↓
gitlab-ci.yml trigger hoti hai
↓
Pipeline create hoti hai
↓
Runner jobs execute karta hai

````

---

## 🔹 gitlab-ci.yml File Kya Hoti Hai?

📂 Location:
- Project root directory

📄 Purpose:
- CI/CD scripts define karna

---

### Example Use Case

Agar aap React project bana rahe ho:

```yaml
build:
 script:
   - npm install
   - npm run build
````

👉 Ye commands Runner par run hongi

---

## 🔹 GitLab Runner Ka Main Kaam

✔ Pipeline jobs execute karna
✔ Automation enable karna
✔ CI/CD workflow run karna

---

## 🔥 GitLab Runner Types (Most Important – Interview)

GitLab Runners 3 Types ke hote hain:

1️⃣ Shared Runners
2️⃣ Group Runners
3️⃣ Specific Runners

---

# 🟢 1️⃣ Shared Runners

## 🔹 Kya Hote Hain?

* GitLab ke dwara manage hote hain
* Multiple projects use kar sakte hain
* Mostly public projects ke liye

---

## 🔹 Key Features

✔ GitLab managed
✔ Easy setup
✔ Public projects ke liye useful
✔ Small & Medium projects ke liye best

---

## 🔹 Limitations

❌ Free tier limits
❌ Account verification required
❌ Credit card verification sometimes required

---

## 🔹 Use Case

👉 Agar aapke multiple public projects hain
👉 Aur aap ek hi runner use karna chahte ho

---

# 🟡 2️⃣ Group Runners

## 🔹 Kya Hote Hain?

👉 Specific GitLab Group ke saare projects ke liye available

---

## 🔹 Example

Organization = Techno

Projects:

* Mobile App
* Web App
* Desktop App

👉 Sab ek hi group me
👉 Ek hi Runner sab ke liye use ho sakta hai

---

## 🔹 Key Features

✔ Group level sharing
✔ Team collaboration friendly
✔ Controlled by Group Admin

---

## 🔹 Use Case

👉 Team multiple projects par kaam kar rahi ho
👉 Same infra sab projects me use karna ho

---

# 🔴 3️⃣ Specific Runners (Project Runners)

## 🔹 Kya Hote Hain?

👉 Ek single project ke liye dedicated runner

---

## 🔹 Key Features

✔ Full control
✔ Custom configuration possible
✔ Private projects ke liye best
✔ Self-hosted setup possible

---

## 🔹 Use Case

👉 Highly secure environment
👉 Custom infrastructure
👉 Local server / private cloud
👉 Sensitive data projects

---

## 🔹 Example Scenario

Agar aap:

* Firebase / Supabase project run kar rahe ho
* Data cloud par nahi bhejna chahte
* Local server par CI/CD chalana chahte

👉 Use Specific Runner

---

## 🔹 Self Hosted Runner Concept

👉 Aap khud runner setup karte ho
👉 Docker + Local Machine use hota hai
👉 Full control milta hai

---

# 🔥 Quick Comparison Table

| Feature      | Shared       | Group          | Specific       |
| ------------ | ------------ | -------------- | -------------- |
| Managed By   | GitLab       | Group Admin    | Project Owner  |
| Scope        | All Projects | Group Projects | Single Project |
| Control      | Low          | Medium         | Full           |
| Security     | Medium       | Good           | Highest        |
| Setup Effort | Very Easy    | Medium         | High           |

---

# 🧠 Interview Important Points

### Q1. GitLab Runner kya karta hai?

➡ CI/CD jobs execute karta hai

---

### Q2. Runner scripts kaha define hoti hain?

➡ gitlab-ci.yml file me

---

### Q3. Shared vs Group vs Specific Difference?

👉 Shared → GitLab managed, multi projects
👉 Group → Group level projects
👉 Specific → Single project dedicated

---

### Q4. High Security me kaunsa use kare?

➡ Specific Runner

---

### Q5. Team Projects me kaunsa best?

➡ Group Runner

---

### Q6. Small project + easy setup?

➡ Shared Runner

---

# 🧾 One-Line Summary

👉 GitLab Runner = CI/CD jobs execute karne wala engine
👉 Types decide karte hain scope + control + security

---

# 🚀 Real World Strategy

Small Startup → Shared Runner
Team Product → Group Runner
Enterprise Secure System → Specific Runner

---

# 🔚 Final Conclusion

GitLab Runner CI/CD ka backbone hai
Runner ke bina pipeline sirf configuration file hoti hai
Runner hi actual automation execute karta hai

---

## 📌 Golden Line (Interview Ready)

> "GitLab Runner is an execution agent that runs CI/CD jobs defined inside gitlab-ci.yml pipelines."

---

```
```
