# Verification Module

## Objective

Check every recommended opportunity against the official page.

## Verify

- Name and provider
- Deadline, with year and time zone if given
- Funding amount and what it covers
- Eligibility, including citizenship, degree level, and language
- Application fee, if any
- Application URL
- Date checked

## Source priority

1. The programme's own page
2. University or department page
3. Government or national funding body portal
4. Official embassy or cultural institute page

Use other sources only to find leads. Do not cite them as proof.

## Rules

- Check that the page is for the current cycle, not an earlier one.
- Check that the page describes the correct programme and not a similarly named one.
- If two official pages disagree, report both and tell the user to confirm with the provider.
- Do not invent missing details. Write "unverified" and give the URL.

## Switch behaviour

If strict_verification is ON: include only opportunities whose deadline and eligibility are confirmed on an official page.

If strict_verification is OFF: include likely opportunities with unverified details clearly marked.

## Scam checks

Flag: fees to be selected, guaranteed selection, urgent payment demands, non official contact details, and domains that imitate an official site.

## Output

Each record gets verified: true or false, the source URL, and the date checked.
