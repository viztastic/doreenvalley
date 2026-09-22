# Save the Doreen Valley — website

A three-page campaign site opposing the proposed Middle Hut BESS at 260 and 340
Middle Hut Road, Doreen. One self-contained HTML file. No build step, no
dependencies, nothing to install.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site — all three pages, styles and scripts inline. |
| `hero.jpg` | The valley photograph used behind the home page heading. Replace it with a better one any time — keep the same filename and nothing else needs changing. |
| `_headers` | Security headers. Cloudflare Pages and Netlify both read this automatically. |
| `README.md` | This file. Not published. |

## Put it online (about five minutes)

### Cloudflare Pages — drag and drop

1. Sign in at **dash.cloudflare.com** (free account is fine).
2. **Workers & Pages** → **Create** → **Pages** → **Upload assets**.
3. Name the project `save-the-doreen-valley`.
4. Drag this whole folder onto the upload box. Click **Deploy site**.
5. You get a live URL like `save-the-doreen-valley.pages.dev`. Share that.

To update it later, open the project → **Create new deployment** → drag the
folder again.

### Your own domain

Buy `savethedoreenvalley.org.au` or similar, then in the Pages project go to
**Custom domains** → **Set up a custom domain** and follow the DNS steps.
A real domain is worth the $20 or so — neighbours trust it, and it looks like a
campaign rather than a link someone forwarded.

### Netlify instead

Drag the folder onto **app.netlify.com/drop**. Done. Same result.

## The forms

All three forms post to Formspree at `https://formspree.io/f/xvkgaapa`:

- the petition,
- the "keep me posted" mailing list,
- the optional "send us a copy" of a submission.

Each submission carries a `form` field (`petition`, `mailing-list` or
`submission-copy`) so you can tell them apart in the Formspree dashboard, and a
`_subject` line so the notification emails are readable.

Once hosted, submitting happens inline without leaving the page. Test all three
after your first deploy, and check they arrive in Formspree.

**Worth doing in Formspree:** turn on reCAPTCHA to stop spam signatures — a
petition full of junk is easy to dismiss. You may also hit the free plan's
monthly submission cap if the campaign takes off; check before you letterbox
the street.

To change the endpoint, edit one line near the bottom of `index.html`:

```js
var FORMSPREE = "https://formspree.io/f/xvkgaapa";
```

## Before you share it widely

Two placeholders are still in the page:

1. **`[AUTHORISED BY — name, suburb]`** in the footer. Australian campaign
   material conventionally carries an authorisation. Put a real name and suburb
   there.
2. **`[AUTHORITY NAMED ON THE PUBLIC NOTICE]`** in the submission builder
   (again, one line of JavaScript near the bottom). Fill it in, along with the
   application reference number, as soon as the public notice is published.

Also worth adding when you have them: photographs taken from homes above the
valley, and the number of dwellings with a direct line of sight to the site.
Both do more work than any wording on the page.

## Keeping it accurate

Every factual claim traces to a source listed on the "full case" page — the
developers' own site, Nillumbik Shire Council's statement of 20 August 2026,
EPA Victoria, or Planning Victoria. If any of it changes, update the page and
the "Updated" date in the footer. Accuracy is the campaign's main asset: one
overstated claim gives the proponent an easy way to dismiss the rest.
