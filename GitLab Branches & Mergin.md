# 🌿 GitLab Branches & Merging – Detailed Notes (with Practical Flow)

> Is lecture me humne **GitLab me Branches aur Merging** ka concept  
> **theory + practical example** ke saath samjha.  
> Ye concept **team-based development** ke liye bahut hi important hai.

---

## 🎯 Lecture Objective

Is video ke baad aap samajh paoge:

- Branch kya hoti hai aur kyun use hoti hai
- New branch kaise create karte hain
- Branch me kaam karke code push kaise karte hain
- Merge Request (MR) kya hoti hai
- Branch ko main branch me kaise merge karte hain  
  - GitLab UI se  
  - Git commands se

---

## 🔹 Branches ka Concept (Theory)

### ❓ Branch kya hoti hai?

- Branch = **main codebase ki ek copy**
- Is copy ke andar aap:
  - New feature add kar sakte ho
  - Experiment kar sakte ho
  - Bug fix kar sakte ho

👉 Bina **main branch** ko disturb kiye

---

### 💡 Simple Example

- Aapka project already GitLab par hai
- Ab aap ek **new feature** add karna chahte ho
- Lekin:
  - Main code kharab nahi karna
  - Team leader ka code disturb nahi karna

👉 Solution: **New branch create karo**

---

### 🔁 Branch Workflow (High Level)

1. Main branch already exists
2. New branch create hoti hai (exact copy)
3. New feature us branch me develop hota hai
4. Feature final hone ke baad:
   - Branch → Main branch me merge

---

## 🔹 Team Work Scenario

- 10 log ek hi project par kaam kar rahe hain
- Sab **main branch** me direct push nahi karte
- Har developer:
  - Apni **separate branch** me kaam karta hai
- Final code:
  - Review ke baad main branch me merge hota hai

📌 **Main branch hamesha stable rehti hai**

---

## 🔹 Step 1: New Project Create Karna

- GitLab me project create kiya:
  - Group select kiya (e.g. `techno`)
  - Project name: `branch-and-merge`
  - Visibility: Private
- Project GitLab par ready

---

## 🔹 Step 2: Initial Code (Main Branch)

- New file create ki:
```

index.html

````
- Code example:
```html
<h2>Branches and Merging</h2>
````

* Commit message:

```
group leader
```

📌 Ye code **main branch** me gaya

---

## 🔹 Step 3: Project Clone Karna (Local System)

```bash
git clone <project-ssh-url>
cd branch-and-merge
code .
```

👉 Ab:

* Project local system me aa gaya
* Git already initialized hai

---

## 🔹 Step 4: New Branch Create Karna

### ❗ Reason

Main branch me direct changes nahi karni hain
(Group leader gussa ho sakta hai 😄)

---

### Command (Create + Switch):

```bash
git checkout -b css
```

👉 Isse:

* `css` naam ki new branch create ho gayi
* Automatically us branch me switch ho gaye

### Branch check:

```bash
git branch
```

Output:

```
main
* css
```

---

## 🔹 Step 5: New Feature (CSS File) Add Karna

* New file:

  ```
  style.css
  ```
* Example changes:

```css
* {
  margin: 0;
  padding: 0;
}
```

---

## 🔹 Step 6: Commit & Push (CSS Branch)

```bash
git add .
git commit -m "style.css file added in css"
git push -u origin css
```

📌 Important:

* Code **css branch** me push hua
* Main branch abhi untouched hai

---

## 🔹 Step 7: GitLab UI me Branch Status

* Pehle:

  * Sirf `main` branch visible thi
* Push ke baad:

  * `css` branch bhi visible ho gayi
* GitLab automatically:

  * **Create Merge Request** ka option show karta hai

---

## 🔹 Step 8: Merge Request (UI se Merge)

### Merge Request kya hoti hai?

* Request to merge:

  * Source branch → Target branch
  * `css` → `main`

---

### Steps:

1. **Create Merge Request** par click
2. Title auto-filled (change optional)
3. Description optional
4. Click **Create Merge Request**
5. Status: **Ready to merge**
6. Click **Merge**

👉 Result:

* `style.css` main branch ka part ban gayi
* CSS branch delete bhi kar sakte ho

---

## 🔹 Step 9: Merge Using Git Commands (Alternative)

### Switch to main branch:

```bash
git switch main
```

### Merge css branch:

```bash
git merge css
```

### Push updated main branch:

```bash
git push
```

👉 Same result, bas UI ki jagah CLI use hua

---

## 🔹 Final Result

* Main branch me:

  * `index.html`
  * `style.css`
* Feature successfully merged
* Extra branch delete ho chuki

---

## 🧠 Interview & Real-World Points

**Q1. Branch ka use kyun hota hai?**
➡ Main codebase ko disturb kiye bina development ke liye

**Q2. Merge Request kya hoti hai?**
➡ Ek process jisme branch ka code review ke baad main me merge hota hai

**Q3. Team me kaam kaise hota hai?**
➡ Har developer separate branch me kaam karta hai

**Q4. GitLab me merge kaise kar sakte hain?**
➡ UI se ya Git commands se (dono)

---

## 🧾 One-Line Summary

> **Branching hume safe development ka environment deta hai aur merging se final, tested code main branch ka part banta hai.**

---

## 🔚 Conclusion

* Branches = safety + parallel development
* Merging = controlled integration
* Ye concept GitLab CI/CD aur DevOps workflow ka base hai

🚀 **Next Video: GitLab CI/CD Pipelines**

```
```
