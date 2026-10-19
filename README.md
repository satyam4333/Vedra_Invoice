# JERVISH Business Suite — Free Self-Hosted Edition

A Refrens-inspired, local-first business management app. It is an independent implementation and does not use Refrens code, branding, or private APIs.

## Included
- Dashboard
- GST-ready invoice builder with line items, HSN/SAC and GST
- Quotations + convert quotation to invoice
- Client management
- Product/item catalogue
- Payment recording and outstanding calculation
- Expense/purchase tracking
- Business settings
- Print / Save as PDF through browser print
- JSON backup and restore
- Responsive desktop/mobile layout
- PWA manifest
- No paid API, no database subscription, no login required

## Deploy
This is a static site. Upload `index.html` and `manifest.json` to any static hosting provider such as GitHub Pages, Netlify, Vercel, Cloudflare Pages, or your own server.

No build command is required.

## Important limitation
Because this version is intentionally static and free, data is stored in the browser's localStorage. It is not a cloud multi-user SaaS. Clearing browser data removes the local data, so use Backup / Restore regularly.

It does not include proprietary/regulated integrations such as Refrens' private backend, bank feeds, WhatsApp/email delivery infrastructure, payment gateway settlement, GSTN e-invoice API credentials, e-way bill API credentials, or AI OCR backend. Those require external services/accounts.

## Recommended next upgrade
If you want a true cloud SaaS with login, PostgreSQL, multi-user access, file storage, email/WhatsApp, and server-side PDF generation, this same UI can be moved to a React/Next.js + Supabase architecture.


## Invoice format update
The invoice layout is based on the uploaded reference invoice's structure: Sales Invoice heading, Invoice No/Date, side-by-side Billed By and Billed To blocks, GSTIN/PAN, item table, tax columns, bank details, totals, terms and electronic-document footer. The actual party values from the reference document are NOT hard-coded into the application.

### Automatic GST
- Seller state is taken from Business Settings.
- Party state is stored in the Party Master.
- Same seller + party state => CGST + SGST, each half of the applicable GST.
- Different states => IGST, with CGST/SGST removed.
- If a party state field is empty, the app attempts to infer the state from the party address.


## v3 enhancements
- Local logo upload from device (stored as local data).
- Professional blue invoice/quotation visual theme.
- Unit selector: pcs, kg, g, set, box, meter, litre.
- Enhanced invoice preview and print/save-PDF workflow.
- Invoice/quotation records remain saved in browser local storage.
- Download Invoice File creates a portable HTML copy for local storage.
