# 📘 Git & GitHub – SSH Keys (SSH vs HTTPS) Detailed Notes

> Is lecture me humne **GitHub SSH Keys** ka concept detail me samjha,  
> kyun SSH use kiya jata hai, HTTPS se kaise better hai,  
> aur **step-by-step SSH key generate karke GitHub account se link** karna dekha.

---

## 🎯 Lecture Objective

Is video ka main aim tha:

- SSH key kya hoti hai samajhna  
- HTTPS vs SSH ka difference  
- Multiple GitHub accounts ek hi system par kaise use karein  
- SSH key generate karna  
- SSH key GitHub account me add karna  
- SSH URL use karke repository clone / push karna  

---

## 🔹 Repository Clone / Push ke 2 Tarike

GitHub par repository ke saath **2 URLs** milte hain:

1. **HTTPS URL**
2. **SSH URL**

### 🔸 HTTPS URL
- Username / password ya token based authentication
- First time authentication required
- System me **global credential store** hota hai
- Ek time par **sirf ek GitHub account** easily use hota hai

### 🔸 SSH URL
- **Key-based authentication**
- One-time setup
- Password / token bar-bar nahi chahiye
- **Multiple GitHub accounts** ek hi system par possible

---

## 🔐 What is SSH?

- **SSH = Secure Shell**
- Secure, encrypted communication protocol
- Key-based authentication use karta hai

### SSH Authentication kaise kaam karta hai?
- Ek **key pair** hota hai:
  - 🔑 Public Key
  - 🔒 Private Key
- Public key → GitHub account me add hoti hai
- Private key → Aapke system me rehti hai

📌 Jab aap GitHub se connect karte ho:
- GitHub public key verify karta hai
- System private key se authenticate hota hai

---

## 🔹 SSH vs HTTPS (Interview Question ⭐)

| Feature | HTTPS | SSH |
|------|------|------|
| Authentication | Username / Token | Key-based |
| Security | Good | **More Secure** |
| Speed | Normal | **Faster** |
| One-time setup | ❌ | ✅ |
| Multiple accounts | ❌ Difficult | ✅ Easy |
| Developer preference | Less | **Most Preferred** |

👉 **Answer**: SSH zyada secure aur fast hoti hai as compared to HTTPS.

---

## 🔹 Why Developers Prefer SSH?

- One-time setup
- No repeated authentication
- Multiple GitHub accounts easily handle
- Faster & encrypted
- Industry standard (Senior level practice)

---

## 🛠️ SSH Key Generate Karna (Step-by-Step)

### 1️⃣ Git Bash / Terminal Open Karo

Kisi bhi folder me:
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
````

### 🔍 Command Explanation

| Part         | Meaning                                    |
| ------------ | ------------------------------------------ |
| `ssh-keygen` | SSH key generate command                   |
| `-t`         | Key type                                   |
| `ed25519`    | Fast & most secure cryptographic algorithm |
| `-C`         | Comment (usually GitHub email)             |

📌 `ed25519`:

* RSA / DSA se zyada secure
* Fast
* Modern cryptography standard

---

### 2️⃣ Key Location

Default path:

```text
~/.ssh/
```

Press **Enter** (default location accept)

---

### 3️⃣ Passphrase (Optional)

* Passphrase poochega
* Skip karne ke liye **Enter** press kar do (recommended for simplicity)

---

## 📂 Generated Files

Inside `.ssh` folder:

| File             | Purpose                                |
| ---------------- | -------------------------------------- |
| `id_ed25519`     | 🔒 Private key (DO NOT SHARE)          |
| `id_ed25519.pub` | 🔑 Public key (GitHub me add hoti hai) |

---

## 🔹 Public Key Copy Karna

1. `id_ed25519.pub` file open karo
2. Poora content copy karo
   (starts with `ssh-ed25519 ...`)

---

## 🔹 GitHub Account me SSH Key Add Karna

### Steps:

1. GitHub → Profile
2. **Settings**
3. **SSH and GPG keys**
4. Click **New SSH key**
5. Fill details:

   * **Title**: Any name (e.g. Personal Laptop)
   * **Key**: Paste public key
6. Click **Add SSH key**
7. GitHub authentication confirm karo

✅ SSH key successfully added

---

## 🔹 SSH URL Enable Ho Gaya

Ab:

* Repository ke SSH section me
* Koi warning nahi aayegi
* SSH URL usable ho jata hai

---

## 🔹 Clone Repository using SSH

### Old (HTTPS):

```bash
git clone https://github.com/user/repo.git
```

### New (SSH):

```bash
git clone git@github.com:user/repo.git
```

📌 Result:

* No username
* No password
* Direct clone

---

## 🔹 Multiple GitHub Accounts ka Use

### Scenario:

* Ek **personal** GitHub account
* Ek **office** GitHub account

### Solution:

* Har account ke liye:

  * Separate SSH key generate
  * Respective GitHub account me add
* Same system par multiple accounts smoothly work karenge

---

## 🔹 Advantages Summary

* 🔐 Secure (Encrypted)
* ⚡ Fast
* 🔁 One-time setup
* 👥 Multiple accounts supported
* 💼 Industry best practice

---

## 🧠 Interview Questions

**Q1. SSH kya hoti hai?**
➡ Secure Shell, key-based authentication protocol

**Q2. SSH HTTPS se zyada secure kyun hai?**
➡ Encrypted + key-based authentication

**Q3. ed25519 kyun use karte hain?**
➡ Fast & modern cryptographic algorithm

**Q4. Public vs Private key?**
➡ Public → GitHub
➡ Private → Local system

---

## 🔹 One-Line Summary

> **SSH keys provide fast, secure, one-time authentication and allow developers to work with multiple GitHub accounts on the same system.**

---

## 🔚 Conclusion

* Beginners HTTPS se start kar sakte hain
* Professionals / DevOps / CI-CD me **SSH mandatory skill**
* Real-world projects me SSH hi use hota hai

👉 **Next topic: SSH config file & multiple keys handling 🚀**

```
```
