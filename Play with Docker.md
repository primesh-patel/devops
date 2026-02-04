# 🐳 Play with Docker – Complete Notes (Live Docker Without Local Setup)

## 🎯 Video ka Objective

Is video me hum samajhte hain:

- Play with Docker kya hota hai
- Local setup ke bina Docker image kaise run karte hain
- Docker Hub + Play with Docker ka use
- Platform-specific image kyu banani padti hai
- Live testing ka real-world use case

👉 Ye topic **Docker learning + interviews dono ke liye important** hai.

---

## ❓ Play with Docker Kya Hai?

Play with Docker (PWD) ek **online platform** hai jahan:

- Aap **Docker images ko live run** kar sakte ho
- **Local system me Docker install karne ki zarurat nahi**
- Sirf **limited time (4 hours)** ke liye environment milta hai
- Real server jaisa experience milta hai

👉 Simple words me:
> Play with Docker = Free temporary Docker server (browser ke through)

---

## 🔥 Play with Docker Ka Main Purpose

- Docker image ko **test karna**
- Demo ya practice karna
- Interview ya learning ke time **quick testing**
- Jab local system heavy ya restricted ho

---

## ⚠ Important Limitation

- Environment **sirf 4 hours** ke liye hota hai
- Time over hone ke baad:
  - Containers
  - Images
  - Instances  
  👉 Sab delete ho jaate hain

---

## 📦 Play with Docker Ke Liye Kya Required Hai?

1. Docker image (Dockerfile se bani hui)
2. Image Docker Hub par **uploaded honi chahiye**
3. Image **Linux platform compatible** honi chahiye

---

## 🧠 Platform Compatibility Kyun Zaroori Hai?

Play with Docker ka environment:
- **Linux OS**
- Specific CPU architecture

Isliye image banate waqt platform specify karna padta hai.

---

## 🛠 Docker Image Build for Play with Docker

Normal build ke bajay yahan `buildx` use hota hai:

```bash
docker buildx build --platform linux/amd64 -t username/repo-name .
````

### Explanation:

* `buildx` → multi-platform image build ke liye
* `--platform linux/amd64` → Linux server compatible image
* `-t` → image name
* `.` → current directory

---

## 🐳 Docker Hub Par Repository Create Karna

Steps:

1. Docker Hub me login
2. Repositories → Create Repository
3. Repository name (example: `my-node`)
4. Visibility:

   * Public (recommended)
5. Create button click

👉 Image name format:

```
username/repository-name
```

---

## 🚀 Docker Image Push Karna (Upload)

```bash
docker push username/repository-name
```

Push hone ke baad:

* Image Docker Hub par visible
* OS → Linux
* Architecture → wahi jo platform diya tha

---

## 🌍 Play with Docker Access Karna

Steps:

1. Google me search:

   ```
   Play with Docker
   ```
2. Official website open karo
3. Docker Hub account se **Sign In**
4. **Start** button par click

---

## ⏱ Session Duration

* Timer start hota hai
* Total time = **4 hours**
* Timer screen par visible hota hai

---

## 🧩 New Instance Create Karna

* **Add New Instance** par click
* Ek Linux terminal open ho jaata hai
* Docker already installed hota hai

Check:

```bash
docker -v
```

---

## ⬇ Docker Image Pull Karna (PWD Server Par)

```bash
docker pull username/repository-name
```

Check:

```bash
docker images
```

---

## ▶ Docker Container Run Karna

```bash
docker run -p 4000:4000 username/repository-name
```

### Explanation:

* `-p` → port mapping
* 4000 → app port
* image name → Docker Hub wali image

---

## 🌐 Application Live Karna

Steps:

1. Container run hone ke baad
2. **Open Port** option dikhega
3. Port number likho (example: 4000)
4. PWD ek **public URL generate karta hai**

Example:

```
https://xxxx.play-with-docker.com
```

👉 Ab app **live ho chuki hoti hai**

---

## ✅ Output Verification

* Browser me URL open karo
* Application successfully run hoti dikhegi
* Same jaise localhost par hoti hai

---

## 💡 Real-World Use Cases

* Interview demo
* Client ko live app dikhana
* Docker practice without installation
* Lightweight testing environment

---

## 📌 Interview Important Points

* Play with Docker = online Docker playground
* No local setup required
* Time-limited environment
* Linux-based server
* Docker Hub images required

---

## ❓ Interview Questions & Answers

### Q1: Play with Docker kya hota hai?

✔ Online platform jahan Docker images ko temporary server par run kar sakte hain

### Q2: Kitne time ke liye environment milta hai?

✔ 4 hours

### Q3: Play with Docker me kaunsa OS hota hai?

✔ Linux

### Q4: Image ko Docker Hub par push karna kyun zaroori hai?

✔ Kyunki Play with Docker images Docker Hub se pull karta hai

---

## 📝 One-Line Interview Answer

> Play with Docker ek online platform hai jahan hum bina local setup Docker images ko limited time ke liye live run kar sakte hain.

---

## 🔚 Final Summary

* Play with Docker = temporary Docker server
* Docker Hub + PWD powerful combination
* Learning & testing ke liye best
* Production ke liye nahi, testing/demo ke liye

---

## 🔜 Next Topics Suggestions

* Play with Docker + Docker Compose
* Multi-container app testing
* Kubernetes playgrounds
* CI/CD demo using Play with Docker

---
