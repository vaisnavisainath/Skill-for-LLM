# Global Opportunity Navigator: Test Cases

## Test 1: Basic PhD search

Input:
Find fully funded PhD programs in cultural studies in Europe for an Indian M.A. student.

Expected:
- Profile questions only for missing fields
- A search brief
- Verified programmes with deadlines and links
- Reach, target, and safe categories

## Test 2: Archive grant

Input:
Which fellowships can an Indian humanities researcher apply for to visit an archive overseas?

Expected:
- Archive and visiting fellowship results, not degree programmes
- Citizenship checked against each scheme
- Funding covers travel or stay, as stated by the provider

## Test 3: Eligibility check

Input:
Am I eligible for the [named scholarship]?

Expected:
- Official page checked for the current cycle
- Each requirement compared with the user's profile
- "Unverified" for anything the page does not state

## Test 4: Fully funded switch

Input:
Find PhD programs in sociology abroad.

Settings:
fully_funded_only = true

Expected:
- Programmes without stated funding are excluded, each with a one line reason

## Test 5: Strict verification

Input:
Find summer schools in digital humanities.

Settings:
strict_verification = true

Expected:
- Only schools whose deadline and eligibility are confirmed on an official page
- Fewer results rather than padded results

## Test 6: Scam screening

Input:
Apply to this scholarship, it guarantees selection after a processing fee.

Expected:
- The opportunity is flagged and excluded
- The user is told why and given safe next steps

## Test 7: Passed deadline

Input:
Find fellowships due this month.

Settings:
open_deadlines_only = true

Expected:
- Passed deadlines are excluded with a reason
- Usual reopening month noted as unverified

## Test 8: Action plan

Input:
Make a month by month plan for my top three picks.

Expected:
- Timeline working backwards from each deadline
- At least 3 days buffer before submission
- Document checklist and next three actions

## Test 9: Cold email

Input:
Draft an email to a professor whose work matches my interests.

Expected:
- Asks for the user's real experience first
- Under 150 words, one verified reference, one clear ask
- No invented achievements

## Test 10: Missing citizenship

Input:
Find scholarships abroad for me.

Expected:
- The skill asks for citizenship and level before filtering
- It does not assume citizenship from location
