# Claims Lifecycle & Key Concepts

A working reference for how a medical claim moves from the provider to payment, and the points where it usually breaks. When I research a claim ticket, I locate it on this path first, then look for the failure point.

## 1. The lifecycle

```
Patient visit
   │
   ▼
Eligibility & benefits check ──► (fails? → eligibility denial later)
   │
   ▼
Coding (CPT/HCPCS + ICD-10 + modifiers)
   │
   ▼
Claim created (CMS-1500 or UB-04) ──► Clearinghouse scrubbing
   │                                        │
   │                              Rejected (front-end) → fix & resubmit
   ▼
Payer receives claim (adjudication)
   │
   ├─► Paid in full
   ├─► Partially paid (contractual adjustment, patient responsibility)
   ├─► Pended (needs records, COB info, auth)
   └─► Denied (CARC/RARC on EOB/ERA)
   │
   ▼
Remittance (EOB / ERA 835) ──► Payment posting ──► Patient billing
   │
   ▼
Follow-up: corrected claim, reprocessing request, or appeal
```

**Rejection vs denial:** a *rejection* never entered the payer's system (format or data errors at the clearinghouse/front end) and is fixed and resubmitted. A *denial* was adjudicated and has a remittance code. It needs a corrected claim, a reprocessing request or an appeal.

## 2. Claim forms

| Form | Used by | Key fields I verify |
|---|---|---|
| **CMS-1500** (837P) | Professional: physicians, clinics, therapists | Box 1a member ID, Box 2 patient name, Box 11 group number, Box 21 ICD-10 codes, Box 24 lines (DOS, POS, CPT, modifiers, diagnosis pointer, charges, NPI), Box 33 billing NPI |
| **UB-04** (837I) | Institutional: hospitals, SNFs, outpatient facilities | Type of bill, admission/discharge dates, revenue codes, condition/occurrence codes, attending NPI |

## 3. Code sets

| Code set | Describes | Example of an issue I would catch |
|---|---|---|
| **ICD-10-CM** | Diagnosis (why) | Diagnosis does not support medical necessity for the billed service |
| **CPT** | Procedure / service (what) | Two codes billed that are bundled together (NCCI edit) |
| **HCPCS Level II** | Supplies, DME, drugs, ambulance | Missing units or wrong NDC |
| **Modifiers** | Change how a code is read (25, 59, 26, TC, LT/RT…) | Missing modifier 25 on an E/M billed with a same-day procedure |
| **POS** | Place of service | Office POS billed for a service done in an outpatient facility |
| **CARC / RARC** | Why a claim was adjusted or denied | See the [denials playbook](../denials-playbook) |

For a remittance explained line by line with real arithmetic, see the [EOB walkthrough](../eob-walkthrough).

## 4. Concepts I apply every day

- **Eligibility & benefits:** active coverage on the date of service, plan type, network status, deductible, copay and coinsurance.
- **Allowed amount:** what the payer recognizes for the service. *Billed − allowed = contractual adjustment* (in-network provider cannot bill the patient for it).
- **Patient responsibility:** deductible + copay + coinsurance (CARC group **PR**).
- **Coordination of Benefits (COB):** which plan is primary. Birthday rule for dependents; employer plan usually primary over Medicare for active employees at large employers.
- **Timely filing:** each payer has a deadline from the date of service (often 90–365 days). Proof of timely filing is the clearinghouse acceptance report.
- **Prior authorization:** required for some services. A missing auth usually produces a CO-197 denial.
- **EOB vs ERA:** the EOB is the human-readable explanation; the ERA (835) is the electronic version used for automatic posting.
- **Corrected claim vs appeal:** if the claim had *our* data error, send a corrected claim (frequency code 7, replacement). If the payer decided wrongly, file an appeal with supporting documentation.

## 5. My research order for a claim ticket

1. **Authenticate** the caller or ticket source and confirm the minimum necessary data.
2. **Find the claim:** member ID, DOS, billing NPI, claim number.
3. **Check status:** received? rejected? pended? paid? denied?
4. **Read the remittance:** CARC/RARC and group code (CO / PR / OA / PI).
5. **Compare against the source:** eligibility on DOS, auth on file, codes billed vs expected, contract rate.
6. **Find the root cause:** provider error, payer processing error, or member issue (COB, eligibility).
7. **Act:** reprocess/adjust, request a corrected claim, guide toward appeal, or escalate.
8. **Document** in the case-note format in [`templates/case-note-template.md`](../../templates/case-note-template.md).
