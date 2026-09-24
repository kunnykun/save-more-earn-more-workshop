# Bonus pattern — Meeting Notes → Action Items Agent

Optional — try this if you finish all three joint builds early and want another pattern before Personal Build, or if your own task fits this shape better than any of today's three projects. Same Claude Code session as before - keep going, no restart needed.

**1. Look at the data**
```
Read bonus-meeting-notes/meeting-transcript.txt and tell me in one
sentence what this meeting was about.
```

**2. Extract action items**
```
Go through bonus-meeting-notes/meeting-transcript.txt and pull out
every action item mentioned - who owns it and any deadline that was said
out loud, even informally ("by Friday", "today"). Save this as a table
in bonus-meeting-notes/actions.md.
```

**3. Draft the recap**
```
Now draft a short recap email to send to everyone who attended,
summarizing the meeting in a few lines and listing their own action
items clearly. Save it as bonus-meeting-notes/recap-email.md.
```

**4. Add a guardrail**
```
Add a rule: if an action item's owner or deadline isn't clearly stated in
the transcript, mark it "NEEDS CONFIRMATION" instead of guessing. Check
bonus-meeting-notes/actions.md against this rule and fix anything
that guessed.
```

Open `actions.md` and `recap-email.md` when you're done to see the results.
