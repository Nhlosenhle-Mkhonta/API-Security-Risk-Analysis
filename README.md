# API Security Risk Analysis – ReqRes Demo API

## 📌 Project Overview
This repository contains a professional **API Security Risk Analysis Report** performed on the **ReqRes demo API** (`https://reqres.in`).  
The project simulates how cybersecurity agencies and AppSec consultants audit SaaS APIs for risks such as open endpoints, weak authentication, and missing rate limiting.

---

## 🛠 Tools Used
- **Postman** – for sending API requests and inspecting responses  
- **Browser DevTools (Network tab)** – for analyzing headers, status codes, and responses  
- **Google Docs / MS Word** – for drafting the report before exporting to PDF  

---

## 🎯 Scope
- **Allowed**: Read-only testing of demo API endpoints, documentation review, header inspection  
- **Not Allowed**: Exploitation, flooding/DoS, attacking private or production APIs  

---

## 📖 Methodology
1. Selected the **ReqRes API** (`https://reqres.in`)  
2. Reviewed API documentation and available endpoints  
3. Tested endpoints using Postman and Browser DevTools:
   - `GET /users?page=2`
   - `POST /login`
4. Inspected:
   - Authentication requirements  
   - Headers and tokens  
   - Response data  
5. Identified risks and classified severity (Low / Medium / High)  
6. Translated risks into **business impact** (privacy, downtime, compliance)  
7. Suggested clear **remediation steps**  
8. Documented findings in a professional PDF report  

---

## ⚠️ Key Risks Identified
- **Unauthorized Access (401)** – endpoints reject requests but error messages may expose metadata  
- **Forbidden Requests (403)** – access control enforced but inconsistent error handling  
- **Weak Login Simulation** – token returned without expiry or refresh  
- **Open Endpoints** – user data accessible without authentication  
- **Missing Rate Limiting** – repeated requests succeed without throttling  

---

## 📄 Deliverables
- **Report.pdf** – API Security Risk Analysis Report  
- **Screenshots/** – Postman and DevTools request/response captures  
- **README.md** – methodology, scope, and tools used  

---

## ✅ Recommendations
- Require authentication for all sensitive endpoints  
- Use JWT tokens with expiry and refresh mechanisms  
- Apply rate limiting (e.g., 100 requests/min per IP)  
- Validate and sanitize all inputs  
- Return minimal data fields in responses  
- Standardize error messages to avoid leaking system details  
- Implement monitoring and logging for unusual API usage  

