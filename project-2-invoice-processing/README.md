# MEDIUM — Invoice Processing Agent (Accounts Payable)

Same session, same shape as Easy — read data, draft output, add judgment, add a guardrail. New scenario this time: instead of writing to a customer, you're checking a **supplier invoice against the purchase order (PO) it should match**, and preparing what goes to your accountant.

**The business problem:** a supplier invoice arrives. Before it gets paid, someone has to check it actually matches what was ordered — right item, right quantity, right price. Done by hand, this is slow and error-prone, and mismatches that slip through cost real money. This is the classic "PO matching" step every accounts payable process needs.

**About the CLAUDE.md file in this folder:** it already has today's guardrail written into it — Claude Code reads it automatically, so the rule from step 4 below is already active before you even reach that step.

**0. Just keep typing (2 min)** — same Claude Code session as Easy, no restart.

**1. Look at both files together (5 min)**
```
Read project-2-invoice-processing/purchase-orders.csv and
project-2-invoice-processing/incoming-invoices.csv. In one or two
sentences, tell me what each file represents and how they're meant to
relate to each other.
```
*Teaching point:* Claude should notice on its own that invoices reference PO numbers — set up the next step by asking the room "what would you personally check first if you were doing this by hand?"

**2. Match and classify (8 min)**
```
For each invoice in project-2-invoice-processing/incoming-invoices.csv,
find the matching purchase order in
project-2-invoice-processing/purchase-orders.csv by PO number, and
compare item description, quantity, and unit price. Classify each
invoice as one of: MATCH (everything agrees), PRICE MISMATCH, QUANTITY
MISMATCH, or NO PO FOUND. Save the results as a table in
project-2-invoice-processing/match-report.md, including the exact
difference for any mismatch (e.g. "invoiced at $92.00 vs PO price of
$85.00").
```
*Teaching point:* open `match-report.md` together. This data has all four cases on purpose — walk through one of each so the room sees Claude isn't just diffing numbers, it's applying the same judgment an AP clerk would.

**3. Draft what goes to the accountant (7 min)**
```
Using project-2-invoice-processing/match-report.md, draft two things and
save them to project-2-invoice-processing/accountant-email.md:
1. An email listing every MATCHED invoice, recommending them for
   payment.
2. A separate email flagging every mismatched or unmatched invoice,
   explaining exactly what's wrong with each one and recommending they
   be held for manual review before paying.
Keep both emails short, clear, and professional - this is going to a
real accountant, not the supplier.
```
*Teaching point:* this is the moment to point out the agent isn't just summarizing, it's making a payment recommendation — which is exactly why the next step matters.

**4. Add a guardrail (5 min)**
```
Add a rule: never recommend an invoice for payment if there is any
discrepancy at all, even a small one - it must go to the "hold for
review" list instead, no exceptions. Check
project-2-invoice-processing/accountant-email.md against this rule and
fix anything that breaks it.
```
*Teaching point:* the core "lessons learned" message, same as Easy — a useful agent needs firm boundaries around money and payments especially. Ask the room: what's a rule *their* business would need before anything gets auto-approved?

**5. Review as a group (3 min)** — open `match-report.md` and `accountant-email.md`, take two or three questions.

---

**Optional stretch, if time allows:** turn this into a one-click app instead of a set of files — see `materials/bonus-build-a-ui.md` for the generic pattern, which works for this project too.
