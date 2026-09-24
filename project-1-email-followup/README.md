# EASY — Email & Lead Follow-Up Agent (and putting it live on Telegram)

You're already in a running Claude Code session from the setup steps - stay right there, no need to restart it. Just type each prompt below into the same session, one at a time, and press Enter. Read the output before moving to the next one.

**About the CLAUDE.md file in this folder:** Claude Code reads any file called `CLAUDE.md` automatically, every time, without you having to say anything. This folder already has one with today's guardrail rule already written in — so even before you type step 4 below, the rule is already active. It's a preview of how you'd do this for real in your own business: write the rule once, and it applies to every future conversation, not just this session.

**1. Look at the data**
```
Read project-1-email-followup/leads.csv and give me a one-line summary of each enquiry.
```

**2. Draft the replies**
```
For each lead in project-1-email-followup/leads.csv, draft a personalized
reply. Keep the tone friendly and professional, match the length of
their reply to the length of their enquiry, and always end with one
clear next step. Save the drafts to project-1-email-followup/replies.md,
one per lead.
```

**3. Add urgency triage**
```
Now go back through project-1-email-followup/leads.csv and flag any
enquiry that sounds urgent or high-value - anything mentioning a
deadline, a breakdown, a large budget, or visible stress. Add a priority
column (High/Normal) to a new file
project-1-email-followup/leads_prioritized.csv, and explain your
reasoning for each High flag in one line.
```

**4. Add a guardrail**
```
Add a rule: never mention pricing or promise a specific delivery date in
any reply - instead say a team member will confirm that shortly. Check
every draft in project-1-email-followup/replies.md against this rule and
fix any that break it.
```

Open `replies.md` and `leads_prioritized.csv` to see the results.

---

**5. Take it live on Telegram**

Everything so far has produced files - this step takes the exact same agent and puts it somewhere a real enquiry could actually reach it: a live chat bot on your phone. **You'll need Telegram installed** (free, App Store / Google Play) - if you set it up from the pre-workshop email, you're ready.

**5a. Create your bot (3 min)**
Open Telegram, search for **@BotFather**, and message it:
```
/newbot
```
Follow the prompts (pick a name, pick a username ending in "bot"). BotFather replies with a token that looks like `123456789:ABCdefGhIJKlmNoPQRsTUVwxyz`. Copy it.

**5b. Add the token (1 min)**
Open `.env`, add a new line:
```
export TELEGRAM_BOT_TOKEN="paste-your-token-here"
```
Save, then in the terminal run `source .env` again.

**5c. Ask Claude to build it (10 min)**
Same session, same style of prompt as everything else today:
```
Write a small Python script called telegram_bot.py that connects to my
Telegram bot using the python-telegram-bot library and the
TELEGRAM_BOT_TOKEN environment variable. For every message it receives,
it should draft a reply using the same tone and rules we used in
project-1-email-followup - friendly, professional, one clear next step,
never mentioning pricing or a specific delivery date - and reply with
"DRAFT REPLY (not sent to the customer):" followed by the draft. Use
polling, not webhooks, so it's simple to run. Install whatever
dependencies are needed.
```
Let Claude write the file and install what it needs.

**5d. Run it and test it (5 min)**
```
python telegram_bot.py
```
Leave that running, open Telegram on your phone, find your bot, and send it a message like a real customer enquiry. Watch it reply live.

*Teaching point:* the "DRAFT REPLY (not sent to the customer)" prefix isn't an accident - it's the same guardrail lesson as step 4, just more important now that the agent is wired to something live. A human-in-the-loop step before anything actually reaches a real customer matters even more here. A good next step for later: have it forward drafts to *you* instead of replying in the same chat, so you approve before anything goes out.

**After today:** this bot only keeps running while `python telegram_bot.py` is active in this Codespace. To keep it running permanently, it needs to be deployed somewhere that stays on - a good 90-Day Roadmap item, not something to solve today.

---

**Optional stretch, if time allows:** turn this into a one-click app instead of typed prompts - see `materials/bonus-build-a-ui.md`.
