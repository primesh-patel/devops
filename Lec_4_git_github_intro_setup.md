# 🧑‍💻 Git & GitHub — Introduction and Setup Notes

DevOps Engineer के लिए Git और GitHub बहुत important हैं।  
अगर आपने पहले कभी Git/GitHub use नहीं किया है, तो भी tension नहीं —  
यहाँ beginner से advanced तक सब cover किया जाएगा।

---

## 🔹 Version Control System (VCS) क्या है?

Version Control System एक software होता है जो:
- Code changes को track करता है  
- बताता है किस file की किस line में क्या change हुआ  
- Changes की history maintain करता है  
- Old version पर revert करने देता है  
- Multiple people को same project पर collaborate करने देता है  
- Backup और recovery की facility देता है  

👉 यानी VCS से code **safe, trackable और collaborative** बन जाता है।

---

## 🧰 Git क्या है?

- Git एक **popular Version Control System software** है।  
- इसका use करके हम:
  - Code changes track करते हैं  
  - Revert कर सकते हैं  
  - Branching & merging कर सकते हैं  
  - Team collaboration कर सकते हैं  

### 🔹 Branching & Merging
- New feature या experiment के लिए अलग branch बनाते हैं  
- Main code को disturb किए बिना work करते हैं  
- जब code ready हो जाए, तो main branch में merge कर देते हैं  

👉 Git fast, lightweight और small से लेकर large projects के लिए ideal है।

---

## 🌐 Version Control Hosting Platform क्या है?

Git local system पर code manage करता है,  
लेकिन code को online store & collaborate करने के लिए हमें hosting platform चाहिए।

### 🔹 Hosting Platform क्या करता है?
- Central repository provide करता है  
- Code store & manage करता है  
- Collaboration tools देता है:
  - Pull requests  
  - Code reviews  
  - Issue tracking  
- Cloud backup देता है  
- CI/CD integration support करता है  

👉 यह एक **cloud-based platform** होता है।

---

## 🧰 GitHub क्या है?

- GitHub एक **cloud-based Git hosting platform** है।  
- यहाँ आप:
  - Code host कर सकते हो  
  - Team के साथ collaborate कर सकते हो  
  - Open-source projects में contribute कर सकते हो  
  - अपना code globally share कर सकते हो  

👉 यह DevOps और developers के लिए बहुत powerful platform है।

> बाद में GitLab भी cover किया जाएगा।

---

## ⚙️ Git Installation (Windows Example)

1. Browser में search करें: **Git download**  
2. Official website खोलें  
3. अपने OS के हिसाब से version चुनें (जैसे Windows 64-bit)  
4. Installer download करें  
5. Double click करके install करें  
6. Options mostly default रखें  
7. “Open Git Bash here” option enable करें  
8. Install complete करें  

👉 Installation के बाद right-click पर **Open Git Bash here** दिखेगा।

---

## 🖥️ Git Bash Terminal

- Git commands run करने के लिए terminal use होता है  
- Windows में इसे **Git Bash** कहते हैं  
- Right click → *Open Git Bash here* से open करें  

👉 सारी Git commands यहीं run होंगी।

---

## 🌐 GitHub Account Setup

1. GitHub website खोलें  
2. **Sign up / Login** करें  
3. Account create करें  
4. Username अपने real/professional नाम पर रखें  

> Username आपके GitHub URL में दिखता है, इसलिए professional रखें।

---

## 🔗 Git को GitHub से Connect करना (Configuration)

Git को बताना पड़ता है कि आपका GitHub account कौन सा है।

### ✅ Username set करें
```bash
git config --global user.name "your_github_username"
✅ Email set करें (GitHub account वाली)
bash
Copy code
git config --global user.email "your_email@gmail.com"
⚠️ वही email use करें जिससे GitHub account बनाया है।

🔍 Configuration Verify करें
bash
Copy code
git config --list
👉 Output में:

user.name

user.email
आपका सही data दिखना चाहिए।

✅ Result
अब:

Git (local software)

GitHub (cloud hosting platform)

👉 दोनों आपस में connected/integrated हो चुके हैं।

अब जब आप Git से code push करोगे,
तो वो directly आपके GitHub account में जाएगा।

📌 आज क्या सीखा?
Version Control System क्या होता है

Git क्या है और क्यों use होता है

GitHub क्या है

Git installation कैसे करते हैं

GitHub account कैसे बनाते हैं

Git को GitHub से कैसे connect करते हैं

🚀 Next Step
Next video में:

Folder बनाएँगे

Code लिखेंगे

Git use करके code को GitHub पर push करेंगे

👉 Practical hands-on शुरू होगा!

✅ Summary
Git = Version Control System software

GitHub = Git hosting & collaboration platform

Git + GitHub = Code tracking + cloud hosting + collaboration

👉 DevOps Engineer के लिए ये basic & must-have skills हैं।
