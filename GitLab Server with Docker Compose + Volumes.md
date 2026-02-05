# 🐳 GitLab Server with Docker Compose + Volumes (Persistent Storage Notes)

## 🎯 Video ka Main Goal

Is video ka purpose hai:

✅ GitLab server ka data loss problem solve karna  
✅ Docker volumes use karke GitLab ka data permanent store karna  
✅ Docker Compose file me volumes ka configuration add karna  
✅ GitLab container stop/restart ke baad bhi repositories safe rakhna  

---

## 🧨 Previous Video Problem (Data Loss Issue)

Pichle video me humne:

- Docker Compose se GitLab server run kiya tha

But problem ye thi:

📌 **Jaise hi container stop hota tha, GitLab ka data delete ho jaata tha**

Example:
- Projects create kiye
- Repositories banayi
- Next day container stop karke restart kiya

➡️ **Projects show nahi hue**
➡️ **Data completely lost**

### Reason (Docker ka default behavior)

Docker containers by default:

- temporary storage use karte hain
- container stop/remove hone ke baad data erase ho jaata hai

---

## ✅ Solution: Docker Volumes

Data ko permanent banane ke liye:

🔥 Docker Volumes ka use karna zaroori hai.

### Docker Volume ka benefit

Docker volume ka use karne se:

✅ container stop/delete hone ke baad bhi data safe rahega  
✅ GitLab projects/repositories permanently store rahenge  
✅ logs aur config bhi preserve rahenge  

---

## 🛑 Container Stop Karne ke 2 Ways

### Method 1: Ctrl + C
Agar terminal me container run ho raha hai:

```bash
Ctrl + C
➡️ Container stop ho jaata hai.

Method 2: docker compose down
docker compose down
➡️ Container stop + remove ho jaata hai.

📌 Ye command container ko delete bhi kar sakti hai
(aur data loss wahi hota hai agar volumes nahi lage).

🧾 Docker Desktop me Check
Container stop hone ke baad:

Docker Desktop me container show nahi hota

Image still available hoti hai (GitLab CE image)

📌 Main Work: Compose File me Volumes Add Karna
Ab hum docker-compose.yml file me ek new section add karte hain:

volumes:
Volumes ka use hum GitLab ke 3 major parts store karne ke liye karte hain:

Config

Logs

Data (most important)

🧠 GitLab ke Data Parts (Important)
GitLab container ke andar 3 important directories hoti hain:

1️⃣ Config Directory
GitLab ka configuration store hota hai:

📌 Container path:

/etc/gitlab
2️⃣ Logs Directory
GitLab logs store hote hain:

📌 Container path:

/var/log/gitlab
3️⃣ Data Directory (Most Important)
Repositories, projects, database, uploads etc store hote hain:

📌 Container path:

/var/opt/gitlab
🧾 Volume Mapping ka Concept
Volume mapping ka format:

host_path : container_path
Host path matlab:

aapke system ka folder

Container path matlab:

container ke andar ka folder

🏗 Compose File me Volumes Add Karna
Instructor ne compose file me volumes section add kiya:

volumes:
  - ./gitlab/config:/etc/gitlab
  - ./gitlab/logs:/var/log/gitlab
  - ./gitlab/data:/var/opt/gitlab
Explanation
✅ Config Volume
- ./gitlab/config:/etc/gitlab
Host system me folder:

./gitlab/config

Container ke andar folder:

/etc/gitlab

➡️ GitLab configuration now permanent store hoga.

✅ Logs Volume
- ./gitlab/logs:/var/log/gitlab
Host system me folder:

./gitlab/logs

Container ke andar folder:

/var/log/gitlab

➡️ GitLab logs now permanent store honge.

✅ Data Volume (Most Important)
- ./gitlab/data:/var/opt/gitlab
Host system me folder:

./gitlab/data

Container ke andar folder:

/var/opt/gitlab

➡️ Projects, repositories, database, uploads sab safe rahenge.

📌 Real Meaning of ./gitlab/...
./ ka matlab hota hai:

👉 Current directory (jis folder me docker-compose.yml file hai)

So GitLab ke folders automatically yahi create ho jaayenge:

demo/
 ├── docker-compose.yml
 └── gitlab/
      ├── config/
      ├── logs/
      └── data/
💾 Auto Folder Creation
Jaise hi command run hoti hai:

docker compose up
Docker automatically folders create kar deta hai:

config

logs

data

🚀 GitLab Server Run Command
Volume add karne ke baad:

docker compose up
What happens now?
Docker Compose automatically:

✅ GitLab image pull karega (agar missing hai)
✅ container run karega
✅ ports map karega
✅ volumes mount karega
✅ GitLab ka data host machine pe save karega

⏳ Startup Time
GitLab heavy application hai.

First time run me:

🕐 5 to 10 minutes lagte hain.

Instructor ne bola:
"ab hacker wali feeling lo" 😄

🌐 GitLab Access
Browser me open karo:

http://localhost:8000
🔑 Login Credentials
Username:

root
Password:

jo compose file me set kiya tha (previous video wali setting)

🏗 Testing: Project Create Karke Verify Karna
Instructor ne test ke liye:

Create Project

Create Blank Project

Project name: Farzin

Owner: root

Repository: Public

Create project

➡️ Project successfully create ho gaya.

🧠 Main Proof (Volumes ka Power)
Ab agar container stop bhi ho jaaye:

docker compose down
aur phir wapas start kare:

docker compose up
➡️ Project delete nahi hoga
➡️ Repositories wapas show hongi
➡️ Data persistent rahega

Because now data container ke andar nahi,
host system ke folder me store ho raha hai.

🔥 Docker Compose + Docker Volumes ka Combined Benefit
Docker Compose se kya benefit mila?
✅ complex commands remove ho gayi
✅ one command me sab run ho gaya
✅ easy management of services

Docker Volumes se kya benefit mila?
✅ GitLab projects safe
✅ GitLab repositories safe
✅ Logs safe
✅ Config safe
✅ Container stop/restart ke baad bhi data safe

📌 Interview Important Questions
Q1: Container stop karne par data loss kyu hota hai?
✔ Because container storage ephemeral hota hai (temporary).

Q2: Data permanent kaise banate hain Docker me?
✔ Docker volumes use karke.

Q3: Docker Compose me volumes kaise define karte hain?
✔ volumes: section me host path aur container path mapping karke.

Example:

- ./gitlab/data:/var/opt/gitlab
Q4: GitLab data directory kaun si hoti hai?
✔ /var/opt/gitlab

Q5: GitLab config directory kaun si hoti hai?
✔ /etc/gitlab

Q6: GitLab logs directory kaun si hoti hai?
✔ /var/log/gitlab

Q7: docker compose down kya karta hai?
✔ Container stop + remove kar deta hai.

🧾 Final Compose File (Full Working Example)
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
    volumes:
      - ./gitlab/config:/etc/gitlab
      - ./gitlab/logs:/var/log/gitlab
      - ./gitlab/data:/var/opt/gitlab
🔁 Important Commands Summary
Start GitLab Server
docker compose up
Stop and Remove Container
docker compose down
Run in Background (Optional)
docker compose up -d
🏁 Conclusion
Without volumes → data lost

With volumes → data safe

GitLab server ko docker compose ke through run karna best practice hai

Volumes mandatory hain production level GitLab setup me

