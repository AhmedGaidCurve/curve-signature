# Curve Email Signature Generator

A one-page tool for Curve Modern Technology (CMT) employees. Each person fills in their details and copies a
ready-made email signature, with the Curve logo, into Outlook or Gmail.

- English (left-to-right) or Arabic (right-to-left) signature
- The page itself in English or Arabic (button in the header). Arabic link: `https://ahmedgaidcurve.github.io/curve-signature/?lang=ar`
- The signature is built from tables and inline styles only, so Outlook and Gmail display it correctly
- Copy the signature, copy its HTML code, or download it as a `.htm` file
- The details stay in the user's browser. Nothing is sent to a server.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The generator page |
| `logo.png` | Curve logo (420×240, transparent background, shown at 140×80). The signature links to it, so keep it in the published site. |
| `logo-dark.png` | Light-on-transparent version of the logo, used in the page header in dark mode |

## Publish on GitHub Pages

1. Sign in to github.com and click **New repository**. Name it, for example `curve-signature`, and make it
   **Public**. (On a free account, GitHub Pages only works for public repositories.)
2. In the new repository, click **uploading an existing file**, drag in `index.html`, `logo.png` and
   `README.md`, then click **Commit changes**.
3. Go to **Settings > Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch `main`, folder
   `/ (root)`, and click **Save**.
4. After a minute or two, the site is live at `https://ahmedgaidcurve.github.io/curve-signature/`.
   Send that link to colleagues.

The signature uses the logo from the published site
(`https://ahmedgaidcurve.github.io/curve-signature/logo.png`). If you delete the repository or rename
it, the logo disappears from every signature that uses it.

## Changing the logo

Replace `logo.png` with a new image of the same size (420×240, or another image with a 7:4 width-to-height ratio)
and commit it. Signatures that were already copied pick up the new image automatically, because they link to the
same address.

## HR settings (company.json)

HR controls the company data in `company.json`: company name (English and Arabic), website, company email
domains, default country code, departments and job titles (English and Arabic), and the legal note.

1. Open the page with `?hr=1` at the end: `https://ahmedgaidcurve.github.io/curve-signature/?hr=1`
2. Fill in the settings. The page shows them right away, but only in that browser (a "draft").
3. Click **Download company.json**, then upload it to this repository (**Add file > Upload files**, **Commit changes**).
4. After 1 to 2 minutes, everyone gets the new lists. Click **Discard draft** to go back to the published settings.

Lists use one line per item: `English name | Arabic name`.

## Other features

- **QR code**: optional vCard QR beside the signature (made in the browser; nothing is sent anywhere).
- **Legal note**: HR's note in small grey text under the signature, in the signature's language.
- **Number check**: phone numbers are tidied to `+CC xx xxxx xxxx`; warnings for wrong numbers and non-company emails.
