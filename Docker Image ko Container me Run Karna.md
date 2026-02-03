# ▶️ Docker Image ko Container me Run Karna (Port Mapping ke saath)

## 🔁 Recap (Previous Video)

Pichhli video me humne:
- Node.js + Express project banaya
- Dockerfile likhi
- Dockerfile ka use karke **custom Docker image (`my-app`) build** ki

Ab:
- Docker Desktop → Images section me **my-app image dikh rahi hai**
- Lekin image se **abhi tak container run nahi kiya**

👉 Is video ka focus:
> **Docker image ko run karke container banana aur application ko browser me access karna**

---

## 🎯 Is Video ke Objectives

Is video me hum seekhenge:
- Docker image ko container me kaise run karein
- Docker Desktop se container run karna
- Port mapping ka concept
- Random port vs fixed port
- Container start / stop / delete

---

## 📦 Docker Image kaha dikh rahi hoti hai?

Docker Desktop → **Images tab**

Yahan:
- `my-app` image listed hoti hai
- Ye image Dockerfile se build hui hoti hai

⚠️ Note:
> Docker image kabhi project folder me file ki tarah nahi dikhti  
> Wo Docker ke internal storage me hoti hai

---

## ▶️ Step 1: Docker Image Run Karna

Docker Desktop me:
- `my-app` image ke saamne **Run** button hota hai
- Run pe click karte hi container banne lagta hai

---

## ⚠️ Important Concept: Port Mapping

Agar hum image ko **direct run** kar den:
- App sirf **container ke andar** chalegi
- Browser se access nahi hogi

👉 Kyun?
> Kyunki **host machine ka port** container ke port se connect nahi hua

---

## 🔌 Container Port vs Host Port

- **Container Port** → App ke andar ka port (jaise `4000`)
- **Host Port** → Laptop / system ka port

Dono ko connect karna zaroori hota hai

---

## 🧾 Step 2: Optional Settings (Docker Desktop)

Run karte waqt:
- **Container Name** → e.g. `my-container`
- **Port Mapping**:
  - Container Port: `4000`
  - Host Port:
    - Same `4000` (recommended)
    - ya `0` (random port)

---

## 🔢 Fixed Port (Recommended)

Agar app me:
```js
app.listen(4000)
````

To Docker Desktop me bhi:

```
4000 : 4000
```

✔ Easy
✔ No confusion
✔ Interview friendly

---

## 🎲 Random Port (Advanced Use Case)

Agar host port me:

```
0
```

Likho, to Docker:

* Automatically random free port assign karega
* Useful jab **multiple containers** ek saath chal rahe ho

Example:

```
32768 → 4000
```

---

## ▶️ Step 3: Container Run Karna

* Port set karne ke baad **Run** button click karo
* Container start ho jaata hai

Docker Desktop → Containers tab me:

* Status: **Running**
* Logs me dikhega:

```
App is running on port 4000
```

---

## 🌐 Step 4: Application Access Karna

Docker Desktop:

* Container ke saamne **Open in browser / link** milta hai

Browser me:

```
http://localhost:4000
```

ya

```
http://localhost:<random-port>
```

✔ API response aata hai
✔ Matlab app container ke andar perfectly run ho rahi hai

---

## 🧠 Important Observation

* System me Node.js manually run nahi ho raha
* Sirf Docker chal raha hai
* App **pure container ke andar isolated** hai

👉 Ye Docker ka **biggest benefit** hai

---

## ⏹ Step 5: Container Stop Karna

Docker Desktop:

* Container ke saamne **Stop** button

Stop ke baad:

* Browser refresh karo → kuch bhi load nahi hoga

✔ Proof: App band ho chuki hai

---

## 🗑 Step 6: Container Delete Karna

* Container stop karo
* **Delete** button click karo

⚠️ Note:

> Container delete karne se **image delete nahi hoti**

Image abhi bhi Images tab me available hoti hai

---

## 🔁 Step 7: Image ko Dobara Run Karna

* Same image ko dobara run karo
* Naya container create hoga
* Naya container name + port mil sakta hai

---

## 🔑 Fixed Port vs Random Port (Comparison)

| Fixed Port             | Random Port         |
| ---------------------- | ------------------- |
| Easy to remember       | Auto-managed        |
| Beginners ke liye best | Multi-container use |
| `localhost:4000`       | `localhost:32768`   |

---

## 🎯 Interview Ready Lines

* Docker image ko run karne par container banta hai
* Container ek isolated environment hota hai
* Port mapping se container app ko host system se expose kiya jaata hai
* Docker Desktop GUI se container start, stop aur delete kar sakte hain

---

## 📌 Final Summary

* Dockerfile → Image banati hai
* Image run → Container banta hai
* Port mapping → Browser access deta hai
* Container stop/delete → App band

---

## 🚀 What’s Next?

Aane wali videos me:

* `docker run -p` via CLI
* `.dockerignore`
* Production-ready Dockerfile
* Python / React apps Dockerize karna
* Docker Compose

---

✅ **Yahin se Docker ka real practical use start hota hai**
Agar chaho to next main:

* CLI way samjhaun
* isi ka Python version banaun
* ya short interview notes nikaal doon

Bas bolo 👍🔥
