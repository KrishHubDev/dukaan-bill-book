# Dukaan Bill Book

A simple billing and khata (credit ledger) web app for a retail shop, in the spirit of Vyapar but focused on what a kirana counter needs. It is one HTML file with no server and no build step.

## Features

- **Products with multiple price lists**: each product has an English name, a Gujarati name, a unit and a price for each list (Retail, Wholesale, or your own lists such as Dealer).
- **Fast billing with type-ahead search**: type `su` or `ખાં` and matching products appear below the box. Use ↑ ↓ and Enter to pick, then enter a **Count**; amounts and totals update as you type.
- **Scan a Gujarati list into a bill**: photograph a customer's list and the items and counts are added to the bill, after you review the matches.
  - Free mode reads the list on the device (Tesseract OCR, Gujarati + English). Good for printed or neat lists.
  - Claude mode (optional) reads messy handwriting much better. Add your own Claude API key in **Settings**.
- **Invoices**: print or save as PDF, download as an HTML file, copy as text, or send on WhatsApp.
- **Customers & dues**: outstanding balance per customer with opening balances, a ledger, payments received, WhatsApp due reminders, and a CSV export.
- **Sales report**: Today, This week, This month, Last month, All time or a custom range. Shows totals, cash vs credit, day-wise and item-wise sales, and the bill list, with CSV export.
- **Backup / restore** to a JSON file.

## Run it

Open `index.html` in a browser. To host it for free, enable **GitHub Pages**: go to **Settings → Pages**, choose "Deploy from a branch", then select `main` and `/ (root)`.

## Where data is stored

All data stays in the browser's `localStorage` on that device. Nothing is sent to a server. The only exception is a list photo sent to the Claude API, and only when you add an API key. Clearing browser data deletes your bills, so use **Settings → Download backup** regularly. To move to another device, restore the backup there.

The Claude API key is kept in that browser only and is never included in backups. Don't save it on a shared computer.

## Tech

Plain HTML, CSS and JavaScript. Fonts: Hind Vadodara and Baloo Bhai 2 (Google Fonts). OCR: [tesseract.js](https://github.com/naptha/tesseract.js), loaded only when you scan.
