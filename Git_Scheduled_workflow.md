# 📘 GitHub Actions – Scheduled Workflow (Cron Based) | Explained Notes

> In notes ka focus hai **GitHub Actions workflow ko time ke basis par run karna**  
> yani **Scheduled Workflow** using **cron**.

---

## 🔁 Recap (Previous Video)

Last video me humne dekha tha:
- Workflow **events** ke base par kaise run hota hai  
  (jaise: `push`, `pull_request`)
- First GitHub Actions workflow create kiya

👉 Is video me **event-based trigger ❌**  
👉 **time-based trigger ✅**

---

## 🎯 Is Video ka Objective

- Workflow ko **schedule** karna
- Specific **time par automatic execution**
- `cron` ka use samajhna

---

## 🔹 Scheduling ka matlab kya hota hai?

Scheduling =  
👉 Ek **fixed time** define karna  
👉 Us time par workflow **automatically run ho**

### Real-life examples:
- Daily backup (raat 12 baje)
- Weekly report (Sunday 6 PM)
- Nightly maintenance job

📌 Yahan **code push / PR ka role nahi hota**

---

## 🔹 Step 1: New Repository Create karna

1. GitHub → **Repositories**
2. Click **New**
3. Repository name:
