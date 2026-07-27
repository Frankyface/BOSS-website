# BOSS Website

Static rebuild of [bossolutions.pro](https://bossolutions.pro) (BOSS — Bubyn Onusko Software Solutions), migrated off GoHighLevel so it can be hosted for free on GitHub Pages.

## Structure

```
index.html          Home page
contact/index.html  About Us / Contact page (matches the old /contact URL)
styles.css          All styling (Poppins font loaded from Google Fonts)
assets/             All images, downloaded from the original site's CDN
```

No build step, no dependencies — plain HTML and CSS. Edit the files and push; GitHub Pages redeploys automatically.

## Hosting on GitHub Pages

The site is served from the `main` branch root. Settings → Pages → Source: **Deploy from a branch**, Branch: **main / (root)**.

Default URL: `https://frankyface.github.io/BOSS-website/`

### Pointing bossolutions.pro at it (when ready to leave GoHighLevel)

1. In this repo: Settings → Pages → Custom domain → enter `bossolutions.pro` (this creates a `CNAME` file).
2. At the domain registrar, replace the current GoHighLevel DNS records with:
   - `A` records for the apex (`bossolutions.pro`) pointing to GitHub Pages IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Optional `CNAME` record for `www` → `frankyface.github.io`
3. Back in Settings → Pages, tick **Enforce HTTPS** once the certificate is issued.

## Notes from the migration

- The **App** link in the header points to `app.bossolutions.pro`, which is the GoHighLevel client portal. It will stop working once the GoHighLevel subscription is cancelled — remove the link at that point if there's no replacement.
- The original site had no contact forms (all CTAs link to the contact page; contact is by phone/email), so nothing form-related was lost in the move to static hosting.
- Two sections that existed in the original page builder but were **hidden** on the live site (a stats bar and a "Hear From Our Clients" testimonial carousel, both still containing lorem-ipsum placeholder text) were intentionally left out.
