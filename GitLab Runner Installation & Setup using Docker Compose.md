# 🦊 GitLab Runner Installation & Setup using Docker Compose (Complete Notes)

## 🎯 Video Goal (Objective)

Is video me hum seekhenge:

✅ GitLab Runner ka complete setup  
✅ GitLab Runner ko GitLab Server ke sath register karna  
✅ Docker Compose file me GitLab Runner service add karna  
✅ Runner ko online status me lana  

📌 Reason:
Aage CI/CD pipelines run karne ke liye GitLab Runner compulsory hota hai.

---

# 🔥 Recap (Previous Videos)

Pichle videos me humne:

- GitLab Server ko Docker me run kiya
- Docker Compose use kiya
- Docker Volumes use kiya (data persist karne ke liye)

Ab next step:

➡️ GitLab Runner install + configure karna.

---

# ⭐ GitLab Runner Setup ka Concept

GitLab Runner ek agent hota hai jo:

- GitLab Server se jobs leta hai
- CI/CD pipelines execute karta hai

📌 Important:
GitLab Server khud jobs run nahi karta.
Runner jobs execute karta hai.

---

# 🛠 Docker Compose File me Changes (GitLab Server service)

## ✅ 2 New Properties add ki gayi GitLab Server service me:

### 1️⃣ hostname

```yaml
hostname: my-gitlab-server
````

📌 Use:
GitLab container ko ek fixed hostname mil jaata hai.

👉 Mostly yahi hostname runner registration time pe use hota hai.

---

### 2️⃣ restart: always

```yaml
restart: always
```

📌 Meaning:
Agar container crash ho jaye ya system restart ho jaye,
to container automatically restart ho jayega.

👉 Best practice for production-like setup.

---

# 🧩 New Service Add: GitLab Runner

Ab hum Docker Compose me ek nayi service create karte hain:

✅ `gitlab-runner`

---

# 📌 GitLab Runner Service Configuration

## 1️⃣ Service Name

```yaml
gitlab-runner:
```

Service name kuch bhi ho sakta hai, but meaningful rakhna best hota hai.

---

## 2️⃣ Image (GitLab Runner Official Image)

```yaml
image: gitlab/gitlab-runner:latest
```

📌 Meaning:
Ye Docker Hub se GitLab Runner ki official image pull karega.

---

## 3️⃣ Container Name

```yaml
container_name: my-gitlab-runner
```

📌 Benefit:
Container ka fixed naam set ho jata hai.

---

## 4️⃣ restart policy

```yaml
restart: always
```

📌 Meaning:
Runner automatically restart hota rahega if stopped unexpectedly.

---

## 5️⃣ depends_on

```yaml
depends_on:
  - gitlab-server
```

📌 Meaning:
GitLab Runner tabhi start hoga jab GitLab Server start ho chuka ho.

👉 Because runner ka kaam GitLab server se connect hona hota hai.

---

# 🗂 GitLab Runner ke Volumes

Runner ki settings save karne ke liye volume use hota hai.

```yaml
volumes:
  - ./gitlab-runner:/etc/gitlab-runner
```

📌 Meaning:
Runner ki config files container delete/stop hone ke baad bhi safe rahegi.

---

# 🔥 Docker Socket Mount (Most Important)

```yaml
- /var/run/docker.sock:/var/run/docker.sock
```

📌 Why required?

GitLab Runner ko Docker commands execute karni hoti hain
(jaise build image, run container, test container, etc.)

Docker socket mount karne ka matlab:

> Runner host machine ke Docker daemon ko access kar sakta hai.

👉 Isse runner easily Docker executor use kar paata hai.

---

# 🔐 privileged: true (Very Important)

```yaml
privileged: true
```

📌 Meaning:
Runner ko extra permissions milti hain.

📌 Why required?
Taaki runner Docker containers ko properly run kar sake.

👉 Without this, pipelines me Docker build/run errors aa sakte hain.

---

# ✅ Final docker-compose.yml (GitLab Server + Runner)

Example structure:

```yaml
version: "3.8"

services:
  gitlab-server:
    image: gitlab/gitlab-ce:latest
    container_name: my-gitlab-server
    hostname: my-gitlab-server
    restart: always
    ports:
      - "8000:80"
    environment:
      GITLAB_OMNIBUS_CONFIG: |
        gitlab_rails['initial_root_password'] = "StrongPassword@123456"
        puma['worker_processes'] = 0
    volumes:
      - ./gitlab/config:/etc/gitlab
      - ./gitlab/logs:/var/log/gitlab
      - ./gitlab/data:/var/opt/gitlab

  gitlab-runner:
    image: gitlab/gitlab-runner:latest
    container_name: my-gitlab-runner
    restart: always
    depends_on:
      - gitlab-server
    volumes:
      - ./gitlab-runner:/etc/gitlab-runner
      - /var/run/docker.sock:/var/run/docker.sock
    privileged: true
```

---

# 🚀 Docker Compose Run Command

GitLab Server + Runner start karne ke liye command:

```bash
docker compose up -d
```

## 📌 Meaning:

* `up` → services start karega
* `-d` → background mode me run karega

---

# 🌐 GitLab Server Access

Browser me open karna:

```text
http://localhost:8000
```

📌 Login:

* Username: `root`
* Password: jo docker-compose.yml me set kiya hai

---

# 📂 New Project Create (for testing)

Instructor ne ek project banaya:

* Project Name: `gitlab-runner`
* Public repository
* README enabled

📌 Purpose:
Runner registration & CI/CD testing ke liye.

---

# ⚙ GitLab Runner Registration Token

GitLab UI me token milta hai:

Path:

➡️ Admin Area
➡️ CI/CD
➡️ Runners
➡️ Registration Token Copy

📌 Token ka use:
Runner ko GitLab server ke sath register karne ke liye.

---

# 🖥 Runner Register Command (Inside Container)

Runner ko register karne ke liye command:

```bash
docker exec -it my-gitlab-runner gitlab-runner register
```

📌 Explanation:

* `docker exec` → container ke andar command run karega
* `-it` → interactive mode
* `my-gitlab-runner` → container name
* `gitlab-runner register` → runner registration process start karega

---

# 🧾 Runner Registration Steps (Inputs)

Command run karne ke baad runner kuch questions poochta hai:

---

## 1️⃣ GitLab Instance URL

Instructor ne URL diya:

```text
http://my-gitlab-server
```

📌 Reason:
Docker network me containers apne container_name/hostname se access ho jaate hain.

---

## 2️⃣ Registration Token

Jo GitLab admin panel se copy kiya tha, wahi paste kiya.

---

## 3️⃣ Runner Description

Example:

```text
my-docker-runner
```

📌 Purpose:
Runner ko identify karne ke liye.

---

## 4️⃣ Tags

Example:

```text
docker
```

📌 Tags ka use:
CI/CD pipeline me specify kar sakte ho ki job kis runner pe run ho.

---

## 5️⃣ Executor Select

Executor ka matlab:

Runner job kaise run karega?

Instructor ne choose kiya:

```text
docker
```

📌 Means:
Runner Docker containers ke through jobs execute karega.

---

## 6️⃣ Default Docker Image

Instructor ne choose kiya:

```text
alpine:latest
```

📌 Alpine kya hai?

* lightweight Linux image
* fast execution
* mostly CI/CD jobs ke liye best

---

# ✅ Runner Successfully Registered Message

Registration complete hone ke baad message aata hai:

✅ Runner registered successfully
✅ config file saved

---

# 🔄 Runner Restart (Important Step)

Changes apply karne ke liye runner restart kiya:

```bash
docker restart my-gitlab-runner
```

---

# 🧪 Runner Verify Command

Runner list check karne ke liye:

```bash
docker exec -it my-gitlab-runner gitlab-runner list
```

📌 Output me runner details show hoti hain.

---

# 🌍 GitLab UI me Runner Online Status

GitLab Admin panel me jaake check kiya:

➡️ Admin Area
➡️ CI/CD
➡️ Runners

Result:

✅ Runner "Online" show hone lagta hai.

📌 Meaning:
Runner successfully connected hai GitLab server ke sath.

---

# ⭐ Why Runner Online Hona Important hai?

Agar runner online nahi hai to:

❌ CI/CD jobs pending me stuck ho jayengi
❌ pipeline run nahi hogi
❌ build/test/deploy execute nahi hoga

---

# 🧠 Interview Questions (Most Important)

## ❓ Q1: GitLab Runner ko register karne ke liye kya chahiye?

✅ Answer:

* GitLab instance URL
* Registration token

---

## ❓ Q2: GitLab Runner ka executor kya hota hai?

✅ Answer:
Executor define karta hai runner job kaise execute karega.

Examples:

* shell
* docker
* kubernetes

---

## ❓ Q3: Docker executor use karne ka benefit kya hai?

✅ Answer:
Docker executor isolated environment provide karta hai,
jisse pipeline consistent aur reproducible hoti hai.

---

## ❓ Q4: Docker socket mount kyu karte hain?

```yaml
/var/run/docker.sock:/var/run/docker.sock
```

✅ Answer:
Taaki runner Docker daemon ko access kar sake
aur docker build/run commands execute kar sake.

---

## ❓ Q5: privileged: true kyu use hota hai?

✅ Answer:
Runner ko extra permissions dene ke liye
taaki wo Docker containers properly run/build kar sake.

---

## ❓ Q6: depends_on ka use kya hai?

✅ Answer:
Runner ko GitLab server ke start hone ke baad hi run karna hota hai.
Isliye runner service GitLab server service pe depend karti hai.

---

# 🔥 One-Line Summary (Revision)

✅ GitLab Runner setup Docker Compose me ek separate service add karke hota hai.
✅ Runner register karne ke liye URL + token chahiye hota hai.
✅ Docker executor me runner pipelines Docker container ke through run karta hai.
✅ Runner online aa gaya means CI/CD pipelines execute karne ke liye ready hai.

---

# 🎯 Final Conclusion

Is video me humne:

✅ GitLab Runner install kiya
✅ Docker Compose me runner service add ki
✅ Runner ko GitLab server ke sath register kiya
✅ Runner verify kiya
✅ GitLab UI me runner ko online dekha

---
