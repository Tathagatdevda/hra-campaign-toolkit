# HRA Geo Targeting Tool

Turns the HRA **Store Classification Report** (Excel) into Google Ads location lists, so a vendor's ad budget only goes to areas where stores actually carry that vendor.

**Live:** https://tathagatdevda.github.io/hra-geo-targeting-tool/

## How it works

1. **Upload** the Store Classification Report (.xlsx) exported from the CRM.
2. **Choose vendor**: who the campaign is for. Stores marked *Yes* or *Open Ticket* count as carrying it (changeable under Advanced). Add more vendors for co-op campaigns and match ANY or ALL.
3. **Choose area**: one or more states, optionally narrowed to counties.
4. **Review**: ZIPs where no store carries the vendor are skipped automatically (you can include any of them again).
5. **Export**: ZIP list (+ exclusions), city & county list, radius-per-store CSV for Google Ads Editor, or an Excel planning report.

## Privacy

The Excel file is read **in your browser only**. Nothing is uploaded to a server, and no store data is stored in this repository.

## Tech

A single static page (`index.html`), with no build step. Excel parsing and the planning report use [SheetJS](https://sheetjs.com/) 0.18.5 from cdnjs. Fonts: Roboto, Roboto Slab and Roboto Mono from Google Fonts. The colors, spacing and type match the Figma design-system variables one-to-one (see the `:root` tokens at the top of `index.html`).
