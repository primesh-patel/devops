```md
# 📘 GitHub Pull Request – Explained Notes (Hinglish)

> Ye notes **lecture ko explain karte huye** banaye gaye hain.  
> Topic: **Pull Request (PR) – Open Source Contribution ka core concept**  
> Ye concept interviews + real-world projects dono ke liye **bahut important** hai ⭐

---

## 🔹 Pull Request (PR) kya hoti hai?

**Pull Request** tab use hoti hai jab:

- Aap kisi **GitHub repository me contribute** karna chahte ho  
- Lekin:
  - Aap us repo ke **collaborator nahi ho**
  - Aapke paas **direct push access nahi** hai  

👉 Aise me aap **repo owner se request** karte ho:

> “Maine aapke project me kaam kiya hai,  
please meri changes ko review karke  
apni branch me merge kar lijiye.”

Isi ko **Pull Request** kehte hain.

---

## 🔹 Pull Request ka Real Use Case

- Open Source projects
- Public repositories
- Community contributions
- Jab aap **Open Source Contributor** banna chahte ho

👉 Isi process ke through:
- Aapka naam contributors me aata hai
- Aap industry-level workflow seekhte ho

---

## 🔹 Important Terms (Clear Understanding)

### 🔸 Repository Owner
- Jiske account me original repo hoti hai
- Final decision leta hai (accept / reject)

### 🔸 Contributor
- Jo project me contribute karta hai
- Direct push access nahi hota

### 🔸 Fork
- Original repository ki **copy**
- Aapke GitHub account me banti hai

---

## 🔹 High-Level Pull Request Flow

```

Original Repo (Owner)
↑
Pull Request
↑
Forked Repo (Your Account)
↑
Local Clone (Your System)

````

---

## 🔹 Step 1: Public Repository Select Karna

- Ek **public repository** choose karo
- Jisme aap:
  - Feature add karna chahte ho
  - Bug fix karna chahte ho
  - CSS / Docs / Code improve karna chahte ho

👉 Aap collaborator **nahi ho**, isliye direct push allowed nahi

---

## 🔹 Step 2: Repository Fork Karna

### Fork ka matlab:
- Original repo ki **exact copy**
- Aapke GitHub account me

### Steps:
1. Repository page open karo
2. **Fork** button pe click karo
3. Main branch ko fork karo
4. GitHub aapke account me repo copy bana dega

👉 Ab ye repo **aapki ownership** me hai

---

## 🔹 Step 3: Forked Repo Clone Karna (Local System)

```bash
git clone <forked-repo-url>
cd repository-name
````

👉 Ab aap:

* Local system par kaam kar sakte ho
* Bina kisi restriction ke

---

## 🔹 Step 4: New Branch Create Karna (Best Practice)

⚠️ **Main branch me kabhi direct kaam nahi karna**

```bash
git checkout -b new-feature
```

👉 Reason:

* Clean workflow
* Easy review
* Safe merging

---

## 🔹 Step 5: Changes Karna (Development)

Example:

* `style.css` add karna
* CSS code likhna
* Feature / improvement add karna

👉 Ye saari changes **new-feature branch** me hoti hain

---

## 🔹 Step 6: Add, Commit & Push (Forked Repo)

```bash
git add .
git commit -m "Add CSS styling"
git push -u origin new-feature
```

👉 Yahan `origin` = **aapki forked repository**

---

## 🔹 Step 7: Compare & Pull Request

GitHub automatically suggestion deta hai:

> **Compare & Pull Request**

Steps:

1. Button pe click karo
2. Title likho (clear & professional)
3. Description likho:

   * Kya change kiya
   * Kyun useful hai
4. **Create Pull Request**

👉 Ab PR create ho chuki hai 🎉

---

## 🔹 Step 8: Repository Owner ka Role

Owner ko notification milta hai
Owner PR me ye sab check karta hai:

* Files changed
* Code quality
* Commits
* Description
* Conversation

### Owner ke paas 3 options hote hain:

1. ❌ **Reject / Comment**
2. 🔁 **Request Changes**
3. ✅ **Approve**

---

## 🔹 Step 9: Pull Request Merge Karna

Agar owner ko kaam pasand aa gaya:

1. **Approve**
2. **Merge Pull Request**
3. **Confirm Merge**

👉 Result:

* Aapki branch ke changes
* Owner ki **main branch** me aa jaate hain

---

## 🔹 Final Result on GitHub

* `main` branch me new files visible
* Commit message show hota hai
* Contributor ka naam show hota hai
* Contributors list update ho jaati hai ✅

---

## 🔹 Open Source Contributor ka Matlab

> Jo:

* Public repo me contribute kare
* Pull Request ke through
* Jiska PR merge ho jaaye

👉 Aap officially **Open Source Contributor** ban jaate ho 🎯

---

## 🔹 Interview Important Questions 🎯

### Q1. Pull Request kya hoti hai?

> Repository owner se request hoti hai apni changes ko merge karwane ke liye

### Q2. Fork kyun zaroori hai?

> Kyunki without access aap direct push nahi kar sakte

### Q3. Kya main branch me direct kaam kar sakte hain?

❌ Nahi, hamesha new branch use karni chahiye

### Q4. Pull Request kaun merge karta hai?

> Repository owner / maintainer

---

## 🔹 Pull Request vs Collaborator (Quick Difference)

| Pull Request          | Collaborator        |
| --------------------- | ------------------- |
| No direct push        | Direct push allowed |
| Fork required         | Fork not required   |
| Owner approval needed | Approval not needed |

---

## 🔹 One-Line Interview Answer 🧠

> **“Pull Request is a way to contribute to a repository without direct access by requesting the owner to review and merge our changes.”**

---

## 🔹 Final Conclusion

* Pull Request = **heart of open source**
* Safe, professional & scalable workflow
* Real industry practice
* Resume + GitHub profile boost 💯

---
