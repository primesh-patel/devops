# 🐳 Docker Image Versions (Tags) – Complete & Descriptive Notes

## 🎯 Video ka Objective

Is video me hum seekhte hain:
- Docker images ke **multiple versions** kaise create hote hain
- Docker images ke **versions (tags)** kaise manage kiye jaate hain
- Ek hi project ke **multiple versions ko parallel run** kaise kar sakte hain
- Docker images se related **most important interview question**

👉 Ye topic **real production + interviews dono ke liye critical** hai.

---

## 🔁 Recap (Previous Knowledge)

Ab tak hum:
- Node.js application bana chuke hain
- Dockerfile likh chuke hain
- `.dockerignore` samajh chuke hain
- Docker image build kar chuke hain
- Image ko container me run karke test bhi kar chuke hain

Ab next logical step:
> **Same Docker image ke multiple versions kaise banaye aur manage karein**

---

## 🤔 Version Ka Matlab Kya Hota Hai?

Version ka matlab hota hai:
- Project ka **updated state**
- New feature
- Bug fix
- Performance improvement

### Real-life Example:
- React 18 → React 19
- Angular 16 → Angular 17

➡️ Naam same rehta hai  
➡️ Sirf **version change hota hai**

---

## 🧠 Same Concept in Docker Images

Docker me:
- Image ka **name same rehta hai**
- Uske aage **versions (tags)** lagte hain

Example:
```text
my-node-app:latest
my-node-app:v1
my-node-app:v2
````

👉 Ye **same project** ki different states hoti hain

---

## 🧹 Important Command (Cleanup)

### Docker System Prune

```bash
docker system prune -a
```

### Ye command kya karti hai?

* Stopped containers delete
* Unused images delete
* Cache clear
* System clean

⚠️ **Warning:**
Ye command powerful hai, production me carefully use karein.

---

## 🏗 First Docker Image Build (Version 1)

```bash
docker build -t my-node-app .
```

### Explanation:

* `docker build` → Image create karta hai
* `-t` → Image ka naam dena
* `my-node-app` → Image name
* `.` → Current directory (Dockerfile yahin hai)

### Result:

* Docker image create ho jaati hai
* Tag default hota hai: `latest`

---

## ▶ Running Version 1 Image

* Docker Desktop → Run
* Container name: `node`
* Host Port: `4000`
* Container Port: `4000`

✔ App successfully run ho jaati hai
✔ API browser me accessible hoti hai

---

## 🔄 Project Update (New Feature / Bug Fix)

Example update:

* Ek naya employee record add kar diya
* Code change kiya
* File save kar di

👉 Ab project **update ho chuka hai**

---

## ❓ MOST IMPORTANT INTERVIEW QUESTION

**Question:**
Agar project me update aaye, to:

* New image **new name se banayein?**
* Ya **same image ka new version banayein?**

### ✅ Correct Answer (Best Practice)

👉 **Same image name, different versions (tags)**

❌ Alag-alag image names banana
✔ Versioning use karna

---

## 🧠 Reason (Interview Explanation)

Jaise:

* React ka naam React hi rehta hai
* Sirf versions change hote hain (18, 19)

Same:

* Docker image ka naam same
* Version tag update

Agar har update pe naya naam:

* 10 updates → 10 image names
* Management nightmare ❌

---

## 🏷 Creating Version 2 Docker Image

```bash
docker build -t my-node-app:v2 .
```

### Explanation:

* Same image name: `my-node-app`
* New version tag: `v2`
* Latest code ke saath new image create

---

## 📦 Image List Check

```bash
docker images
```

Output:

```text
my-node-app   latest
my-node-app   v2
```

👉 Same project
👉 Multiple versions available

---

## ▶ Running Multiple Versions Together

### Version 1:

* Port: `4000`

### Version 2:

* Port: Random (`0`) or different port

Docker Desktop automatically:

* Random host port assign karta hai
* Dono versions parallel run hote hain

---

## 🌐 Result

* Version 1 → Old features
* Version 2 → New updated features

✔ Dono apps simultaneously accessible
✔ Zero downtime possible
✔ Easy rollback possible

---

## 🚀 Production Advantage

* New version test kar sakte ho
* Old version users ke liye live rehta hai
* Agar bug aaye → rollback easily

---

## 🧠 Key Interview Points (Must Remember)

* Docker image versions = **tags**
* Same image name, different versions
* `latest` default tag hota hai
* Production me versioning mandatory hoti hai
* Parallel containers possible

---

## 📌 Best Practices Summary

✔ Image name same rakho
✔ Versions (tags) use karo
✔ Ports properly manage karo
✔ Old versions delete mat karo immediately
✔ Rollback ready rakho

---

## 🧠 One-Line Interview Answer

> Docker images ke multiple versions ko hum **tags** ke through manage karte hain, jisme image ka naam same rehta hai aur version change hota rehta hai.

---

## 🔚 Final Conclusion

Docker image versioning:

* Clean
* Professional
* Scalable
* Production-ready approach

---

## 🔜 What’s Next?

Aane wali videos me:

* Docker image push to Docker Hub
* Tagging strategies
* Production deployment
* Docker Compose

---

Agar chaho to main:

* **Is topic ka short interview PDF**
* **Real production versioning strategy**
* **Python project ke liye same concept**

bhi bana deta hoon 🔥
Bas bolo 👍
