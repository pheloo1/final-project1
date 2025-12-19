# 🔐 Secure Node.js Express Application  
**Full-Spectrum Web App Hardening – SSD Project**

This project is a **secured version** of a deliberately vulnerable Node.js + Express application.  
It demonstrates a complete security workflow including **DAST, SAST (Semgrep), custom rule creation, vulnerability fixing, and re-testing**.

Base vulnerable app:  
https://github.com/SirAppSec/vuln-node.js-express.js-app

---

## 🎯 Objectives

- Discover real vulnerabilities using **OWASP ZAP** and **manual testing**
- Map issues to the **OWASP Top 10**
- Trace vulnerabilities to source code using **Semgrep**
- Write **custom Semgrep rules** for exploited patterns
- Fix vulnerabilities and prove remediation with re-testing

---

## 🛠️ Technologies

- Node.js, Express.js  
- SQLite + Sequelize  
- OWASP ZAP, Postman  
- Semgrep (built-in + custom rules)  
- Helmet, dotenv, JWT  

---

## ⚙️ Setup & Run

```bash
git clone https://github.com/SirAppSec/vuln-node.js-express.js-app.git
cd vuln-node.js-express.js-app
npm install
npm run dev
```

App runs on:
```
http://localhost:3000
```

Create `.env` from `.env.example` before running.

---

## 🔍 Security Testing

### DAST
- Automated scan using **OWASP ZAP**
- Manual exploitation using **Postman**
- Found **8+ distinct vulnerabilities** across **4+ OWASP Top 10 categories**

### SAST
Run built-in rules:
```bash
semgrep --config "p/javascript" --config "p/nodejs"
```

Run custom rules:
```bash
semgrep --config semgrep-rules/
```

Custom rules detect:
- SQL injection via string concatenation
- XSS from unsanitized output
- Insecure JWT handling

---

## 🔧 Fixes & Hardening

- Parameterized SQL queries
- Input validation & output encoding
- Secure JWT verification
- Security headers using Helmet
- Removed hard-coded secrets
- Improved access control

---

## 🔁 Re-Testing

- OWASP ZAP attacks no longer succeed
- Semgrep findings reduced or eliminated
- Custom rules confirm vulnerable patterns are removed

---

## 📦 Included Deliverables

- Hardened source code  
- `semgrep-rules/` (custom rules)  
- `.env.example`  
- Security report (PDF)  
- Before/After test evidence  
- Short demo video  

---

## ⚠️ Disclaimer

For **educational purposes only**.  
All testing was performed on **local lab environments**.
