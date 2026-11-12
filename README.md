# HRA Campaign Toolkit

Turns the HRA Store Classification Report (Excel) into two things:

1. **Google Ads location lists**, so a vendor's ad budget only goes to areas where stores actually carry that vendor.
2. **Mailchimp member lists**: emails of members whose stores are subscribed to a vendor, filtered by one or more states.

Live: https://tathagatdevda.github.io/hra-campaign-toolkit/

## How it works

1. **Upload** the Store Classification Report (.xlsx) exported from the CRM, or the HRA template (`assets/HRA_Campaign_Toolkit_Template.xlsx`, downloadable from the upload screen) filled in with your stores.
2. **Choose task**: ad locations or member email list.
3. **Choose vendor**: a store counts as carrying / subscribed when its vendor cell is **Yes, Open Ticket or Pending** (changeable under Advanced). Ads can combine vendors for co-op campaigns (match ANY or ALL); email lists use one vendor.
4. **Choose area**: ads pick states and optionally counties; email lists pick one or more states.
5. **Review**: ads skip ZIPs where no store carries the vendor (you can include any of them again). Email lists show one row per email address: owners with several stores get the email once, and stores with no email are counted and left out.
6. **Export**:
   - Ads: ZIP list (+ exclusions), city & county list, radius-per-store CSV for Google Ads Editor, or an Excel planning report.
   - Email: Mailchimp-ready CSV with `Email Address, First Name, Last Name, Store, State, Tags` (tag = vendor name). Import it into the HRA MEMBERS audience; Mailchimp keeps unsubscribed members unsubscribed.

## Privacy

The Excel file is read in your browser only. Nothing is uploaded to a server, and no store or member data is stored in this repository. The template contains column headers only.

## Motion

Calm by default, with four big moments (upload success, task picked, review numbers counting up, "file lands" on download) and feedback for errors, selection, loading and copy. Everything falls back to short fades when the device asks for reduced motion.

## Tech

A single static page (`index.html`), with no build step. Excel parsing and the planning report use SheetJS 0.18.5 from cdnjs. Fonts: Roboto, Roboto Slab and Roboto Mono from Google Fonts. Colors, spacing and type match the Figma design-system variables one-to-one (see the `:root` tokens at the top of `index.html`).
