# GitHub Contribution Standards – Organisation Guide

This document defines the **production‑level workflow** every contributor in our organisation must follow.  
Iska main goal hai: clean workflow, zero conflicts, predictable reviews, and professional development standards.

---

## 🚀 1. Project Setup (Fork + Clone)

### **Step 1: Fork the Repository**
Aapko jo bhi project assign hua hai:
- GitHub par jao
- **Fork** button dabao  
- Apne GitHub account me ek copy ban jayegi

### **Step 2: Clone Your Fork**
```bash
git clone https://github.com/<your-username>/<repo>.git
cd <repo>
```
Isse aapke system me project aa jayega.

---

## 🔧 2. Basic Git Commands (With Meaning)

### **1️⃣ `git init`**
Initialises git in a folder. (Mostly organisation repos me already hota hai)

### **2️⃣ `git remote add origin <url>`**
Local repo ko ek remote GitHub repo se connect karta hai.

### **3️⃣ `git remote -v`**
Remotes check karne ke liye:
- `origin` → aapka fork  
- `upstream` → main organisation repo

### **4️⃣ Add upstream remote**
```bash
git remote add upstream https://github.com/<org>/<repo>.git
```

### **5️⃣ `git checkout <branch>`**
Branch switch karne ke liye.

### **6️⃣ `git pull`**
Remote changes ko local me lane ke liye.

### **7️⃣ `git fetch`**
Remote branches ka metadata laata hai but merge nahi karta.

---

## 🌿 3. Branching Standards (Feature Workflow)

Har feature / bug fix ke liye **new branch** banao:

```bash
git checkout -b feature/<feature-name>
```

Examples:
- `feature/login-api`
- `bugfix/navbar-issue`
- `docs/readme-update`

**❌ Kabhi bhi `main` ya `dev` me directly commit mat karo.**

---

## 🧑‍💻 4. Working on Your Branch

Aapko jab bhi kaam shuru karna ho:

### **1️⃣ Latest code lo**
```bash
git checkout dev
git pull upstream dev
git checkout feature/<branch>
git merge dev
```
(This prevents future conflicts)

---

## 💾 5. Adding, Committing & Pushing Changes

### **Step 1: Changes stage karo**
```bash
git add .
```

### **Step 2: Commit message (professional format)**
```bash
git commit -m "feat: added login API with validations"
```

### **Commit message rules**
- `feat:` → new feature  
- `fix:` → bug fix  
- `docs:` → documentation  
- `chore:` → minor cleanups  

### **Step 3: Push to your fork**
```bash
git push origin feature/<branch>
```

---

## 🔁 6. Before Creating a Pull Request (IMPORTANT)

PR banane se *pehle hamesha* latest code lo:

```bash
git checkout dev
git pull upstream dev
git checkout feature/<branch>
git merge dev
# Resolve conflicts if any
```

---

## 🔀 7. Creating the Pull Request (PR)

1. GitHub repo → **Compare & Pull Request**
2. Base branch → `dev`
3. Head branch → `feature/<branch>`
4. Description me:
   - Kya change kiya  
   - Why change was needed  
   - Testing steps  
5. Submit PR

---

## 🧑‍🏫 8. Review Process (L2 Developer)

### **L2 Developer Responsibilities**
- Code quality review  
- Architecture check  
- Performance considerations  
- Security validation  
- Standards follow kiye ya nahi  

### **If approved → L2 merges the PR into `dev`**

### **If changes requested → Developer updates branch**
```bash
git add .
git commit -m "fix: updated login validation as per review"
git push
```
Same PR automatically update ho jayega.

---

## 🏁 9. Final Merge to `main`
Only **maintainers** merge `dev` → `main` on production release.

---

## ✔️ Summary Flow

```
Fork → Clone → Create Feature Branch → Code  
→ Commit → Push → PR → L2 Review → Merge to dev → Release to main
```

---

## 📄 End of Document  
Follow this strictly for all organisation projects.
