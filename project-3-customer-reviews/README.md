# Customer Review Response Agent

Same session, same shape as the first two builds - read the data, draft the output, add judgment, add a guardrail. New scenario this time: your business just got a batch of new online reviews across Google, Facebook, and Yelp, and they all need a response - without a real reply taking half your day, and without a bad review turning into a worse one.

**The business problem:** reviews shape your reputation before a customer ever picks up the phone. Most owners either ignore reviews (looks like they don't care) or reply to everything with the same generic line (looks like they don't actually read them). Worse, a defensive or over-promising reply to a bad review usually does more damage than the review itself. This builds an agent that reads each review on its own terms, replies in the right tone for what actually happened, and knows the one rule that matters most: some reviews need a written reply, and some need a phone call, not a public reply.

**About the CLAUDE.md file in this folder:** this one already has today's guardrail written into it — Claude Code reads it automatically, so the rule from step 4 below is already active before you even reach that step.

**0. Just keep typing (2 min)** - same Claude Code session as before, no restart.

**1. Look at the data (4 min)**
```
Read project-3-customer-reviews/reviews.csv and give me a one-line
summary of the spread - how many reviews, what ratings, which
platforms.
```
*Teaching point:* ask the room "which one or two of these would you personally worry about most, if this landed in your inbox?" - hold their answers in mind for step 3.

**2. Draft the replies (8 min)**
```
For every review in project-3-customer-reviews/reviews.csv rated 4 or 5
stars, draft a warm, specific thank-you reply that references something
actual from their review - not a generic "thanks for your feedback."
For every review rated 2 or 3 stars, draft a calm, non-defensive reply
that acknowledges the specific issue without making excuses or getting
defensive. Save every draft to
project-3-customer-reviews/draft-replies.md, one per review, labelled
with its review_id.
```
*Teaching point:* open `draft-replies.md` together - the room should immediately feel the tone difference between a 5-star reply and a 2-star reply, and notice Claude isn't being defensive on the critical ones.

**3. Flag what needs a phone call, not a reply (7 min)**
```
Now go back through project-3-customer-reviews/reviews.csv and flag any
review that describes property damage, a safety concern, a request for
a refund, or a threat to report or escalate - these need a phone call
from a real person, not a public reply. Save this as
project-3-customer-reviews/needs-a-call.md, listing the review_id,
exactly what's concerning, and a one-line reason it can't just get a
written reply.
```
*Teaching point:* this is the same triage judgment as Easy's urgency flag and Medium's mismatch classification - same shape, new domain. This data has two "needs a call" cases on purpose, for two different reasons (damage-and-refund vs. a safety concern) - worth pointing out that "serious" doesn't always look the same.

**4. Add a guardrail (5 min)**
```
Add a rule: never write a public reply that admits fault, mentions
compensation or refunds, or promises a specific fix or timeline - a real
person handles anything like that by phone or private message instead.
Check every draft in project-3-customer-reviews/draft-replies.md against
this rule and rewrite any that break it, so they acknowledge the issue
and say the business will be in touch directly, without promising
anything measurable.
```
*Teaching point:* same core lesson as the other two builds, different reason this time - public replies are permanent and can be read as an admission, so anything with a real consequence (money, a fix, a timeline) has to move to a private, human conversation. Ask the room: where else in their business does "put it in writing" vs. "pick up the phone" matter?

**5. Review as a group (3 min)** - open `draft-replies.md` and `needs-a-call.md`, take two or three questions.

---

**Optional stretch, if time allows:** turn this into a one-click app instead of a set of files - see `materials/bonus-build-a-ui.md` for the generic pattern, which works for this project too.
