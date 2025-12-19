🔐 Secure Node.js Express Application

Full-Spectrum Web App Hardening Project

This project is a hardened version of a deliberately vulnerable Node.js + Express web application.
It demonstrates a complete secure software development workflow including DAST, SAST (Semgrep), custom security rules, vulnerability remediation, and re-testing.

Base vulnerable app:
https://github.com/SirAppSec/vuln-node.js-express.js-app

📌 Project Objectives

Identify real-world web vulnerabilities using Dynamic Application Security Testing (DAST)

Map findings to the OWASP Top 10

Trace vulnerabilities to source code using Static Application Security Testing (SAST) with Semgrep

Write custom Semgrep rules for exploited patterns

Fix vulnerabilities using secure coding practices

Re-test to prove vulnerabilities are resolved

🧠 Technologies Used

Backend: Node.js, Express.js

Database: SQLite + Sequelize

Security Testing:

OWASP ZAP (DAST)

Postman (manual exploitation)

Semgrep (SAST + custom rules)

Security Libraries:

Helmet

dotenv

JSON Web Tokens (JWT)

Optional Bonus: Splunk (PCAP traffic analysis)

📂 Project Structure
.
├── src/
│   ├── controllers/
│   ├── routes/
│   ├── middleware/
│   └── utils/
├── semgrep-rules/
│   ├── insecure-sql-concat.yaml
│   ├── insecure-jwt.yaml
│   └── xss-unsanitized-output.yaml
├── .env.example
├── package.json
└── README.md

⚙️ Installation & Setup
1️⃣ Clone the Repository
git clone https://github.com/SirAppSec/vuln-node.js-express.js-app.git
cd vuln-node.js-express.js-app

2️⃣ Install Dependencies
npm install

3️⃣ Environment Variables

Create a .env file based on .env.example:

JWT_SECRET=your_secret_here
PORT=3000

4️⃣ Run the Application
npm run dev


The app will be available at:

http://localhost:3000

🧪 Security Testing Workflow
🔍 Phase A – Dynamic Testing (DAST)

Automated scan using OWASP ZAP

Manual exploitation using Postman

Discovered 8+ distinct vulnerabilities across 4+ OWASP Top 10 categories

Examples:

SQL Injection

XSS

Broken Access Control (IDOR)

Insecure JWT handling

🔎 Phase B – Static Analysis (SAST with Semgrep)
Run Built-in Rules
semgrep --config "p/javascript" --config "p/nodejs"

Run Custom Rules
semgrep --config semgrep-rules/


Custom rules were written to detect:

SQL queries built via string concatenation

Unsanitized user input rendered to output (XSS)

Insecure JWT verification patterns

🛠️ Phase C – Fixes & Hardening

Implemented fixes include:

✅ Parameterized SQL queries (no string concatenation)

✅ Server-side input validation & output encoding

✅ Secure JWT verification (algorithm, expiry, issuer)

✅ Security headers via Helmet

✅ Removal of hard-coded secrets

✅ Improved authorization & access control checks

Each vulnerability fix was committed separately with clear references.

🔁 Re-Testing & Verification

Re-ran OWASP ZAP → attacks no longer succeed

Re-ran Semgrep → findings reduced or eliminated

Custom rules confirm vulnerable patterns are removed

📊 Bonus – Traffic Capture & Splunk (Optional)

Captured attack traffic (PCAP) during testing

Ingested PCAP into Splunk

Used SPL queries to rediscover vulnerabilities from logs

Validated real-world visibility of attacks

📦 Deliverables Included

✔ Hardened source code

✔ semgrep-rules/ directory (custom rules)

✔ .env.example (no secrets)

✔ Security report (PDF)

✔ Before/After testing evidence

✔ Short demo video (≤ 3 minutes)

📚 Learning Outcomes

By completing this project, you demonstrate:

Practical web pentesting skills

Strong understanding of OWASP Top 10

Ability to use SAST & DAST together

Secure coding in Node.js & Express

Evidence-based security validation

⚠️ Disclaimer

This project is for educational purposes only.
All testing was performed on local / lab environments only.
