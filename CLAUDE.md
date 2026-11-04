# Mail Totals Tracker — UKG Print Shop

This folder has one Excel workbook, `Mail Totals Tracker.xlsx`. The print shop uses it to add
up outgoing mail as **letters** and **flats**. It replaces a paper notepad.

This file is written so a technician can read it directly, or open this folder in Claude Code
and ask Claude to help with setup or changes.

## The goal for the technician

Put `Mail Totals Tracker.xlsx` in the print shop's Microsoft Teams so everyone on the team can
open it and type in it. No macros, add-ins, or code are needed. It works in Excel desktop,
Excel for the web, and the Excel tab inside Teams.

## How to add it to Teams

1. In Teams, open the print shop team and pick the channel to use (for example **General**).
2. Open the **Files** tab in that channel, click **Upload**, and choose `Mail Totals Tracker.xlsx`.
3. Optional, but recommended: pin it as a tab. Click **+** at the top of the channel, choose
   **Excel**, then pick the uploaded file. Name the tab **Mail Totals**.
4. Make sure everyone in the print shop is a member of the team. Members can edit by default.
5. Tell staff to open it from the tab or the Files list, not to download a copy. A downloaded
   copy will not sync with everyone else's entries.

Optional: protect the sheet so nobody types over the formulas. Unlock the yellow cells first,
then use Review > Protect Sheet.

## Layout (one sheet: "Mail Totals")

| Cells | What it is |
|---|---|
| B2 | Date (yellow, typed in) |
| Row 4 | Headers: Category, Letters, Flats, Total |
| A5:A9 | Categories: POA, Employee Notification Letters, Termination Letters, Garnishments, Interrogatories |
| A10:A12 | Blank yellow rows. Staff can type a name here for a new category |
| B5:C12 | Yellow input boxes: Letters (B) and Flats (C) for each category |
| D5:D12 | `=B+C` total for each category |
| Row 13 | TOTAL: `=SUM()` of all Letters, all Flats, and the grand total |

- Every category has both a Letters box and a Flats box.
- To add a later batch to the same category, type a formula such as `=400+120` in the box.
- Data validation on B5:C12 only allows numbers 0 or higher.
- To start a new day, clear B5:C12 and change the date. To keep a record, save a copy first,
  or use SharePoint version history.
- Color legend: yellow fill with blue text = typed in, black text = formulas.

## Rules for changing the workbook (for Claude or anyone else)

- Keep it to one simple sheet. The user asked for it to be condensed and easy to use.
- Use formulas for totals. Don't paste in fixed numbers.
- Keep it macro-free (`.xlsx`). Macros don't run in Excel for the web or Teams.
- To add more category rows, insert them **above** the TOTAL row so the `SUM` ranges grow.
  Then copy the `=B+C` formula into column D of the new rows.
- Keep the Arial font and the yellow color for input cells.
