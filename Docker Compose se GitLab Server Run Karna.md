# 🐳 Docker Compose se GitLab Server Run Karna (Practical Notes)

## 🎯 Video ka Objective

Is video me hum seekhte hain:

- Docker Compose ka practical use
- GitLab server ko Docker Compose se run karna
- YAML file me configuration kaise likhte hain
- GitLab root password automatically set kaise karte hain
- YAML me `|` (pipe symbol) ka use
- Docker Compose se complex commands ko simplify kaise karte hain
- End me ek important concept: **Volume ka need** (Data persistence)

---

## 🔥 Docker Compose ka Real Use Kyu Hota Hai?

Docker Compose ka main purpose hota hai:

✅ **Badi-badi Docker commands ko short aur manageable banana**

Aap manually Docker me ye sab karte ho:

- image pull karna
- container run karna
- ports map karna
- environment variables set karna
- multiple services manage karna

But ye sab kaafi **lambi commands** ban jaati hain.

### Example (Last video GitLab setup)
Last video me GitLab server run karne ke liye:

- GitLab image pull command
- GitLab run command (port mapping ke sath)
- Root password extract karne ki command

Ye sab manually karna padta tha.

---

## ✅ Docker Compose Kya Karta Hai?

Docker Compose ka concept:

- Aap ek file banate ho: `docker-compose.yml`
- Us file me saari configuration define kar dete ho
- Aur sirf ek command se sab run ho jaata hai:

```bash
docker compose up
````

👉 Compose file automatically:

* image download karega (agar local me nahi hai)
* container create karega
* port mapping karega
* environment variables apply karega

---

## 📁 Step 1: Project Folder Banana

Instructor ne ek folder banaya:

📌 `demo`

Aur us folder ko VS Code me open kiya.

---

## 📄 Step 2: Compose File Banana

File ka naam kuch bhi rakh sakte ho, but best practice:

✅ `docker-compose.yml`

Instructor ne file ka naam diya:

* `docker-compose.yml`

### YAML Extension

YAML file ka extension hota hai:

* `.yml`
* `.yaml`

---

## 🧠 YAML Kya Hota Hai?

YAML ka full form:

**YAML = Yet Another Markup Language**

### YAML ki speciality

* Human readable format
* Curly brackets `{}` nahi hote
* Indentation (spaces) bahut important hoti hai

📌 YAML me indentation galat hui to file kaam nahi karegi.

---

## 🧾 Step 3: Docker Compose Version Define Karna

Compose file me first line:

```yml
version: "3.8"
```

### Explanation

* Docker compose ka version define karta hai
* Latest commonly used version: **3.8**

---

## 🛠 Step 4: Services Define Karna

Docker Compose me "services" ka matlab hota hai:

* Aap ek file me multiple containers define kar sakte ho.

```yml
services:
```

---

## 🦊 Step 5: GitLab Service Define Karna

Service ka naam kuch bhi rakh sakte ho.

Instructor ne rakha:

```yml
gitlab_server:
```

📌 Ye sirf ek label hai.
Actual container ka naam alag define hota hai.

---

## 📦 Step 6: GitLab Image Define Karna

GitLab official image:

```yml
image: gitlab/gitlab-ce
```

### Explanation

* `gitlab` = DockerHub ka official namespace/user
* `gitlab-ce` = GitLab Community Edition image

---

## ⚡ Important Point (Image Pull Automatic)

Agar image local system me already installed nahi hai:

👉 Docker Compose automatically DockerHub se pull kar lega.

Means:

* manual `docker pull` karne ki need nahi.

---

## 🏷 Step 7: Container Name Define Karna

Container ka name set karne ke liye:

```yml
container_name: my_gitlab_server
```

### Benefit

* Container ko identify karna easy ho jaata hai
* `docker ps` me clear name dikhai deta hai

---

## 🌐 Step 8: Port Mapping Define Karna

Ports define karte hain:

```yml
ports:
  - "8000:80"
```

### Explanation

* `8000` = Host machine port (browser me access)
* `80` = Container ka default GitLab port

So GitLab browser me open hoga:

```
http://localhost:8000
```

---

## 🌱 Step 9: Environment Variables Define Karna

GitLab ko configure karne ke liye environment section use hota hai:

```yml
environment:
```

Instructor ne variable use kiya:

```yml
GITLAB_OMNIBUS_CONFIG: |
```

---

## 🧠 GITLAB_OMNIBUS_CONFIG Kya Hai?

GitLab ka ek special environment variable:

✅ `GITLAB_OMNIBUS_CONFIG`

Iska use hota hai:

* GitLab configuration set karne ke liye
* root password define karne ke liye
* internal settings modify karne ke liye

---

## 📌 YAML Pipe Symbol `|` (Interview Important)

```yml
GITLAB_OMNIBUS_CONFIG: |
```

### Pipe `|` ka meaning

Pipe symbol YAML me use hota hai jab:

✅ multi-line string likhni ho

Agar aapko ek line se zyada text likhna ho to pipe symbol lagate hain.

📌 Interview question ban sakta hai:

**Q: YAML me `|` ka use kya hota hai?**
✔ Answer: Multi-line string define karne ke liye.

---

## 🔐 Step 10: Root Password Set Karna (Auto)

Compose file me root password define kiya:

```yml
gitlab_rails['initial_root_password'] = "StrongPasswordHere"
```

### Explanation

* GitLab me default username hota hai: `root`
* Password normally extract karna padta hai file se
* But yaha hum password pehle hi set kar rahe hain

📌 Password length minimum:

* 14-15 characters recommended

Password me include karna chahiye:

* Capital letters
* Small letters
* Numbers
* Special characters

Example:
`F@Farzan#123456789A`

---

## ⚙ Step 11: Puma Worker Process Disable Karna

Instructor ne ek extra line add ki:

```yml
puma['worker_processes'] = 0
```

### Puma kya hota hai?

GitLab internally **Puma web server** use karta hai.

Puma multi-worker / cluster mode me run karta hai.

### Worker_processes = 0 ka meaning

* Multi worker clustering disable
* Simple setup (low resources)
* Local practice ke liye best

📌 Reason:
Instructor heavy load handle nahi kar raha,
sirf local GitLab practice kar raha hai.

---

## ✅ Full Compose File (Final Format)

```yml
version: "3.8"

services:
  gitlab_server:
    image: gitlab/gitlab-ce
    container_name: my_gitlab_server
    ports:
      - "8000:80"
    environment:
      GITLAB_OMNIBUS_CONFIG: |
        gitlab_rails['initial_root_password'] = "F@Farzan#123456789A"
        puma['worker_processes'] = 0
```

---

## 🚀 Step 12: GitLab Run Karna using Docker Compose

Ab sirf ek command:

```bash
docker compose up
```

### Explanation

Ye command automatically:

* image pull karega (agar missing hai)
* container create karega
* ports configure karega
* password apply karega
* GitLab server run karega

---

## ⏳ Wait Time (Very Important)

GitLab heavy software hai.

First time start hone me lagta hai:

🕐 5 to 10 minutes

Instructor ne bola:

* hacking wali feeling aayegi 😄

---

## 🌐 Step 13: GitLab Access Karna Browser me

Port mapping host machine ka 8000 tha.

So open karo:

```
http://localhost:8000
```

---

## 🔑 Login Details

Username:

```
root
```

Password:

* Jo compose file me define kiya tha

---

## 🏗 GitLab me Repository Create Karna

GitLab open hone ke baad:

* "Create Project" pe click
* "Create Blank Project"
* Project name do (example: farzan)
* Owner: root
* Visibility: public/private
* Create project

Repository create ho jaati hai successfully.

---

## ⚠ Main Issue (Important Concept)

Yaha ek problem aati hai:

### ❌ Data Persistence Issue

Abhi tak hum volumes use nahi kar rahe.

So agar container stop ho gaya ya delete ho gaya:

* repositories
* projects
* configurations
* data

sab kuch LOST ho jaayega.

📌 Docker ka rule:
Container delete = container ke andar ka data delete.

---

## 💾 Solution: Docker Volumes (Next Video Topic)

Data ko safe rakhne ke liye:

✅ Docker Volumes use karna mandatory hai

Volumes ka benefit:

* Container delete ho jaaye tab bhi data safe rahega
* GitLab projects permanently store ho jaayenge

Instructor ne bola:
👉 Next video me volumes add karenge docker-compose file me.

---

## 📌 Interview Important Points

### Q1: Docker Compose kyu use karte hain?

✔ Multiple commands ko ek YAML file me define karke easily run karne ke liye.

### Q2: YAML me indentation important kyu hai?

✔ YAML indentation-based language hai, indentation galat hui to config break ho jaati hai.

### Q3: Docker Compose image pull kab karta hai?

✔ Jab local system me image available nahi hoti.

### Q4: `GITLAB_OMNIBUS_CONFIG` ka use kya hai?

✔ GitLab configuration define karne ke liye (password, settings, etc.)

### Q5: YAML me `|` pipe symbol ka use?

✔ Multi-line strings define karne ke liye.

### Q6: `puma['worker_processes']=0` ka matlab?

✔ Puma web server ka cluster/worker mode disable karna, low resource setup ke liye.

### Q7: Container stop karne ke baad data kyu lost hota hai?

✔ Container ka data ephemeral hota hai. Persistent storage ke liye volumes chahiye.

---

## 🔥 Summary (One Shot Revision)

* Docker Compose complex Docker setup ko easy banata hai
* `docker-compose.yml` file me:

  * image
  * container name
  * ports
  * environment variables
  * password config
  * puma settings
    define ki jaati hai
* Command sirf ek:

  ```bash
  docker compose up
  ```
* GitLab heavy hai → 5-10 min wait
* Login: root + password (jo YAML me set)
* Problem: volumes nahi lagaye → data loss hoga
* Next topic: volumes add karna

---
