# REF: case_study_1
**LIVE DEMO**: IN-PROGRESS

**How the System works in common language tone**

Imagine you run a **health insurance office**.  
Every day, **hospitals and clinics send you claims** (bills for services).  

But here’s the challenge:  

- Each hospital uses a **different format** to send their claims (some in tables, some in JSON-like forms).  
- Many claims get **denied** for various reasons:  
  - ❌ Missing paperwork  
  - ❌ Wrong doctor info
  - ❌ Expired authorization  

Some denied claims can be **fixed and resubmitted**, while others are **dead ends** and need manual review.  

---

## 🧑‍💼 Our Pipeline is Like a Smart Clerk

1. **Collects all claims**  
   → No matter what form they come in.  

2. **Translates them into a single format**  
   → All documents follow the same template:  
   `Claim ID | Patient ID | Reason for Denial | Status | …`  

3. **Checks each claim against rules**  
   → Decides if it can be **resubmitted automatically** or needs **manual review**.  

   **Rules:**
   - 🟢 Fixable → Auto-resubmit  
     - Missing patient ID (but not exclusively)
     - Expired authorization (date) → request new one  
     - Inferred fixes
       - Incorrect NPI → correct it
       - Missing modifier → add it  
   - 🔴 Not Fixable → Manual review
     - Wrong procedure code  

---

## 📦 What the System Produces

- **Clean Book** → all claims standardized in one format.  
- **Resubmission List** → only claims that are fixable and ready to send back.  

---

## 📊 Tracking & Logs

The system keeps notes, like:  
> “I saw **9 claims**, **7 denied**, **5 can be resubmitted**.”

---