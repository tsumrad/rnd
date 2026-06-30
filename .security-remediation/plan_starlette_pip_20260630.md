## Security remediation — starlette (pip)

**Severity:** HIGH
**Current range:** >= 0.4.1, < 1.3.1
**Target version:** 1.3.1
**Breaking change:** Yes
**GHSAs:** GHSA-82w8-qh3p-5jfq, GHSA-jp82-jpqv-5vv3, GHSA-wqp7-x3pw-xc5r, GHSA-x746-7m8f-x49c, GHSA-86qp-5c8j-p5mr, GHSA-2c2j-9gv5-cj73, GHSA-f96h-pmfr-66vw, GHSA-v5gw-mw7f-84px, GHSA-74m5-2c7w-9w3x

### Vulnerability summary
- **GHSA-82w8-qh3p-5jfq** (CVSS 7.5) — Starlette: request.form() limits silently ignored for application/x-www-form-urlencoded enable DoS
- **GHSA-jp82-jpqv-5vv3** (CVSS 3.7) — Starlette: Unvalidated request path concatenated into authority poisons request.url.hostname
- **GHSA-wqp7-x3pw-xc5r** (CVSS 7.5) — Starlette: SSRF and NTLM credential theft via UNC paths in StaticFiles on Windows
- **GHSA-x746-7m8f-x49c** (CVSS 5.3) — Starlette: Arbitrary HTTP method dispatched to `HTTPEndpoint` attributes via `getattr`
- **GHSA-86qp-5c8j-p5mr** (CVSS 6.5) — Starlette has missing Host header validation that poisons request.url.path, bypassing path-based security checks
- **GHSA-2c2j-9gv5-cj73** (CVSS 5.3) — Starlette has possible denial-of-service vector when parsing large files in multipart forms
- **GHSA-f96h-pmfr-66vw** (CVSS 0.0) — Starlette Denial of service (DoS) via multipart/form-data
- **GHSA-v5gw-mw7f-84px** (CVSS 3.7) — Starlette has Path Traversal vulnerability in StaticFiles
- **GHSA-74m5-2c7w-9w3x** (CVSS 7.5) — MultipartParser denial of service with too many fields or files

### Resolution options
- [ ] Assign to coding agent (Copilot / LLM) to author the fix PR
- [ ] Self-resolve — implement migration manually

### Notes
_Add context, blockers, or migration hints here._
