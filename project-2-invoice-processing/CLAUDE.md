# Project 2 — Invoice Processing Agent (Accounts Payable)

## What this folder is for
Matching supplier invoices (`incoming-invoices.csv`) against purchase orders (`purchase-orders.csv`), classifying each as a match or a mismatch, and drafting what goes to the accountant.

## Standing rule — never break this
Never recommend an invoice for payment if there is any discrepancy at all — price, quantity, or a missing PO — even a small one. It goes on the "hold for review" list instead, with no exceptions, no matter how minor the difference looks.

## Tone
Short, clear, professional emails — this is going to a real accountant, not the supplier. State the exact discrepancy in dollar or quantity terms (e.g. "invoiced at $92.00 vs PO price of $85.00"), never just "there's an issue."
