````md
# 📘 Git Stash Command – Explained Notes (Hinglish)

> Ye notes **lecture ko explain karte huye**, real-life scenario + interview point of view se banaye gaye hain.  
> Topic: **`git stash` – pending changes ko temporarily save karna**

---

## 🔹 Git Stash kya hota hai?

**Git Stash** ek aisi command hai jo:

- Aapke **unfinished / pending changes** ko  
- **without commit**  
- ek **temporary safe place** me store kar deti hai  

👉 Taaki aap:
- Branch switch kar sako
- Updates pull / fetch kar sako
- Dusra urgent kaam kar sako  
**without changes lose kiye**

---

## 🔹 Real-Life Problem (Lecture Scenario)

Imagine karo 👇  

- Huzaifa ek **feature branch** par kaam kar raha hai  
- Kaam **complete nahi hua**, isliye commit nahi kar sakta  
- Manager bolta hai:
  - “Main branch me jao, urgent bug fix karo”

⚠️ Problem:
- Changes **delete nahi karna**
- Changes **commit bhi nahi karna**
- Branch **switch zaroori** hai

👉 Solution: **`git stash`** ✅

---

## 🔹 Initial Setup (Lecture Flow)

### 1️⃣ Git initialize
```bash
git init
````

### 2️⃣ Files add & first commit

```bash
git add .
git commit -m "First commit"
```

### 3️⃣ Branch rename + remote connect

```bash
git branch -m main
git remote add origin <repo-url>
git push -u origin main
```

---

## 🔹 Git Stash ka Core Concept

> **“Commit nahi karna, delete nahi karna,
> sirf temporarily side me rakhna.”**

---

## 🔹 Git Stash Use Karna (Basic)

### Step: Pending changes ko stash me bhejna

```bash
git stash
```

👉 Isse kya hota hai:

* Working directory **clean** ho jaati hai
* Pending changes **stash area** me save ho jaate hain
* Aap safely branch switch kar sakte ho

---

## 🔹 Stash ko samajhna: Room Concept 🏠

* Har `git stash` = ek **room**
* Har room me alag-alag pending changes
* Git automatically index deta hai:

  ```
  stash@{0}, stash@{1}, stash@{2} ...
  ```

---

## 🔹 Stash List Dekhna

```bash
git stash list
```

👉 Output batata hai:

* Kitne stash pade hain
* Kis order me pade hain
* Kaun sa latest hai

---

## 🔹 Multiple Stash Banana

Agar aap:

* Dobara changes karo
* Fir commit nahi karna chaho

```bash
git stash
```

👉 Ab stash list me **multiple entries** aa jaayengi

---

## 🔹 Stash se Changes Wapas Lana

### 1️⃣ Latest stash restore karna (copy rehti hai)

```bash
git stash apply
```

👉 Result:

* Latest stash restore
* **Stash list me entry remain karti hai**

---

### 2️⃣ Specific stash restore karna

```bash
git stash apply stash@{1}
```

👉 Use jab:

* Latest nahi
* Koi specific stash chahiye

---

## 🔹 `apply` vs `pop` 🔥 (Very Important)

### 🔸 `git stash apply`

* Changes restore ✔️
* Stash list me entry ❌ delete nahi hoti

### 🔸 `git stash pop`

```bash
git stash pop
```

* Changes restore ✔️
* Stash list se entry ❌ permanently remove

👉 **Pop = Apply + Delete**

---

## 🔹 Example (Lecture Flow)

```bash
git stash pop
```

👉 Result:

* Latest stash working directory me aa gaya
* Stash list se remove ho gaya

---

## 🔹 Stash List Clear Karna (Danger Zone ⚠️)

```bash
git stash clear
```

👉 Isse:

* Saare stash permanently delete
* Recovery possible nahi

⚠️ Use very carefully

---

## 🔹 Important Interview Questions 🎯

### Q1. Git stash ka use kya hai?

> Pending changes ko bina commit kiye temporarily save karna

### Q2. `apply` aur `pop` me difference?

* `apply` → restore only
* `pop` → restore + remove from stash list

### Q3. Kya stash multiple ho sakte hain?

✅ Yes, multiple stash possible

### Q4. Kya stash commit hota hai?

❌ No, stash commit nahi hota

---

## 🔹 Kab Git Stash Use Karein?

✔️ Use when:

* Feature incomplete ho
* Branch switch karna ho
* Pull / fetch karna ho
* Urgent bug fix aa jaaye

❌ Avoid when:

* Changes final ho
* Commit ready ho

---

## 🔹 One-Line Summary (Interview Ready)

> **“Git stash temporarily saves uncommitted changes so we can safely switch branches without losing work.”**

---

## 🔹 Final Conclusion

* `git stash` = **lifesaver in real projects**
* Pending kaam ko safe rakhne ka best tool
* Branch switching ko risk-free banata hai
* Interviews me **favorite topic** 💯

---
