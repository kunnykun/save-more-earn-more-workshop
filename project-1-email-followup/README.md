# Joint Build 1 — Email & Lead Follow-Up Agent

In your terminal:
```
cd project-1-email-followup
claude
```

Then, one at a time, type each prompt below and press Enter. Read the output before moving to the next one.

**1. Look at the data**
```
Read leads.csv and give me a one-line summary of each enquiry.
```

**2. Draft the replies**
```
For each lead in leads.csv, draft a personalized reply. Keep the tone
friendly and professional, match the length of their reply to the length
of their enquiry, and always end with one clear next step. Save the
drafts to replies.md, one per lead.
```

**3. Add urgency triage**
```
Now go back through leads.csv and flag any enquiry that sounds urgent or
high-value - anything mentioning a deadline, a breakdown, a large budget,
or visible stress. Add a priority column (High/Normal) to a new file
leads_prioritized.csv, and explain your reasoning for each High flag in
one line.
```

**4. Add a guardrail**
```
Add a rule: never mention pricing or promise a specific delivery date in
any reply - instead say a team member will confirm that shortly. Check
every draft in replies.md against this rule and fix any that break it.
```

Open `replies.md` and `leads_prioritized.csv` when you're done to see the results.
