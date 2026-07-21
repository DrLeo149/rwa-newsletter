# Ankya Advisors LLP, RWA Newsletter Landing Page

A single static landing page that converts incoming traffic into newsletter
subscribers. It collects a full name, RWA / association name, and email, and
sends every submission to you through [Formspree](https://formspree.io), which
emails you each entry and stores them in a dashboard you can export to CSV.

Files:

- `index.html` , the page, form, and submit logic
- `styles.css` , all styling
- `logos/` , builder and software logos used by the two scrolling strips
- `slides/` , the hero carousel images
- `README.md` , this file

---

## 1. Collecting subscribers (Formspree)

The form is already wired to your Formspree endpoint:

```html
action="https://formspree.io/f/xpqvrzpl"
```

To activate it:

1. Submit one **test entry** on the live (or local) page.
2. The first time, Formspree emails you to **confirm the form**. Click the
   confirmation link once.
3. After that, every submission is emailed to you and stored in your Formspree
   dashboard, where you can export to CSV or connect a dedicated email tool.

The form sends `name`, `association`, and `email`, plus a `consent` value and a
hidden `_gotcha` honeypot that Formspree uses to filter spam. To point the form
at a different Formspree form later, replace the `action` URL in `index.html`.

**Want subscribers to also land in a Google Sheet?** Connect Formspree to Google
Sheets with a free Zapier or Make automation (trigger: new Formspree submission,
action: add row to your Sheet), or upgrade Formspree for its built-in
integration.

---

## 2. Edit the marketing copy

All text you may want to change is wrapped in comments that start with
`<!-- EDIT: ... -->` inside `index.html`. Search the file for `EDIT:` to find
every spot. These include:

- The hero headline and subhead
- The three "What the newsletter covers" cards
- The three "Services we offer" cards
- The two strip headings ("Builder RWAs we work with", "Software we work with")
- The form heading, consent line, and data-use note
- The thank-you message
- The footer text and links
- The WhatsApp number and prefilled message

**Footer links** are already set to your Website, LinkedIn, and Instagram.

---

## 3. Upload to any static host

The page is plain HTML, CSS, and images, so it works on any static host. Pick
one:

- **Netlify Drop:** go to https://app.netlify.com/drop and drag the whole
  project folder in. You get a live URL in seconds.
- **Cloudflare Pages / GitHub Pages / Vercel:** create a project and upload or
  connect the folder.
- **Traditional web hosting:** upload the files with any FTP client.

Upload the **whole folder**, including `index.html`, `styles.css`, `logos/`, and
`slides/`, so the styles, logos, and hero images all load. Folder names are
lowercase on purpose, keep them lowercase on the host.

---

## Notes

- Test the form once after pasting your web app URL. Submit a test entry and
  confirm it reaches both the Sheet and your inbox.
- The page validates fields in the browser and shows an inline thank-you state
  on success, so visitors never leave the page.
- The logo in the header currently loads from ankyadvisors.com. For a fully
  self-contained page, download it and reference it locally.
- Custom domain setup (DNS) is intentionally not covered here. The page runs on
  any host as is.
