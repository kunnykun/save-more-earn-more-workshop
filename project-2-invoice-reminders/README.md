# Joint Build 2 — Invoice & Payment Reminder Agent

In your terminal:
```
cd ../project-2-invoice-reminders
claude
```

**1. Look at the data**
```
Read invoices.csv and summarize which customers are overdue and by how much.
```

**2. Draft tone-matched reminders**
```
Draft a payment reminder email for each overdue invoice in invoices.csv.
Use a gentle, friendly tone for customers marked as first-time-late or
with a good payment history, and a firmer but still professional tone
for repeat late payers. Save the drafts to reminders.md.
```

**3. Escalation list**
```
Identify the 2-3 worst cases - highest amount overdue combined with a
poor payment history - and draft a short note to me (not the customer)
recommending I call them personally instead of emailing, with talking
points for the call.
```

**4. Add a guardrail**
```
Add a rule: never threaten legal action or mention debt collection in
any reminder - every message stays professional and relationship-
preserving. Check all drafts against this rule and fix any that don't
comply.
```

Open `reminders.md` when you're done to see the results.
