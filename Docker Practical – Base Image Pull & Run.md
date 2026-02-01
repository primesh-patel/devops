# 🐳 Docker Practical – Base Image Pull & Run (Step-by-Step Notes)

## 📌 Introduction

Is video se **Docker ka practical phase start hota hai**.  
Ab tak humne Docker ke concepts theoretically cover kiye the, jaise:

- Docker Desktop
- Docker Hub
- Base Image / Parent Image
- Images vs Containers

👉 Ab isi knowledge ko **practically implement** kiya ja raha hai.

Is video ka focus hai:
- Base Image ko **pull (download)** karna  
- Aur us image ko **run karke container banana**

---

## 🎯 Is Video ke Objectives

Is lecture ke end tak aap samajh jaoge:

1. Docker Hub se image kaise pull hoti hai  
2. Docker Desktop me image kaise search karte hain  
3. Image run karte hi container kaise banta hai  
4. Container ka system se independent hona (proof ke saath)

---

## 🔄 Theory Recap (Short)

- **Docker Image** → Blueprint / Template  
- **Docker Container** → Image ka running instance  
- **Base Image** → Starting point for Docker Image  

👉 Ab hum **Node.js ki official base image** ka practical example dekhenge.

---

## 🔍 Step 1: Base Image Search Karna

Hum Node.js ki image use kar rahe hain.

Aap image search kar sakte ho:
- Docker Hub website se  
- Ya directly **Docker Desktop** ke through  

Is video me:
👉 **Docker Desktop** ka use kiya gaya hai.

### Search:
```

node

````

- Node ki **Docker Official Image** dikhegi  
- “Docker Official Image” ka label trust ko show karta hai  

---

## ⬇️ Step 2: Image Pull (Download) Karna

### Method 1: Docker Desktop UI
- Image ke saamne **Pull** button hota hai  
- Click karte hi image download ho jaati hai  

### Method 2: Docker CLI (Command Line)

```bash
docker pull node
````

👉 Is command ka matlab:

* Docker ko bolo: Node image Docker Hub se download karo

---

## ✅ Image Pull Hui Ya Nahi – Kaise Check Karein?

Docker Desktop me:

* **Images** tab par jao
* Wahan dikhega:

  * Image name (node)
  * Image ID
  * Tag (latest)
  * “5 days ago” type ka time

### ⚠️ Important Point:

> “5 days ago” image ke **last update ka time** batata hai,
> aapke download ka time nahi.

---

## 🧠 Docker ka Virtual Environment Concept

Docker Desktop me jo:

* RAM
* CPU
* Disk

dikhta hai,
👉 wo **aapke system ka actual hardware nahi**,
balki Docker ka **virtual environment** hota hai.

---

## ▶️ Step 3: Image Run Karna (Container Banana)

### Rule:

> **Image run hoti hai → Container banta hai**

---

### Method 1: Docker Desktop UI

* Image ke saamne **Run** button
* Click karte hi container start ho jaata hai
* Container **Containers** tab me dikhne lagta hai

---

### Method 2: Docker CLI (Most Important ⭐)

```bash
docker run -it node /bin/bash
```

### Is command ka breakdown:

* `docker run` → image ko run karo
* `-it` → interactive terminal provide karo
* `node` → kaunsi image run karni hai
* `/bin/bash` → container ke andar shell open karo

👉 Result:

* Node image ka ek **container** start ho jaata hai
* Aap container ke terminal ke andar aa jaate ho

---

## 🧪 Step 4: Container ke Andar Testing

Container ke terminal me command run karo:

```bash
node -v
```

Output:

* Node ka version show karega (example: v23.x.x)

---

## 🔁 System vs Container Comparison (Most Important Proof ⭐)

### System terminal me:

```bash
node -v
```

Example output:

```
v20.x.x
```

### Container terminal me:

```bash
node -v
```

Example output:

```
v23.x.x
```

---

## 💡 Key Observation

* Container ka Node version
  ❌ system ke Node version par depend nahi karta

👉 Ye proof karta hai:

> **Docker Containers are completely isolated & independent**

---

## 🧱 Concept Clear Ho Gaya

* Docker Hub se image pull hoti hai
* Image run karte hi container banta hai
* Container ka apna environment hota hai
* System aur container ke versions alag ho sakte hain

---

## 📌 Final Summary (Interview + Practical)

* `docker pull` → image download karta hai
* `docker run` → image ko run karke container banata hai
* Container system se independent hota hai
* Same image → multiple containers possible

---

## 🚀 What’s Next?

Next videos me:

* Dockerfile
* Custom image build
* Real application containers
* Multi-container apps

🎯 **Ab Docker ka real game start ho chuka hai**

```
```
