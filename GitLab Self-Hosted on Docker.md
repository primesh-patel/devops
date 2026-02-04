# 🦊 GitLab Self-Hosted on Docker – Complete Notes

## 🎯 Video ka Objective

Is video me hum seekhte hain:

- GitLab cloud ki limitations kya hoti hain
- GitLab ko **Docker ke upar locally** kaise run karein
- Self-hosted GitLab ka concept
- GitLab ka initial setup (username & password)
- Docker commands ka real use

👉 Ye topic **DevOps + GitLab + Docker interviews** ke liye bahut important hai.

---

## ❓ Problem with GitLab Cloud (Official Platform)

GitLab ke official cloud platform par:

- Free plan me **limitations** hoti hain
- Kai advanced features **paid plans** me hote hain
- Bank / billing integration ki need hoti hai
- Unlimited experimentation possible nahi hota

👉 Isliye hum **self-hosted GitLab** use karte hain.

---

## ✅ Self-Hosted GitLab Kya Hota Hai?

Self-hosted GitLab ka matlab:

- GitLab ka **apna server**
- Apne system par hi GitLab run karna
- Koi cloud limitation nahi
- Sab kuch **local + free + unlimited**

👉 Docker ke through GitLab ko easily self-host kiya ja sakta hai.

---

## 🐳 Docker Kyu Use Kiya GitLab ke Liye?

- GitLab ka setup kaafi heavy hota hai
- Manual installation complex hai
- Docker image ke through:
  - Easy setup
  - Clean environment
  - No dependency issues

👉 Isliye GitLab ko Docker par run karte hain.

---

## 📦 Step 1: GitLab Official Docker Image Pull Karna

GitLab ki official image use hoti hai:

- `gitlab/gitlab-ce`
- CE = Community Edition

👉 Ye image **heavy hoti hai**
- Installation time: **5–10 minutes**
- Internet speed par depend karta hai

Command:
```bash
docker pull gitlab/gitlab-ce
````

---

## 🔍 Image Verify Karna

```bash
docker images
```

* GitLab image ka size kaafi bada dikhega
* Ye normal hai

---

## ▶ Step 2: GitLab Container Run Karna

GitLab container ko run karne ke liye:

```bash
docker run -p 8000:80 gitlab/gitlab-ce
```

### Explanation:

* `docker run` → container start
* `-p 8000:80`

  * 8000 → host (browser se access)
  * 80 → container ka default port
* `gitlab/gitlab-ce` → official image

👉 GitLab ab background me start ho raha hota hai.

---

## ⏳ Important Note (Patience Required)

* GitLab **immediately open nahi hota**
* First run me:

  * Configuration
  * Services startup
  * Database setup

👉 **5–10 minutes wait karna mandatory hai**

---

## 🌐 Step 3: GitLab Access Karna (Browser)

Browser me open karo:

```
http://localhost:8000/users/sign_in
```

### First time:

* Page load nahi hoga
* Thoda wait karna padega
* Auto reload hota rahega

👉 Jab GitLab ready hoga tab login page aayega.

---

## 🔐 Login Credentials Kaha Se Milenge?

❌ GitLab cloud wala account kaam nahi karega
✅ Ye **local GitLab server** hai

Default:

* Username: `root`
* Password: container ke andar stored hota hai

---

## 🧠 Step 4: Root Password Nikalna (Important)

### 1️⃣ New terminal open karo

(Old terminal close mat karna – container run ho raha hai)

### 2️⃣ Running containers dekho

```bash
docker ps -a
```

* Container ID copy karo

---

### 3️⃣ Container ke andar command run karo

```bash
docker exec -it <container_id> cat /etc/gitlab/initial_root_password
```

### Explanation:

* `docker exec -it` → container ke andar command
* `cat` → file ka content read
* File me **root password hota hai**

👉 Password copy kar lo

---

## 🔓 Step 5: GitLab Login

Login details:

* Username: `root`
* Password: jo file se mila

👉 Login successful hote hi **GitLab dashboard** open ho jaata hai.

---

## 🖥 GitLab UI (Local vs Cloud)

* UI bilkul **GitLab cloud jaisa hi hota hai**
* Koi difference nahi hota:

  * Projects
  * Groups
  * Repositories
  * Branches
  * Merge requests

👉 Matlab jo cloud par seekha tha, wahi yahan apply hota hai.

---

## 🚀 GitLab Me Kya-Kya Kar Sakte Ho?

* New projects create
* Code push / pull
* Branch create & merge
* Issues manage
* Users & groups
* **CI/CD pipelines** (next videos me)

👉 Sab kuch **without any limitation**

---

## 💡 Real-World Advantages

* DevOps practice ke liye best
* Interview preparation
* CI/CD testing
* Company-like GitLab environment
* No billing tension

---

## ⚠ Common Mistakes (Students Karte Hain)

❌ Container start hote hi browser open kar dete hain
❌ Installation slow hone par panic
❌ Old terminal close kar dete hain

✅ Solution:

* 5–10 min patiently wait karo
* Container running rehne do
* Password container se hi nikalo

---

## 📌 Interview Important Questions

### Q1: Self-hosted GitLab kya hota hai?

✔ GitLab jo hum apne server ya local system par run karte hain

### Q2: Docker par GitLab kyu install karte hain?

✔ Easy setup, no dependency issues, quick deployment

### Q3: Default GitLab username kya hota hai?

✔ `root`

### Q4: Root password kaha milta hai?

✔ `/etc/gitlab/initial_root_password` file me

---

## 🧾 One-Line Interview Answer

> Self-hosted GitLab ek locally hosted GitLab server hota hai jo hum Docker ke through bina kisi cloud limitation ke use kar sakte hain.

---

## 🔚 Final Summary

* GitLab cloud → limited
* Docker + GitLab → unlimited power
* Local server → full control
* DevOps learning ke liye must-know setup

---

## 🔜 Next Topics (Coming Up)

* GitLab CI/CD Pipelines
* `.gitlab-ci.yml`
* Runners (shared vs specific)
* GitLab + Docker integration

---
