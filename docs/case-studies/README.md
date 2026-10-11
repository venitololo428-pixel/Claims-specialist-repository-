# Case Studies (De-identified Practice Cases)

> All names, member IDs, NPIs, claim numbers and amounts below are **fictional**. The cases reproduce common issue types in claims and provider services to show how I research, decide and document. They are not records of real claims.

Each case follows the same audit-ready structure I use for real tickets: **Issue → Research → Root cause → Action → Documentation**.

## Summary

| # | Case | Root cause | Outcome |
|---|---|---|---|
| 1 | [Duplicate denial (CARC 18)](#case-1--duplicate-denial-after-a-resubmission-carc-18) | Provider resubmitted a pended claim | Original claim kept open; provider sent records instead of a new claim |
| 2 | [COB denial for a dependent (CARC 22)](#case-2--cob-denial-for-a-dependent-carc-22) | Billed secondary plan first | Birthday rule applied; provider redirected to primary plan |
| 3 | [Underpayment against contract](#case-3--underpayment-against-contract) | Fee schedule not updated (payer error) | Pattern escalated across 6 claims; provider underpayment recovered |
| 4 | [Authorization mismatch (CARC 197)](#case-4--missing-authorization-carc-197-that-was-actually-on-file) | Auth for one CPT, claim billed another | Clear path to auth update / retro review |
| 5 | [Deductible applied twice](#case-5--patient-responsibility-looks-too-high-accumulators) | Accumulator not updated after reprocessing | Accumulator corrected; member overcharge prevented |

---

## Case 1 — Duplicate denial after a resubmission (CARC 18)

**Issue.** A provider office calls: a follow-up visit claim was denied as a duplicate. They say it was "never paid".

**Research.**
- Claim A (original), DOS 03/04: status *pended*, waiting for medical records requested 25 days earlier.
- Claim B, same DOS, same CPT 99214: denied CARC 18 (exact duplicate).
- The office never sent the records. Instead it resubmitted the claim after 3 weeks.

**Root cause.** Provider workflow: resubmitting a pended claim creates a duplicate. The original was never denied.

**Action.** Explained that Claim B is correctly denied and that Claim A is still open. Gave the fax/portal route for records and the deadline to send them. Asked them not to resubmit again.

**Documentation (case note).**
> Prov office called re: CLM B denied CARC 18. Original CLM A same DOS/CPT pended for med records (req'd 03/10). Records not rec'd. Advised CLM B correctly denied as dup; submit records for CLM A via portal by 04/09. Advised no further resubmission. No adjustment needed. Follow-up flag set 04/10.

---

## Case 2 — COB denial for a dependent (CARC 22)

**Issue.** A pediatric claim for a 6-year-old dependent is denied: "covered by another payer".

**Research.**
- Child is covered under both parents' employer plans.
- Our plan holds the father's coverage (birthday in **October**); the mother's birthday is in **March**.
- Birthday rule: the parent whose birthday falls **earlier in the calendar year** is primary → mother's plan is primary.
- COB questionnaire on file confirms the other coverage.

**Root cause.** Correct adjudication. The provider billed the secondary plan first.

**Action.** Guided provider to bill mother's plan as primary, then send the primary EOB to us for secondary consideration.

**Documentation.**
> Prov inquiry re: CARC 22 on dep claim. Dep has dual coverage; per birthday rule other plan is primary (subscriber DOB March vs ours Oct). COB verified on file. Denial correct. Advised bill primary, then submit with primary EOB for secondary. No adjustment.

---

## Case 3 — Underpayment against contract

**Issue.** An in-network physical therapy clinic reports that CPT 97110 (therapeutic exercise, 4 units) is being paid lower than its contract.

**Research.**
- Allowed on ERA: **$20.00 per unit**. Contract rate for 97110: **$27.50 per unit**.
- Checked 5 more recent claims from the same TIN: all priced at $20.00 → same pattern.
- Fee schedule update effective 01/01 was loaded for the previous year's rate.

**Root cause.** Payer error: fee schedule configuration, affecting multiple claims.

**Action.** Did not adjust only one claim. Escalated to the configuration/pricing team with the list of affected claims, then requested reprocessing once the fee schedule was corrected. Gave provider the ticket reference and expected timeline.

**Impact (fictional figures).** $7.50 × 4 units = **$30.00 per claim**; across 6 identified claims = **$180.00** recovered for the provider, plus future claims priced correctly.

**Documentation.**
> TIN XXXX reports UP on 97110. ERA allowed $20.00/unit vs contract $27.50/unit. Pattern confirmed on 6 claims since 01/01 (list attached). Root cause: FS not updated. Escalated to pricing, ref PRC-0000. Reprocess after correction. Prov advised of ref # and 10 bus. day estimate.

---

## Case 4 — Missing authorization (CARC 197) that was actually on file

**Issue.** An MRI claim is denied for missing precertification. The provider insists they had an authorization.

**Research.**
- Auth found on file: valid dates, approved for CPT **73721** (MRI lower joint, **without** contrast).
- Claim billed CPT **73723** (without **and** with contrast).
- The service changed during the visit; the auth was never updated.

**Root cause.** Code mismatch between auth and claim. The provider must update the authorization or show why the change was needed.

**Action.** Explained the mismatch line by line. Told the provider how to request an auth update / retro-review with the radiology report, and the appeal route if refused.

**Documentation.**
> CARC 197 on MRI claim. Auth on file for 73721; claim billed 73723. Denial correct as billed. Advised prov to request auth modification/retro review w/ radiology report, then reprocess. Appeal rights explained.

---

## Case 5 — Patient responsibility looks too high (accumulators)

**Issue.** A member calls: she paid her deductible in full but a new claim applied **$400** to deductible again.

**Research.**
- Plan deductible: **$1,500** individual.
- Claims history: three earlier claims applied **$600 + $500 + $400 = $1,500** to deductible.
- Accumulator shows only **$1,100** met. One claim was reprocessed and its $400 was not re-added.

**Root cause.** Accumulator not updated after a reprocessing. Processing error.

**Action.** Requested accumulator correction and readjustment of the new claim. The $400 moves from PR (deductible) to plan payment, subject to coinsurance. Told the member to wait for a corrected EOB before paying the provider.

**Documentation.**
> Mbr verified (3 identifiers). Disputes $400 ded on latest claim. Ded met per claims hx ($1,500) but accumulator shows $1,100 after reprocess of earlier claim. Accumulator correction req'd ref ACC-0000; latest claim to be readjusted. Mbr advised to wait for corrected EOB.

---

### What these cases show

- I read the remittance **and** the source (auth, contract, eligibility, COB) before deciding.
- I separate **provider errors**, **payer errors** and **correct denials**, and I explain each one clearly.
- When one claim points to a **systemic** issue, I escalate the pattern instead of fixing one claim at a time.
- My notes are short, factual and audit-ready: what was asked, what I found, what I did, what happens next.
