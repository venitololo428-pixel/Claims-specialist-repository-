# Denials & Discrepancies Playbook

How I approach the most common denial and discrepancy types. Each entry gives the usual root cause, what I check, and the next action. Codes are standard X12 Claim Adjustment Reason Codes (CARC); always confirm the current code description and the payer's own policy before acting.

## Group codes first

| Group | Meaning | Who owes it |
|---|---|---|
| **CO** | Contractual Obligation | Provider writes off; cannot bill patient |
| **PR** | Patient Responsibility | Patient (deductible, copay, coinsurance) |
| **OA** | Other Adjustment | Neither; often COB or informational |
| **PI** | Payer Initiated reduction | Provider, but not contractual; often appealable |

## Common denials

| CARC | Meaning (short) | Usual root cause | What I check | Next action |
|---|---|---|---|---|
| **1 / 2 / 3** | Deductible / coinsurance / copay | Correct cost-sharing applied | Benefits accumulators for the plan year | Explain to provider; bill patient. No error. |
| **4** | Modifier inconsistent / missing | Wrong or missing modifier (e.g. 25, 59, LT/RT) | Lines on claim vs documentation | Corrected claim with proper modifier |
| **16** | Missing / incorrect information | Missing NPI, invalid ID, missing DOS detail | RARC that comes with it (it says *which* field) | Corrected claim with the field fixed |
| **18** | Exact duplicate | Resubmitted instead of corrected | Original claim status and claim number | Do not resubmit. Follow up on original or send replacement (freq. 7) |
| **22** | Covered by another payer (COB) | Payer is secondary or COB not updated | COB on file, other insurance info, birthday rule | Bill primary first; ask member to update COB |
| **27** | Expenses after coverage ended | Terminated eligibility on DOS | Eligibility history, retro terms | Verify with member; bill new coverage or patient |
| **29** | Timely filing expired | Submitted past payer deadline | First submission date, clearinghouse acceptance report | Appeal with proof of timely filing, or write off |
| **45** | Charge exceeds fee schedule | Normal contractual reduction | Contract rate vs allowed | Explain; write off difference (CO) |
| **50** | Not medically necessary | Diagnosis does not support service | ICD-10 vs CPT, payer medical policy | Appeal with records / letter of medical necessity |
| **96 / 204** | Non-covered service | Benefit exclusion | Plan document / SBC | Explain; patient responsibility if waiver signed |
| **97** | Bundled into another service | NCCI edit / global period | Procedure pairs, global surgery days | Modifier 59/XS if truly separate, otherwise accept |
| **109** | Not covered by this payer | Claim sent to wrong payer / plan | Member's current carrier | Redirect to correct payer |
| **197** | Precert / authorization absent | No auth or auth mismatch | Auth number, dates and units authorized | Retro-auth if allowed; else appeal |
| **242** | Services not provided by network provider | Out-of-network or wrong billing NPI | Network / credentialing status of NPI and TIN | Check credentialing; correct NPI or apply OON benefits |

## Discrepancy types (paid, but paid wrong)

| Discrepancy | How I spot it | Resolution path |
|---|---|---|
| **Underpayment** | Allowed < contract rate for the CPT | Reprocessing request with contract rate reference |
| **Overpayment** | Paid twice / paid on termed member | Overpayment recovery or refund request, documented |
| **Wrong patient responsibility** | Accumulators not updated; PR higher than plan design | Adjustment after accumulator correction |
| **Payment to wrong provider / TIN** | Payee on ERA does not match billing entity | Void and reissue; verify provider demographics |
| **Missing payment** | ERA shows paid, provider has no deposit | Trace check / EFT; confirm bank info on file |

## Escalation rules I follow

Escalate instead of resolving at first level when:
- The fix needs a **system or configuration change** (fee schedule loaded wrong, benefit coded wrong). Many claims are affected, not just one.
- The case involves **potential fraud, waste or abuse**.
- An **appeal deadline** is close and the provider needs a formal determination.
- The provider has called **repeatedly** about the same claim without resolution.
- Any **privacy concern** (wrong data disclosed, unverified caller insisting on PHI).
