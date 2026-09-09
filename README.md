
# Automated Data Privacy & PII Compliance Auditor

An automated Python-based data auditing and anonymization engine designed to scan datasets for Personally Identifiable Information (PII), enforce string-masking rules, and output audit-ready compliance verification logs prior to data distribution.

---

## Key Features

* **Automated PII Scanning:** Utilizes optimized Regular Expressions (Regex) to detect exposed email addresses, phone numbers, and national identification numbers.
* **Data Anonymization & Masking:** Applies string-transformation logic to redact sensitive fields while preserving basic structure for downstream analytics.
* **Name Pseudonymization:** Converts full customer names to compliant initials.
* **Compliance & Audit Verification:** Performs post-transformation validation to confirm zero residual PII leakage and prints an automated audit log.

---

## Technical Stack

* **Language:** Python 3.x
* **Core Libraries:** `pandas`, `re`, `numpy`
* **Environment:** Google Colab / Jupyter Notebook

---

## Project Structure & Workflow

1. **Raw Data Generation:** Simulates raw operational datasets containing unmasked sensitive customer attributes.
2. **PII Detection Engine:** Scans columns against predefined regex patterns and counts exposed records.
3. **Anonymization Pipeline:** Converts sensitive attributes into compliant masked formats:
   * **Email:** `rahul.sharma@example.com` $\rightarrow$ `r**********a@example.com`
   * **Phone:** `+91 9876543210` $\rightarrow$ `******3210`
   * **National ID:** `1234-5678-9012` $\rightarrow$ `****-****-9012`
   * **Name:** `Rahul Sharma` $\rightarrow$ `R. S.`
4. **Audit Reporting:** Generates a formal compliance summary log verifying dataset status (`COMPLIANT` / `NON-COMPLIANT`).

---

## How to Run

1. Open the project notebook in **Google Colab** or **Jupyter Notebook**.
2. Run all cells sequentially (`Cell 1` through `Cell 4`).
3. View the generated anonymized DataFrame and the printed **Data Privacy Audit & Compliance Report**.

---

## Sample Audit Output

```text
==================================================
         DATA PRIVACY AUDIT & COMPLIANCE REPORT   
==================================================
Total Records Processed : 5
Total Dataset Columns   : 7
Columns Flagged for PII : 3 ['Email', 'Phone', 'National_ID']
--------------------------------------------------
AUDIT STATUS & COMPLIANCE VERIFICATION:
[SUCCESS] 0 Unmasked PII fields detected.
[SUCCESS] Dataset Status: COMPLIANT (Safe for Distribution)
--------------------------------------------------
SUMMARY OF ACTIONS TAKEN:
 - Column 'Email': Masked & Anonymized successfully.
 - Column 'Phone': Masked & Anonymized successfully.
 - Column 'National_ID': Masked & Anonymized successfully.
==================================================
