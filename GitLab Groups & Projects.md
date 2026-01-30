# 📘 GitLab Groups & Projects – Detailed Notes (Step-by-Step)

> Is lecture me humne **GitLab ke Groups aur Projects** ka concept detail me samjha  
> aur **practical flow** dekha:
> - Group create karna  
> - Group ke andar Project create karna  
> - Local code ko GitLab par SSH ke through push karna  

---

## 🎯 Lecture Objective

Is video ke baad aap ye clearly samajh jaoge:

- GitLab me **Groups kya hote hain**
- Projects (Repositories) ka role
- GitHub vs GitLab structure difference
- Group ke andar project kaise create hota hai
- Local system se GitLab par code kaise push hota hai

---

## 🔹 Groups & Projects – Basic Concept

### 🔸 GitHub ka Concept (Recap)
- GitHub me:
  - **User account** hota hai
  - User ke andar **multiple repositories** hoti hain
  - Repository = source code ka store

---

### 🔸 GitLab ka Concept
- GitLab me:
  - **Group** hota hai (user se thoda advanced)
  - Group ke andar **multiple Projects** hote hain
  - Project = GitHub repository ke barabar

📌 **Simple mapping:**

| GitHub | GitLab |
|------|--------|
| User | Group |
| Repository | Project |
| Repo URL | Group/Project URL |

---

## 🔹 Group Kya Hota Hai?

- Group ek **container** hota hai
- Group ke andar aap:
  - Multiple projects rakh sakte ho
  - Team members add kar sakte ho
  - Permissions manage kar sakte ho

### 💡 Real-life Example
Agar ek company hai **Techno**, to:
- Techno (Group)
  - Mobile App (Project)
  - Web App (Project)
  - Desktop App (Project)

👉 Sab projects **ek hi group** ke andar manage hote hain

---

## 🔹 Project Kya Hota Hai?

- Project = repository
- Yahin par:
  - Source code hota hai
  - Commits, branches, CI/CD pipelines hoti hain

📌 GitHub me jise repository kehte the,  
📌 GitLab me use **Project** kehte hain

---

## 🔹 Step 1: New Group Create Karna

### Steps:
1. GitLab dashboard par jao
2. **New Group** button par click karo
3. Option select karo: **Create a new group**

### Group Details:
- **Group Name**: (example: `techno`)
- Ye name **URL ka part** ban jaata hai  
```

gitlab.com/techno

```
- **Visibility**:
- Private
- Public
- **Who will use this group?**
- Just me
- Team / Company
- **Purpose**:
- Code store karna, DevOps, etc.

👉 Click **Create Group**

---

## 🔹 Step 2: Group ke andar Project Create Karna

Group create hone ke baad:

### Ways:
- Group page se directly **Create Project**
- Ya sidebar se **New Project**

### Project Creation:
1. Click **Create a blank project**
2. **Project Name**:
 - Example: `my-project` / apna naam
3. URL automatically ban jaata hai:
```

gitlab.com/techno/my-project

```
4. Visibility:
- Group private → project bhi private
5. README optional (is lecture me skip kiya)

👉 Click **Create Project**

---

## 🔹 GitLab Project Page par Kya Dikhta Hai?

- Push existing repository ke commands
- SSH-based remote URL
- Git commands ready-made mil jaati hain

---

## 🔹 Step 3: Local Code Create Karna

### Local Working Directory
- VS Code / koi bhi editor open karo
- Example file:
```

index.html

````

### Sample Code:
```html
<!DOCTYPE html>
<html>
<h2>GitLab</h2>
</html>
````

---

## 🔹 Step 4: Git Initialize Karna (Local)

```bash
git init
```

👉 Isse:

* Local repository create hoti hai
* `.git` folder ban jaata hai

---

## 🔹 Step 5: Changes Track & Commit Karna

```bash
git add .
git commit -m "GitLab first code"
```

* `git add .` → staging
* `git commit` → local repo me save

---

## 🔹 Step 6: Local Repo ko GitLab Project se Connect Karna

GitLab already command deta hai:

```bash
git remote add origin git@gitlab.com:techno/my-project.git
```

📌 Yahan **SSH URL** use ho raha hai
📌 SSH key already setup honi chahiye (last video)

---

## 🔹 Step 7: Branch Rename (master → main)

### Check branch:

```bash
git branch
```

Default:

```
master
```

### Rename command:

```bash
git branch -M main
```

---

## 🔹 Step 8: Code Push Karna GitLab par

```bash
git push -u origin main
```

### `-u` ka fayda:

* Future me sirf `git push` likhna padega

---

## 🔹 Result

* Code successfully GitLab project me push ho gaya
* `index.html` file GitLab UI me visible
* Project live ho chuka hai 🎉

---

## 🧠 Interview Important Points

**Q1. GitLab me repository ko kya kehte hain?**
➡ Project

**Q2. GitLab me group ka role kya hota hai?**
➡ Multiple projects & permissions manage karna

**Q3. GitLab URL structure kya hota hai?**

```
gitlab.com/<group-name>/<project-name>
```

**Q4. GitHub aur GitLab me main difference?**
➡ GitHub → user-based repos
➡ GitLab → group-based projects

---

## 🧾 One-Line Summary

> **GitLab me Groups ek container hote hain jinke andar multiple Projects (repositories) manage hote hain, aur SSH ke through hum apna local code securely GitLab par push kar sakte hain.**

---

## 🔚 Conclusion

* Groups → organization & access control
* Projects → actual code repositories
* SSH → secure & professional workflow
* Ye concepts clear honge to **GitLab CI/CD, permissions, DevOps pipelines** easy ho jaate hain

👉 **Next videos me: GitLab CI/CD, runners, pipelines 🚀**

```
```
