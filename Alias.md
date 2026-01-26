````md
# 📘 Git Alias – Complete Notes (Detailed)

---

## 🔹 Git Alias kya hota hai?
- **Git Alias** ka matlab hota hai:
  - Git ki **lambi commands** ke liye
  - **shortcuts / short names** banana  

👉 Simple words me:  
**Git Alias = Git commands ka shortcut**

---

## 🔹 Git Alias ki zarurat kyu padti hai?
- Git me bahut si commands:
  - lambi hoti hain  
  - baar-baar likhni padti hain  

Examples:
```bash
git remote add origin <url>
git log --oneline
git status
git branch
````

👉 Inko short karne ke liye **alias** use hota hai

---

## 🔹 Git Alias se kya fayda hota hai?

* ⏱️ Time save hota hai
* ❌ Typing mistakes kam hoti hain
* 🚀 Productivity badhti hai
* 💡 Interview me strong impression padta hai

---

## 🔹 Git Alias banane ke 2 tarike

1. **Config file edit karke (manual way)**
2. **Git command ke through (easy way)**

Hum dono cover karenge 👍

---

# 🔹 Method 1: `.gitconfig` file se Alias banana (Global)

## 📌 Global alias kya hota hai?

* Jo alias:

  * **har repository me kaam kare**
  * sirf ek project tak limited na ho

👉 Global alias **Home Directory** ki config me store hota hai

---

## 🔹 Home directory me kaise jaayein?

```bash
cd ..
cd ..
```

OR directly:

```bash
cd ~
```

---

## 🔹 Hidden files dekhna

```bash
ls -a
```

👉 Yahan aapko ek file dikhegi:

```text
.gitconfig
```

---

## 🔹 `.gitconfig` file kya hoti hai?

* Ye Git ki **global configuration file** hoti hai
* Isme hota hai:

  * username
  * email
  * aliases
  * other git settings

---

## 🔹 `.gitconfig` file open karna

```bash
nano .gitconfig
```

---

## 🔹 Alias ka syntax (`.gitconfig` ke andar)

```ini
[alias]
    shortcut = actual-command
```

📌 **Indentation (space) bahut important hai**

---

## 🔹 Example: `git status` ka alias banana

### `.gitconfig` ke andar likho:

```ini
[alias]
    st = status
```

👉 Matlab:

```bash
git st  → git status
```

---

## 🔹 File save & exit (nano editor)

* Save: `Ctrl + S`
* Exit: `Ctrl + X`

---

## 🔹 Alias test karna

Kisi bhi git-initialized repository me jaakar:

```bash
git st
```

👉 Output same hoga jaise:

```bash
git status
```

📌 Kyunki ye alias **global** hai,
har repo me kaam karega ✅

---

# 🔹 Method 2: Git Command se Alias banana (Easy & Recommended)

## 🔹 Global alias banana (command se)

```bash
git config --global alias.st status
```

👉 Ye bhi wahi kaam karega jo `.gitconfig` edit karke kiya

---

## 🔹 Repository-specific alias banana

Agar alias **sirf ek project** ke liye chahiye:

```bash
git config alias.br branch
```

👉 Is case me:

* `--global` use nahi kiya
* Alias sirf isi repository me valid hoga

---

## 🔹 Example aliases (Common & Useful)

```bash
git config --global alias.co checkout
git config --global alias.cm commit
git config --global alias.lg "log --oneline --graph --all"
git config --global alias.br branch
```

Use:

```bash
git co main
git cm -m "message"
git lg
git br
```

---

## 🔹 Global vs Local Alias (Difference)

| Type         | Scope                |
| ------------ | -------------------- |
| Global alias | Har repository me    |
| Local alias  | Sirf current repo me |

---

## 🔹 Alias kahan store hota hai?

### Global alias:

```text
~/.gitconfig
```

### Local alias:

```text
.git/config
```

---

## 🔹 Local `.git/config` file dekhna

```bash
cd .git
ls -a
nano config
```

👉 Yahan bhi aapko `[alias]` section milega

---

## 🔹 Alias delete kaise karein?

### Global alias delete:

```bash
git config --global --unset alias.st
```

### Local alias delete:

```bash
git config --unset alias.br
```

---

## 🔹 Alias list kaise dekhein?

### Global aliases:

```bash
git config --global --get-regexp alias
```

### Local aliases:

```bash
git config --get-regexp alias
```

---

## 🔹 Real-life use case

* Daily kaam me:

  * `git status`
  * `git log`
  * `git branch`
  * `git checkout`

👉 In sabke alias bana lo:

* typing fast
* mistakes kam
* kaam smooth

---

## 🔹 Interview ke liye One-Line Summary

> **Git Alias Git commands ke shortcuts hote hain
> jo productivity badhate hain**

---

## 🔹 Interview Rapid Q&A ⭐

**Q. Git alias kya hota hai?**
➡ Git command ka shortcut

**Q. Global alias aur local alias me difference?**
➡ Global har repo me, local sirf ek repo me

**Q. Alias kahan store hota hai?**
➡ `.gitconfig` (global), `.git/config` (local)

---

## 🔹 Best Practices ⚠️

* Short aur meaningful alias rakho
* Team ke saath kaam me:

  * very aggressive aliases avoid karo
* `git reset` jaise commands ke alias carefully banao

---

## 🔹 Golden Tip 🧠

> Agar aap roz koi command 10 baar likh rahe ho
> to **uska alias zaroor banao**

---

## 🔹 Summary (Cheat Sheet)

```text
git status      → git st
git branch      → git br
git checkout    → git co
git commit      → git cm
git log --oneline → git lg
```
Bas bolo next topic kaunsa hai 😄
```
