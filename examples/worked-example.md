# Global Opportunity Navigator: Worked Example

Part of the Global Opportunity Navigator skill. Read `SKILL.md` first. Open this file only when you need to see what finished output looks like.

## About this example

This example shows a run **without web search**. Under SKILL.md section 5 and the Error handling rules, the skill must then give only unverified leads with official URLs to check, and must not state deadlines or amounts from memory. Every deadline and funding cell below therefore reads `unverified`. The profile is a made-up sample. The programmes are real schemes, listed by name only, with no figures from memory.

Request: "Find fully funded master's or PhD options abroad in digital humanities or cultural studies for me."

Settings: `fully_funded_only` ON, `open_deadlines_only` ON, `strict_verification` OFF (needed here, because nothing can be verified without search), `include_application_fees` OFF, `balanced_mix` ON.

## 1. Profile summary

- M.A. English, final year; digital humanities and postcolonial literary studies; Indian citizen (stated by the user, not assumed).
- Goal: fully funded master's or PhD abroad, starting autumn 2027.
- Constraints: no application fees; documents on hand are CV, transcripts and a writing sample; two recommenders available.

## 2. Search brief

"Fully funded master's and doctoral funding in digital humanities and cultural studies in Germany, the UK and the EU for an Indian humanities postgraduate, starting autumn 2027."

## 3. Results

Web search was not available, so every record is `verified: false`. Check each official page before acting.

| Name | Type | Country | Funding | Deadline | Fit | Category | Link | Checked on |
|---|---|---|---|---|---|---|---|---|
| DAAD research grants for doctoral candidates | scholarship | Germany | unverified | unverified | 4/5 | Target | https://www.daad.de | not checked |
| Erasmus Mundus Joint Master's (digital humanities or cultural studies strands) | scholarship / master's | Several EU countries | unverified | unverified | 4/5 | Target | https://erasmus-plus.ec.europa.eu | not checked |
| Chevening Scholarships | scholarship | UK | unverified | unverified | 3/5 | Reach | https://www.chevening.org | not checked |
| European Summer University in Digital Humanities | summer_school | Germany | unverified | unverified | 3/5 | Safe | unverified (find the organiser's official page) | not checked |

Fit scores are qualitative judgements from the sample profile (field match, funding, effort), not predictions. The list is lopsided toward Target; with `balanced_mix` ON the skill says so and notes that a Safe option needs the user's grades before it can be judged.

Sorted by deadline, then score. Deadlines are all unverified, so the order is by score.

## 4. Excluded options

| Option | Reason |
|---|---|
| "Guaranteed scholarship after a USD 300 processing fee" (sent to the user by email) | Asks for a fee to be selected and guarantees selection. Always removed. |
| A programme the user mentions whose page shows last year's deadline | `open_deadlines_only` is ON and the deadline has passed. Usual reopening month: unverified. |

## 5. Action plan (next steps)

Because no deadline is verified, a dated timeline cannot be built. The skill says so and does not guess.

1. Open the four official pages and record each deadline, funding detail, eligibility rule and application fee, with the date checked.
2. Ask the two recommenders now. Give them at least 3 weeks.
3. Start the research proposal and the statement of purpose from your real experience; the skill will draft them on request.

Once the deadlines are confirmed, the skill returns a timeline working backwards from each date, with at least 3 days of buffer, and one combined document checklist.

## 6. Caveats: re-verify on the official site

- Every deadline, amount, eligibility rule (including citizenship) and fee.
- That each page describes the current cycle and the correct programme.
- Whether DAAD and Erasmus Mundus are programmes or funding sources you apply to separately, since this changes the plan.

## Why this is a good output

- It does not invent a deadline or an amount to look complete.
- It separates what it knows (scheme names, official URLs) from what it cannot know without search.
- It removes the scam offer with a reason, and moves the closed programme to the excluded list.
- It ends with exact next actions.
