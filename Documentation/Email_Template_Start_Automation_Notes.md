## Data

- Match the format of the source datasets to be used for filling in email templates.

## Still Missing

- Aggregate Safety Report – SharePoint
- PPRL – SharePoint
- RDA AR Report – Power BI (permission to access)
- Group Mailbox

## Overview

This whole thing is a:

- Glorified email sender
- Email template completer

We use the data provided by Merck to fill in the slots required by the company to create the email template 6 months in advance, fill out the email, and then send it by grabbing data from the dataset using Power BI/Power Automate.

### Matching Fields in Documents and Excel Data

- Reporting Period (Report Start, Report End) `<DD-MMM-YYYY>` -> RDAAR column `[Report Start, Report End]`
- `<insert Compound number>` -> RDAAR column `[MK]`
  - My closest guess for this one is "MK-#"
- `<insert Application number>` -> RDAAR column `[App Num]`
- Due to The FDA `<DD-MMM-YYYY>` -> RDAAR column `[Content Due Date]`
- Content Due Date `<DD-MMM-YYYY>` -> RDAAR column `[Content Due Date]`
- Due to FDA: `<DD-MMM-YYYY>` -> RDAAR column `[Content Due Date]` + 30 days as stated in email template
- Content Due Date for the final, submission-ready DSUR to Specialty Submission Planner (7 business days prior to FDA submission date): `<DD-MMM-YYYY>` -> RDAAR column `[Content Due Date]` + 23 days
- `<insert TRADENAME™ in UPPERCASE letters>` -> PPRL column `[Global Trade Name (Random)]`
- `<insert BLA>` -> RDAAR column `[App Num]` (used for specific drugs that have BLA prefix)
- IND/BBIND ANNUAL REPORT DSUR IN LIEU OF IND ANNUAL REPORT ALERT NOTICE -> We use the data pertaining to the column "Document Type" where the value is "IND/BBIND-Annual Report"
- MK/V-<XXXX> -> RDAAR column `[MK]`
- IND/BBIND `<####>` -> RDAAR column `[App Num]` (I think ?!)
- `<insert Compound number>, insert NDA OR ANDA OR BLA (CDER) insert Application number>` -> RDAAR column `[App Num]`
  - Where the prefix is either NDA, ANDA, or BLA
- `<insert Application number>` -> RDAAR column `[App Num]`
  - Where the prefix is ODD
- Orphan Drug Designation for `<insert Indication>` -> PPRL column `[Therapeutic Area]`

## Additional Fields

What and where is:

- `<Insert Specialty Submission Planner’s first and last name>`
- `<insert Merck email address of Specialty Submission Planner>`
- `<Insert Specialty Submission Planner’s first name>`
- `<(insert Generic Name in parenthesis)>`
- `<insert Contributor names from Contributors List / Components Table below> GPVCM Aggregate Clean Check`
- `<insert IND OR BBIND> <insert Application number>` (do we also insert those with BLA, BBM, etc. or just IND)
- `<insert FDA OR EMA OR FDA and EMA>`

Do we fill out fields where they state:

- "Component Being Provided (Yes/No/Not Applicable)"

---

## Formatting Adjustments

We have to figure out how to:

- Erase the green text in documents
- Turn the red text into black text
