# 🚀 GitHub पर Code Push करने का Step-by-Step Guide

इस नोट में हम सीखेंगे कि कैसे किसी भी project
(simple file, React app, Angular app, Node.js app, etc.)
को अपनी working directory से **GitHub पर push** किया जाता है।

---

## 📌 Prerequisites
Push करने से पहले ये चीजें ready होनी चाहिए:

- ✅ Git installed हो  
- ✅ GitHub account बना हो  
- ✅ Git को GitHub से configure कर चुके हों  
  ```bash
  git config --global user.name "your_username"
  git config --global user.email "your_email@gmail.com"
✅ Git Bash terminal available हो

🗂️ Step 1: Project / Working Directory बनाना
Desktop या किसी location पर एक नया folder बनाएं
Example: e-commerce

यही आपकी working directory होगी।

इसके अंदर कोई file या project बनाएं।
Example: index.html

html
Copy code
<h2>Git and GitHub</h2>
🌐 Step 2: GitHub पर New Repository बनाना
GitHub पर login करें

Repositories tab → New पर click करें

Repository का नाम दें (Example: my-project)

Optional description दें

Repository को Public रखें

Create repository पर click करें

👉 अब GitHub पर आपकी empty remote repository बन चुकी है।

⚠️ Important Note
GitHub UI से drag & drop करके files upload करना:

❌ Professional तरीका नहीं है

❌ Version control, branches, history maintain नहीं होती

👉 As a DevOps Engineer / Developer हमेशा Git commands use करें।

🖥️ Step 3: Git Bash Open करना
Project folder के अंदर right-click करें

Open Git Bash here पर click करें

👉 अब terminal आपकी working directory में open है।

🔍 Step 4: Git Configuration Check करें
bash
Copy code
git config --list
👉 Ensure करें कि:

user.name

user.email
सही set हैं।

🧾 Step 5: Git Initialize करना
bash
Copy code
git init
👉 इससे project में Git initialize होगा
और .git hidden folder बन जाएगा (local repository)।

➕ Step 6: Files Stage करना
सारी files track कराने के लिए:

bash
Copy code
git add .
👉 . का मतलब: current directory की सभी files।

💾 Step 7: Commit करना
bash
Copy code
git commit -m "Initial commit"
👉 Commit message बताता है कि इस stage तक क्या change हुआ।

Example:

bash
Copy code
git commit -m "Added h2 tag in HTML file"
🌿 Step 8: Branch को main में Rename करना
By default branch master हो सकती है,
जबकि GitHub पर default branch main होती है।

bash
Copy code
git branch -M main
🔗 Step 9: Remote Repository Add करना
GitHub repository का URL copy करें और run करें:

bash
Copy code
git remote add origin <repository_url>
Example:

bash
Copy code
git remote add origin https://github.com/username/my-project.git
👉 अब local repo को पता है कि code कहाँ push करना है।

⬆️ Step 10: Code Push करना GitHub पर
bash
Copy code
git push -u origin main
👉 First time push पर authentication मांगेगा:

Browser से sign in करें

Access allow करें

✅ Step 11: Verify on GitHub
GitHub repository page refresh करें

आपकी files और commit message दिखेंगे

Commit पर click करके changes देख सकते हैं

👉 इसका मतलब आपका code successfully GitHub पर push हो चुका है।

🔄 Basic Workflow Summary
bash
Copy code

git init

git add .

git commit -m "message"

git branch -M main

git remote add origin <repo_url>

git push -u origin main

📚 What We Learned Today
Working directory से project push करना

GitHub repository create करना

Git init, add, commit, push commands

Local repo को remote repo से link करना

Authentication process

🚀 Next Topics
आगे आने वाली videos में हम सीखेंगे:

Tracked, untracked, modified files

Staging area क्या होता है

Branching & merging

Git workflow deep concepts

✅ Conclusion
👉 Git commands का use करके:

Code properly version control होता है

History maintain रहती है

Team collaboration आसान होती है

Professional DevOps workflow follow होता है

Practice करते रहो — commands अपने आप याद हो जाएँगी! 😊
