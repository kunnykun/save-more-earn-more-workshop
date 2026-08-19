# Joint Build 3 — Meeting Notes → Action Items Agent

In your terminal:
```
cd ../project-3-meeting-notes
claude
```

**1. Look at the data**
```
Read meeting-transcript.txt and tell me in one sentence what this meeting was about.
```

**2. Extract action items**
```
Go through meeting-transcript.txt and pull out every action item mentioned -
who owns it and any deadline that was said out loud, even informally
("by Friday", "today"). Save this as a table in actions.md.
```

**3. Draft the recap**
```
Now draft a short recap email to send to everyone who attended, summarizing
the meeting in a few lines and listing their own action items clearly.
Save it as recap-email.md.
```

**4. Add a guardrail**
```
Add a rule: if an action item's owner or deadline isn't clearly stated in
the transcript, mark it "NEEDS CONFIRMATION" instead of guessing. Check
actions.md against this rule and fix anything that guessed.
```

Open `actions.md` and `recap-email.md` when you're done to see the results.
