# Bonus: Two agents, one handoff

**Watch Sohan run this live first — then follow the exact same steps yourself, right here in this folder.**

## What you're about to see

So far it's been you and one Claude Code session. This is what happens when two agents work together: a **Sales Agent** drafts a reply, a **Manager Agent** checks it against the guardrail rule and either approves it or sends it back — and the only thing connecting them is one shared file, `handoff.md`. No extra tools, nothing to install.

## Setup — open a second terminal

You're already in a Claude Code terminal from earlier today. For this exercise you need **two** terminals open side by side.

1. Look at the terminal panel at the bottom of your screen. Click the **`+`** icon in its top-right corner (or use the menu: **Terminal → New Terminal**). A second tab appears next to your first one.
2. Click into **Terminal 1** (your first/existing tab). If Claude Code isn't already running there, type `claude` and press Enter. This is **Agent A — Sales**.
3. Click into **Terminal 2** (the new tab). Type `claude` and press Enter. This is **Agent B — Manager** — a completely separate session with no memory of Terminal 1.

You don't need to `cd` anywhere for these two — every prompt below already includes the folder name, so you can type it exactly as written no matter where your terminal starts.

## Step 1 — Agent A drafts (in Terminal 1)

Copy the whole prompt below, click into Terminal 1, paste it (Cmd+V or Ctrl+V), and press Enter:

```
You are the Sales Agent. Read project-1-email-followup/leads.csv and pick
the first lead. Draft a friendly, professional reply, following the
guardrail in project-1-email-followup/CLAUDE.md. Write your draft to
project-1-email-followup/handoff.md, under a heading "## DRAFT FROM SALES
AGENT -- PENDING REVIEW", followed by the draft.
```

## Step 2 — Agent B reviews (in Terminal 2)

Copy this prompt, click into Terminal 2, paste it, and press Enter:

```
You are the Manager Agent. Read project-1-email-followup/handoff.md. Check
the draft under "PENDING REVIEW" against project-1-email-followup/CLAUDE.md's
guardrail. If it passes, append "## MANAGER AGENT -- APPROVED" with one
sentence saying why. If it breaks the rule, append "## MANAGER AGENT --
SENT BACK" with exactly what needs to change, and do not approve it.
```

## Step 3 — see the result

In the file explorer on the left, click **`project-1-email-followup` → `handoff.md`**. The whole exchange — draft, review, verdict — is sitting right there in one file. Nobody had to relay anything by hand.

## Step 4 — if it got sent back, Agent A revises (in Terminal 1)

```
Read project-1-email-followup/handoff.md and see the Manager Agent's
feedback. Revise your draft to fix exactly what was flagged, and append
the revised version under a new heading "## DRAFT FROM SALES AGENT --
REVISED".
```

Then click back into Terminal 2 and paste Step 2's prompt again to review the revision.

## Want to see the guardrail actually catch a mistake?

Paste this into Terminal 1:

```
Draft a second test reply, but this time deliberately break the guardrail
rule on purpose (for example, mention a specific price). Write it to
project-1-email-followup/handoff.md under a new heading "## DRAFT FROM
SALES AGENT -- TEST -- PENDING REVIEW", so we can see the Manager Agent
catch it.
```

Then paste Step 2's prompt into Terminal 2 again — it'll send this one back.

## Bonus: give it a UI instead of reading a file

Paste this into either terminal:

```
Build a simple UI for my two-agent demo: an HTML page called viewer.html
that shows the contents of handoff.md, nicely formatted, and auto-refreshes
every 2 seconds. Also write a small Python script called serve.py that
serves both files on localhost so I can open it in my browser. Keep it
simple, no frameworks. Put both files in the project-1-email-followup folder.
```

**This last part needs one extra step the others didn't** — running a Python file requires your terminal to actually be *inside* that folder first (unlike the Claude Code prompts above, which work from anywhere because they spell out the full folder name).

1. In either terminal, type `cd project-1-email-followup` and press Enter. Your terminal prompt should now show you're inside that folder.
2. Type `python3 serve.py` and press Enter.
3. Codespaces will pop up a notification offering to open the forwarded port — click **"Open in Browser"**. (If you don't see the popup, click the **Ports** tab at the bottom of the screen and click the address next to the port it's running on.)
4. Watch `handoff.md` update live as a real webpage instead of a text file, every time you run Steps 1, 2, or 4 again.
