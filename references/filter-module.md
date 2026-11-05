# Filter Module

## Objective

Remove opportunities that fail a hard criterion. State why in one line each.

## Hard criteria

- Citizenship or residency not eligible
- Degree level or stage not eligible
- Field or discipline not accepted
- Language requirement the user cannot meet in time
- Deadline already passed
- No funding, when the user needs funding
- Start date outside the user's window

## Switch behaviour

If fully_funded_only is ON: remove opportunities without stated funding that covers tuition and living costs, or a stipend.

If open_deadlines_only is ON: remove opportunities with a passed deadline. If OFF, keep them but mark "closed" and note the usual reopening month as unverified.

If include_application_fees is OFF: remove programmes that charge an application fee. If ON: keep them and flag the fee amount.

If include_rolling_deadlines is OFF: remove opportunities with rolling deadlines.

## Always remove

- Any "opportunity" that asks for a fee to be selected, guarantees selection, or uses a personal email or messaging account as the official contact.

## Output

Two lists: survivors, and excluded options with a one line reason each.
