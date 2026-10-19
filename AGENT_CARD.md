# Problem Set 05 | Running Agents on Zapier 

Student: Keziah Sherlyn Vanessa Vickraman · Course: MGMT 6110 · Problem Set 5

Vercel link: https://mgmt6110problemset05zapier.vercel.app/

### AGENT CARD - what it does and does NOT do
My agent card | Full-Court Press | finished *[18 October 23:28:47]*
1. The job: Emails each new WNBA news story to the league office’s communications manager (role-played by me) so no story is missed before media calls
2. The trigger: A new item in a Google News RSS search for “WNBA” (RSS by Zapier, New Item in Feed)
3. The tools: RSS by Zapier (New Item in Feed); Email by Zapier (Send Outbound Email)
4. It must never: Email anyone but me — the To field is fixed to my own address, with no mapped recipient
5. Where a person checks: The comms manager reviews all alerts at 10 AM daily and decides whether the league responds; Zap history is audited weekly against the feed
---

### Tricky case 
`Tricky case`: 
--> fake live-stream pages in the news feed

--> Expectation written: 18 October 23:55, before the next WNBA Finals game

`What I am testing`: 
Full-Court Press forwards every new item in a Google News
search for “WNBA.” I want to see what it does with items that match the search
but are not news, such as fake “WATCH LIVE NOW” streaming pages posted around
game time. *Four of these already slipped into my first 37 runs.*

`What I expect`: 
- On the next game day, I expect the Zap to forward fake streaming
pages to the comms inbox as if they were news stories. The Zap matches keywords, not quality, so any page with “WNBA” in its title counts as a new item. 
- I expect each one to appear in Zap history as a successful run, because technically nothing went wrong.

`Why it matters`: 
- A league comms manager would waste review time on spam, and
the links could lead to scam or illegal streaming sites. A run marked “success”
is not the same as a useful alert.

`Planned fix`: 
- Add exclusion terms to the feed URL (-stream -watch -live), test the new URL in a browser and in Zapier’s Find new records before publishing, then republish.

`How I checked the fix`: On Monday 19 October, I compared Zap history before and after the fix and counted how many fake streaming pages came through.

`What happened`: 
- My expectation held. That morning, before the fix, fake pages were still delivered as successful runs (‘[WATCHLIVE]TV!]’ at 11:34 AM and ‘WNBA Basketball Reddit Streams’ at 12:04 PM).
- I tested the new feed URL at 12:24 PM and published it as version 5 at 1:44 PM. None of the 22 runs between 1:46 and 2:44 PM was a streaming page, and real news still came through (a Cathy Engelbert story at 2:03 PM).
- One side effect: at 2:09 PM, a batch of 15 older stories (published between 25 August and 17 October) fired after republishing.
---

### Question 1 Answer
(a) **My quadrant**. Full-Court Press sits in AI alone, with checks (bottom left).

(b) The two questions. 
1. First, is there a right answer? 
--> **Yes**. The agent’s job is to relay every new item in a Google News feed for “WNBA” to the league comms inbox, accurately and once. Each run can be checked as right or wrong. In my first run at 11:28 PM on 18 October, the headline, publish date and link in the email matched the feed item exactly, which shows a correct relay. The failures are just as clear: of 37 runs, 27 were throttled by Email by Zapier’s sending limit and never delivered, three stories triggered twice (the repeat runs were throttled), and some “new” items were weeks old. Every success and failure can be checked against Zap history, which is what work with a right answer looks like.

2. Second, must people and AI do it together? 
--> **No**, either can do it alone. All 37 runs finished with no human input during the run. A person could also do the job alone by checking Google News every hour. Nothing in the process requires a person’s judgment before a run can finish.

(c) **The person in the loop**. The agent may fetch and forward stories alone, but a person stays at the gate in two places. First, the league comms manager reads alerts at 10 AM daily and decides whether the league responds. That’s a judgment the agent never makes. The “Dirty Play” story about a player’s conduct is an example: relaying it had a right answer, while deciding whether to respond doesn’t. Second, someone audits Zap history weekly against the feed, checking for throttled runs, duplicates, outdated stories and spam such as the fake “WATCH LIVE NOW” streaming pages, several of which came through as successful runs before I added exclusion terms. This check matters because the agent doesn’t report its own failures: 27 missed alerts produced no warning in the inbox. Zapier did block a broken feed URL with a 404 email when I tried to publish it, but nothing flags a feed that stops producing items once it’s live.

The agent would move to A person decides, AI alongside if it drafted responses or rated each story’s risk, since those have no single right answer. It would move to A person leads, AI inside if it posted holding statements only after the comms manager approved them.

(d) **My group’s view**. I agree with most of my group’s placements, especially Insurance: Check completeness of claims document in AI alone, with checks. Like my Full-Court Press agent, it has a right answer, since a document is either complete or not, and a person only needs to spot-check the result. I disagree with one placement: Operations: Escalations of Disputes. My group put it in Agents run it, a person judges, but I would place it in A person decides, AI alongside.

We answer the first question the same way. Resolving a dispute is work with no single right answer: the outcome depends on fairness, the relationship with the customer or supplier, and how much the company is willing to concede, not on a fact AI can verify.

I answer the second question differently. 
--> My group treated it as work that people and AI must do together, with agents running the process and a person judging at set points inside it. 

--> I see an escalated dispute as work either of them can do alone, and in practice a manager handles it alone. By the time a dispute is escalated, it’s usually a <mark>single, high-stakes case rather than a high-volume process</mark>. The manager can resolve it without AI. AI helps by preparing the case: summarizing the history, finding similar past cases and the relevant policy, and drafting two or three settlement options. The person then makes the decision and is accountable for it. That matches the Week 7 deck’s bottom-right example of a banker planning a hard negotiation while AI drafts the options.

My group’s placement would be right under different conditions. If disputes arrived in large numbers and agents triaged them, gathered evidence and proposed resolutions, with a person judging only the contested ones, the work would become a process that people and AI run together, and Agents run it, a person judges would fit. So our disagreement is really about volume and design: for a single escalated case, the person decides with AI alongside.
---