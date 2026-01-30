# 📘 GitLab ke saath System ko Connect Karna (SSH Keys) – Detailed Notes

> Is lecture me humne **GitLab account ko apne local system se connect** karna seekha,  
> specially **SSH Keys** ka use karke.  
> Saath hi GitHub vs GitLab URL structure, Groups, Projects aur cloning ka practical flow samjha.

---

## 🎯 Lecture Objective

Is video ka main focus tha:

- System ko GitLab account se connect karna  
- HTTPS vs SSH authentication samajhna  
- GitLab URL structure (Group & Project concept)  
- SSH key generate karna (GitLab ke liye)  
- SSH key ko GitLab account me add karna  
- SSH ke through project clone karke verify karna  

---

## 🔹 System ko GitLab se Connect Karna – Why Required?

Agar aap:
- Repository / project clone karna chahte ho  
- Code push karna chahte ho  
- Code pull karna chahte ho  

👉 To **system aur GitLab account ka connected hona mandatory** hota hai.

---

## 🔹 Authentication ke 2 Tareeke

### 1️⃣ HTTPS Method
- Username / password / token based
- Global authentication hoti hai
- Multiple accounts ek saath handle karna difficult

### 2️⃣ SSH Method (Recommended ✅)
- Key-based authentication
- Zyada secure
- Zyada fast
- Multiple GitLab accounts ek hi system par easily use kar sakte ho

📌 **Is video ka focus: SSH Method**

---

## 🔹 GitHub vs GitLab – URL Structure

### 🔹 GitHub URL Format
```

[https://github.com/](https://github.com/)<username>/<repository-name>

```

Example:
```

[https://github.com/farhan-ali/demo-repo](https://github.com/farhan-ali/demo-repo)

```

---

### 🔹 GitLab URL Format
```

[https://gitlab.com/](https://gitlab.com/)<group-name>/<project-name>

```

Example:
```

[https://gitlab.com/devops/first-project](https://gitlab.com/devops/first-project)

````

---

## 🔹 Important Terminology Difference

| GitHub | GitLab |
|-----|------|
| Repository | Project |
| Username | Group |
| Repo list | Projects under a group |

📌 GitLab me:
- **Group** ke andar multiple **Projects** hote hain  
- Permissions, collaborators, access control mostly **group level** par manage hota hai

---

## 🔹 Project Access Problem (Without SSH)

Jab naya project create hota hai:
- Aap code **push / pull / clone** nahi kar sakte
- GitLab warning deta hai:
  > *No SSH key added*

👉 Solution: **SSH Key generate & add karna**

---

## 🔹 SSH Key Generate Karna (GitLab ke liye)

### Step 1️⃣ Terminal Open Karo
- Git Bash / Terminal
- Kisi bhi folder ke andar

---

### Step 2️⃣ SSH Key Generate Command

```bash
ssh-keygen -t ed25519 -C "your-email@gmail.com"
````

📌 Breakdown:

* `ssh-keygen` → key generate karne ke liye
* `-t ed25519` → cryptographic algorithm (fast & secure)
* `-C` → comment (usually email id)

---

### Step 3️⃣ Location Confirm Karo

* Default path:

```
~/.ssh/id_ed25519
```

* Enter press karo

---

### Step 4️⃣ Passphrase (Optional)

* Skip kar sakte ho (Enter press karo)

---

## 🔹 SSH Keys Location

Path:

```
~/.ssh/
```

Files:

* `id_ed25519` → **Private Key**
* `id_ed25519.pub` → **Public Key**

⚠️ **Private key kabhi share nahi karni**
✅ **Public key GitLab me add hoti hai**

---

## 🔹 Public SSH Key Copy Karna

* `id_ed25519.pub` file open karo (Notepad / VS Code)
* Puri key copy karo

---

## 🔹 GitLab Account me SSH Key Add Karna

### Step 1️⃣ GitLab → Profile → Preferences

### Step 2️⃣ SSH Keys Section me jao

### Step 3️⃣ Add New SSH Key

* Title: (kuch bhi meaningful)
* Key: **Public SSH key paste karo**
* Expiry: Optional

👉 Click **Add Key**

---

## 🔹 SSH Key Successfully Added ✅

* Ab GitLab account system se linked hai
* Warning messages remove ho jaati hain

---

## 🔹 SSH Connection Test – Project Clone

### Step 1️⃣ Project Open Karo

### Step 2️⃣ Code → SSH URL Copy Karo

Example:

```
git@gitlab.com:devops/first-project.git
```

---

### Step 3️⃣ Clone Command Run Karo

```bash
git clone git@gitlab.com:devops/first-project.git
```

---

## 🔹 Result

* Repository successfully clone ho jaati hai
* README.md file visible hoti hai
* SSH authentication verified ✅

---

## 🔹 Advantages of SSH over HTTPS

* 🔐 More secure (encrypted connection)
* ⚡ Faster
* 🔁 One-time setup
* 👥 Multiple GitLab accounts easily handle
* ❌ No repeated login / password required

---

## 🧠 Interview Questions

**Q1. GitLab me repository ko kya kehte hain?**
➡ Project

**Q2. GitLab URL me username ki jagah kya hota hai?**
➡ Group name

**Q3. SSH key kyun use karte hain?**
➡ Secure & password-less authentication ke liye

**Q4. Public aur Private SSH key me difference?**
➡ Public key → GitLab
➡ Private key → System me safe

**Q5. Recommended SSH algorithm kaunsa hai?**
➡ `ed25519`

---

## 🔹 One-Line Summary

> **SSH keys allow secure, fast, and password-less authentication between your system and GitLab, enabling smooth code push, pull, and clone operations.**

---

## 🔚 Conclusion

* GitLab ke saath SSH setup **mandatory & industry standard** hai
* HTTPS beginners ke liye okay hai, but
* **Professional & DevOps workflows me SSH preferred hota hai**

👉 **Next video: GitLab CI/CD & pipelines 🚀**

```
```
