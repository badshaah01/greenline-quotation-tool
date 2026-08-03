# Greenline Associates — Quotation Generator

Single-file static HTML tool that replaces the manual copy/edit/calculate
quotation workflow. No backend, no build step — one `index.html` file.

## How it works
- Company details (name, GSTIN, address) are constants — set once, rarely touched.
- Quotation/client fields and line items are filled per job.
- Qty × Rate, CGST/SGST (9% each, editable), totals, and amount-in-words
  all auto-calculate.
- "Preview & Print to PDF" renders the print-formatted quote (matching the
  original Greenline quotation layout, with logo + signature stamp embedded
  as base64) and opens the browser print dialog — save as PDF from there.
- "Reset for New Quote" clears client/item fields, keeps company details.

## Deployment
Static site, deploys as-is to Vercel — no build command, no framework,
just serves `index.html`.

## Editing
Everything (HTML/CSS/JS) lives in `index.html`. No dependencies to install.
Open this folder in Antigravity for future changes, same workflow as the
greenline-dashboard project.

## Known limitations
- No persistence/history — it's a fill-print-repeat tool, not a database.
  Quote numbers, past quotes, etc. are not stored anywhere.
- Logo/stamp are baked in as base64 inside the file — if the logo or stamp
  design changes, they need to be re-cropped and re-embedded (ask Claude
  to do this from a fresh image upload).
