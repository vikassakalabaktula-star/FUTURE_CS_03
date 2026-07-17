# FUTURE_CS_03
# API Security Risk Analysis — JSONPlaceholder & ReqRes

A read-only API security audit performed as a training exercise, modeled on how
an AppSec consultant / SOC analyst would assess a SaaS API's authentication,
authorization, and data-exposure posture.

## 📄 Report
See [`API_Security_Risk_Analysis_Report.docx`](./API_Security_Risk_Analysis_Report.docx)
for the full findings, severity ratings, business impact, and remediation steps.

## 🎯 Scope
- **APIs tested:** [JSONPlaceholder](https://jsonplaceholder.typicode.com) and
  [ReqRes](https://reqres.in) — both public demo/test APIs intended for learning.
- **Methods used:** GET requests and documented safe test POST/PUT calls only
  (JSONPlaceholder fakes writes without persisting them).
- **Explicitly out of scope:** exploitation, authentication bypass, rate-limit
  flooding/DoS, and any private or production system.

## 🛠️ Tools Used
- Postman — request construction, header/response inspection
- Browser DevTools — spot-checking headers and response payloads
- Public documentation review for both APIs

## 🧭 Methodology
1. Selected demo APIs designed for public testing.
2. Reviewed each API's documentation for auth requirements.
3. Sent GET requests to core endpoints (`/users`, `/posts`, `/comments`) and
   inspected headers, status codes, and response bodies.
4. Identified data exposure, authentication, and authorization gaps.
5. Mapped each finding informally to the [OWASP API Security Top 10](https://github.com/OWASP/API-Security).
6. Rated severity (Low/Medium/High) and wrote plain-language business impact
   and remediation for each finding.

## 📁 Repo Contents
- `API_Security_Risk_Analysis_Report.docx` — full report
- `screenshots/` — Postman request/response captures (see below)

## 📸 Screenshots
Add your own Postman screenshots here showing:
- A request to `GET /users/1` with the response body visible (shows PII exposure)
- Response headers for a request (shows absence of rate-limit / auth headers)
- A `GET /users/2` vs `/users/3` pair (shows ID enumeration / no object-level auth)

## ⚠️ Ethics & Disclaimer
This analysis was performed only against public APIs explicitly built for
testing and prototyping. No exploitation, no denial-of-service testing, and
no access to private or production systems occurred at any point.
