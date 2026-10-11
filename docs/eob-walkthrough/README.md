# Reading an EOB / ERA: Worked Example

A remittance line by line, with the math. Being able to explain every dollar on a remittance is the core skill behind most provider and member calls: "why did you pay this much?"

> Fictional claim. In-network provider, member plan with **$500 deductible ($450 already met this year)**, **20% coinsurance**, no office copay.

## The remittance

| Line | CPT | Billed | Allowed | Group / CARC | Adjustment | Deductible | Coinsurance | Plan paid |
|---|---|---|---|---|---|---|---|---|
| 1 | 99214 (office visit, est. patient) | $250.00 | $140.00 | CO-45 · PR-1 · PR-2 | $110.00 | $50.00 | $18.00 | $72.00 |
| 2 | 87880 (rapid strep test) | $40.00 | $18.00 | CO-45 · PR-2 | $22.00 | $0.00 | $3.60 | $14.40 |
| **Total** | | **$290.00** | **$158.00** | | **$132.00** | **$50.00** | **$21.60** | **$86.40** |

**Patient responsibility:** $50.00 + $21.60 = **$71.60**

## Line 1, step by step

1. **Billed $250.00 → allowed $140.00.** The in-network contract recognizes $140.00.
   The $110.00 difference is **CO-45** (charge exceeds fee schedule). Provider writes it off and **cannot bill the member** for it.
2. **Deductible.** The member had $500 − $450 = **$50.00** left. It is applied first → **PR-1 $50.00**.
3. **Coinsurance.** Remaining allowed: $140.00 − $50.00 = $90.00. Member pays 20% → **PR-2 $18.00**.
4. **Plan pays** the rest: $90.00 − $18.00 = **$72.00**.

Check: $110.00 + $50.00 + $18.00 + $72.00 = **$250.00** ✔ (every billed dollar is accounted for)

## Line 2, step by step

1. Billed $40.00 → allowed $18.00 → **CO-45 $22.00**.
2. Deductible is now met (line 1 used the last $50), so **$0.00** deductible.
3. Coinsurance 20% × $18.00 = **PR-2 $3.60**.
4. Plan pays $18.00 − $3.60 = **$14.40**.

Check: $22.00 + $3.60 + $14.40 = **$40.00** ✔

## The balancing rule

For every line and for the claim total:

```
Billed = Contractual adjustment (CO) + Patient responsibility (PR) + Plan paid (+ other adjustments OA/PI)
```

If the line does not balance, something is wrong: a missing adjustment, a posting error, or a processing error worth a reprocessing request.

## How I would explain it on the phone

**To the provider:** "Line one allowed $140 under your contract. $50 went to the member's remaining deductible, $18 is 20% coinsurance, and we paid $72. The $110 difference is a contractual adjustment under CO-45 and isn't billable to the patient."

**To the member:** "Your doctor's office can bill you $71.60 in total: $50 that finished your deductible for the year and $21.60 of coinsurance. From now on you only pay the 20% coinsurance on covered services, until you reach your out-of-pocket maximum."
