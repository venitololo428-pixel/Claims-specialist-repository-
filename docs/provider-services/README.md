# Provider Services Workflow

How I handle a provider inquiry from first contact to a closed ticket.

## 1. Authenticate

Before discussing any claim, verify the caller represents the provider:
- Provider **NPI** and **Tax ID (TIN)**
- Caller name and role (billing office, clearinghouse, practice manager)
- For claim detail: member ID **plus** member name and date of birth

Disclose only the **minimum necessary** information for the question asked.

## 2. Classify the inquiry

| Type | Typical question | Where I look |
|---|---|---|
| Claim status | "Did you receive it? Is it paid?" | Claims system, clearinghouse status |
| Denial / adjustment | "Why was this denied / reduced?" | Remittance CARC/RARC → [playbook](../denials-playbook) |
| Payment | "We never got the check / EFT" | Payment trace, payee info, bank data on file |
| Eligibility & benefits | "Is the patient covered for X?" | Eligibility on DOS, plan benefits |
| Authorization | "Do we need auth? Is it approved?" | Auth system, service code list |
| Network / credentialing | "Are we in network?" | Provider directory, credentialing status by NPI/TIN |
| Demographics | Address, TIN or banking change | Provider data team (requires written request) |

## 3. Resolve or route

- **First-contact resolution** when the answer is in the system: status, explanation of a correct denial, eligibility.
- **Adjust / reprocess** when the error is ours and inside my authority.
- **Escalate** with a complete note when it needs another team (pricing, configuration, appeals, credentialing, SIU).

## 4. Document

Every ticket closes with a note that someone else can read six months later without calling anyone:

1. Who contacted and how they were verified
2. What they asked (claim #, DOS)
3. What I found (facts, codes, amounts)
4. What I did and why
5. Next step, owner and date / reference number

Template: [`templates/case-note-template.md`](../../templates/case-note-template.md)

## 5. Queue management habits

- Work the queue by **SLA due date and aging**, not by arrival order alone.
- Group tickets for the **same provider or same issue**; one root cause often closes several tickets.
- Set **follow-up dates** on anything pended; never leave a ticket without a next action.
- Track my own volume, aging and reopen rate in a simple tracker ([`templates/claims-queue-tracker.xlsx`](../../templates/claims-queue-tracker.xlsx)).
