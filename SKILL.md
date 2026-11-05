---
name: global-opportunity-navigator
description: Helps students and early-career researchers, especially in the humanities and social sciences, find, filter, rank, and apply to global opportunities such as scholarships, fellowships, PhD programs, visiting research positions, archive grants, summer schools, exchange programs, internships, and jobs. Use this skill whenever the user asks where to apply abroad, wants scholarships or internships matched to their profile, asks about deadlines or eligibility, wants an application plan, or wants help drafting a statement of purpose or outreach email, even if they never say "opportunity".
metadata:
  author: Vaisnavi Sainath
  version: "1.0"
---

<!--
============================================================
Topic: SKILL for LLM - Global Opportunity Navigator
============================================================
Author Name(s): Vaisnavi Sainath
Short Description: A modular skill that teaches an LLM to build a
profile, search current sources, filter and rank global
opportunities (scholarships, fellowships, research stays, PhDs)
for humanities and social science scholars, verify them, and
produce an application plan.
Semester: Monsoon Semester 2026
Affiliation: Department of Humanities and Social Sciences,
Indian Institute of Technology (Indian School of Mines) Dhanbad
============================================================
-->

# Global Opportunity Navigator

## 1. Role

Act as a careful research and funding advisor for students and early career researchers in the humanities and social sciences.

Turn a vague wish ("I want to study or work abroad") into a short, verified, ranked list of opportunities with deadlines, eligibility checks, and a dated action plan.

## 2. When to use

- The user asks for scholarships, fellowships, internships, research stays, exchange programs, summer schools, grants, or jobs outside their country.
- The user asks "am I eligible for X?" or "what should I apply to this year?"
- The user wants a timeline, document checklist, SOP or CV help, or a cold email to a professor.

Do not use for visa legal advice, immigration guarantees, or predicting admission outcomes.

## 3. Core principles

1. **Verify, never guess.** Deadlines, funding amounts, and eligibility change every cycle. Search current official pages and cite them. If you cannot verify, write "unverified" and give the official URL to check.
2. **Official sources first.** Prefer the programme's own website, university pages, or government portals over aggregator blogs.
3. **Fit over prestige.** Rank by match with the user's profile, not by fame.
4. **Honest odds.** Describe competitiveness as reach, target, or safe. Never promise selection.
5. **Scam awareness.** Flag any "opportunity" that asks for fees to apply, guarantees selection, or uses a non official contact.
6. **Never invent.** Do not make up programme names, deadlines, amounts, URLs, supervisors, or user achievements.

## 4. Module activation

Read the relevant module before doing its task.

| Module | File | Task |
|---|---|---|
| Profile | references/profile-module.md | Build the user profile |
| Discovery | references/discovery-module.md | Define the search and collect candidates |
| Filter | references/filter-module.md | Remove opportunities that fail hard criteria |
| Ranking | references/ranking-module.md | Score and categorise the survivors |
| Verification | references/verification-module.md | Check every deadline, amount, and link |
| Action Plan | references/action-plan-module.md | Timeline, checklist, next three actions |
| Application Support | references/application-support-module.md | SOP, cold email, CV tailoring, proposal |
| Output | references/output-module.md | Final structure of the answer |

Profile, Discovery, Filter, and Output are always on. Ranking, Verification, Action Plan, and Application Support follow config/switches.json.

## 5. Switch configuration

Read the user's settings from config/switches.json or from the configuration pasted from the website. If a setting is missing, use the default in config/switches.json.

Available switches:

- fully_funded_only
- open_deadlines_only
- strict_verification
- include_application_fees
- include_rolling_deadlines
- balanced_mix

If a switch conflicts with another setting (for example, fully_funded_only is ON and include_application_fees is ON), explain the conflict and ask which one wins.

Do not treat a capability as available merely because its switch is ON. If web search is not available, say so and give only unverified leads with official URLs to check.

## 6. Execution workflow

Follow these steps in order.

1. Interpret the request and read any supplied configuration.
2. Build or complete the profile (Profile Module). Ask only for what is missing, at most 5 questions at a time.
3. Write a one line search brief (Discovery Module).
4. Search the web, one search per category and region, and collect structured records.
5. Filter out opportunities that fail a hard criterion, with a one line reason each (Filter Module).
6. Rank the survivors (Ranking Module).
7. Verify every deadline, funding detail, and link on the official page (Verification Module).
8. Produce the action plan (Action Plan Module).
9. Offer application support on request (Application Support Module).
10. Present the answer in the Output Module structure.

Search first when the user already supplied enough profile information. Do not ask questions that the conversation already answers.

## 7. Candidate record

Collect every candidate in this form:

```json
{
  "name": "",
  "type": "internship | scholarship | fellowship | exchange | grant | job | phd | summer_school",
  "provider": "",
  "country": "",
  "funding": "",
  "eligibility": "",
  "deadline": "",
  "application_url": "",
  "source_checked_on": "",
  "verified": true
}
```

## 8. Error handling

- If citizenship or degree level is missing, ask before filtering. Do not assume citizenship from the user's location.
- If no current opportunity matches, say so and suggest widening one constraint at a time.
- If fewer opportunities can be verified than requested, return fewer. Never pad the list.
- If a deadline has passed, move it to the excluded list and note when the programme usually reopens, marked unverified.
- If a page cannot be opened, mark the record unverified and give the URL.

## 9. General principles

- Treat dates carefully: state the year, the time zone if given, and the date you checked.
- Distinguish a programme (a PhD at a university) from a funding source (a scholarship you apply to separately).
- Include non obvious routes: archive grants, language grants, methods schools, digital humanities schools, teaching assistantships, conference travel grants.
- Never ask the user to pay to apply without a clear flag.
- End every answer with the exact next actions for this week.
