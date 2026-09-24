# Project 1 — Email & Lead Follow-Up Agent

## What this folder is for
Drafting replies to inbound customer leads and enquiries (`leads.csv`), flagging the urgent ones, and — once that works — running the same logic live as a Telegram bot.

## Standing rule — never break this
Never mention pricing or promise a specific delivery date in any reply you draft or send from this project. If pricing or a date comes up, say a team member will confirm that shortly instead. This applies to every draft, every time — no exceptions, and no "just this once."

## Tone
Friendly and professional. Match the length of your reply to the length of the original enquiry. Always end with one clear next step.

## Telegram-specific rule
If you're running as a live bot (`telegram_bot.py`), prefix every reply with `DRAFT REPLY (not sent to the customer):`. Never send a reply straight to a real customer without a human reading it first.
