# Optional stretch — turn any project into a one-click app

**This is optional and self-paced, for whoever has time left after finishing Easy and Medium.** It's not part of the guided, timed part of the day — don't feel behind if you don't get to it. The goal is to take one of today's projects (or your own Personal Build) from "a set of files Claude produces" to "a button someone in your business can actually click," without leaving this Codespace.

**Why this is worth doing:** everything so far has been you typing prompts into Claude Code directly. That's perfect for building and testing an automation, but it's not how a non-technical teammate would use it day to day. Wrapping it in a tiny web page with a button is the smallest possible step from "a build" to "a tool."

**The pattern is the same for any project** — Easy, Medium, or your own Personal Build. Pick the one you want to wrap, then follow this in the same Claude Code session:

**1. Ask Claude to build the app (10–15 min)**
```
Build a simple one-page Streamlit app called app.py in
project-X-your-folder/. It should have a single button labeled "Run the
agent". When clicked, it should run the exact same steps we just did by
hand in this session - read the data file(s) in this folder, apply the
same drafting/matching logic and the same guardrail we added, and
display the results on the page (use st.dataframe or st.markdown, not
just raw text). Use the anthropic Python SDK to call Claude, reading the
API key from the ANTHROPIC_API_KEY environment variable that's already
set in this session. If that key is missing or a call fails, show a
clear on-page message instead of crashing. Install whatever
dependencies are needed.
```
Replace `project-X-your-folder` with the project you're wrapping, e.g. `project-1-email-followup` or `project-2-invoice-processing`.

**2. Run it**
```
streamlit run project-X-your-folder/app.py
```
Codespaces will detect the port and pop up a "Open in Browser" notification — click it, or open the **Ports** tab at the bottom and click the forwarded address next to port 8501.

**3. Try it live**
Click the button in the browser. You should see the same kind of output you saw in the terminal earlier, now behind one click instead of a typed prompt.

**4. The guardrail still matters here too**
If you added a "never do X" rule earlier in the project, ask Claude to make sure the app enforces it too, the same way:
```
Make sure app.py enforces the same guardrail rule we added earlier - add
an actual code-level check (a regex or keyword scan on the drafted text,
not just asking the model to self-verify) that runs on every draft
before it's shown, since this version doesn't have a human reading
every draft first.
```

**After today:** like the Telegram bot, this app only runs while `streamlit run` is active in this Codespace. Turning it into something a teammate can open anytime (without you having the Codespace open) is a good 90-Day Roadmap item — it needs proper hosting, not something to solve today.
