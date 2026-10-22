# Publishing a post (Coastal Funding DSCR blog)

Live: https://blog.cfcdscr.com/

## Topics: DSCR only
This blog covers **DSCR (debt service coverage ratio) investment-property loans only**: DSCR basics and math, rental-income qualification, long-term and short-term rentals, LLC/entity buyers, portfolio growth and the DSCR process. Do **not** publish primary-residence topics here (FHA, VA, USDA, first-time buyer, owner-occupied refinance); those belong on the other Coastal Funding blogs. Service area: DSCR investment-property loans nationwide.

1. Create `content/posts/<slug>.md` (lowercase, hyphens, e.g. `content/posts/dscr-short-term-rentals.md`). The slug becomes the URL: `/posts/<slug>/`.
2. Start the file with front matter:

```yaml
---
title: "Can You Use a DSCR Loan for a Short-Term Rental?"
date: 2026-10-25            # ISO date (or 2026-10-25T09:00:00-05:00); future dates are NOT published until then
description: "One or two sentences, <=160 chars, used for meta/OG description."
tags: ["dscr", "short-term rental"]
author: "Coastal Funding Corporation — DSCR"   # must match an author page (see "Author")
image: "images/dscr-short-term-rentals.jpg"     # REQUIRED; see "Images" below
image_alt: "Describe the photo"                 # optional; defaults to the title
draft: false                # true = not published
faq:                        # OPTIONAL; see "FAQ block"
  - q: "Can a short-term rental qualify for a DSCR loan?"
    a: "Often yes. The lender uses the property's rental income to calculate DSCR. Requirements vary by lender."
---
```
3. Write the body in Markdown below the front matter.
4. Commit to `main` (e.g. `gh api` contents PUT, or git push). GitHub Actions builds with Hugo and deploys in ~1 minute. Sitemap (`/sitemap.xml`), RSS (`/index.xml`) and schema update automatically.

Compliance: keep NMLS 103035 references accurate; no rate guarantees. The footer adds NMLS, Equal Housing Opportunity and the not-a-commitment-to-lend notice to every page.

## Images (required on every post)
Every post must have an `image`. It is shown automatically as the featured image at the top of the post, as the thumbnail on the home and list pages, as the social share image (og:image) and in the BlogPosting schema. **Do not** also put the same image inline in the body.

Use one of these:
- **Shared folder (recommended):** commit the file to `static/images/<name>.jpg` and set `image: "images/<name>.jpg"`.
- **Page bundle:** make the post a folder, `content/posts/<slug>/index.md` with the image next to it (`content/posts/<slug>/cover.jpg`), and set `image: "cover.jpg"`.
- **External URL:** `image: "https://..."` (must be a stable public URL).

Recommended: JPG or WebP, landscape 1200x630 or larger, under 500 KB, lowercase hyphenated file name. Commit the image in the same commit as the post.

## FAQ block (optional, recommended for answer engines)
Add a `faq` list to the front matter. Each item has `q` (question) and `a` (short, plain answer, 1-3 sentences). The site shows it as a "Frequently Asked Questions" section at the end of the post and adds FAQPage schema automatically. If the post body already has its own `## Frequently Asked Questions` heading, only the schema is added (no duplicate section). Leave `faq` out and nothing is shown.

## Author
Set `author:` to the exact `name` of a page in `content/authors/` so the byline links to that author page and the schema is correct. Current author name: `Coastal Funding Corporation — DSCR` (page: `/authors/coastal-funding-corporation-dscr/`). If `author` is missing, the byline falls back to the business name. To add a new author, copy a file in `content/authors/`, set `title` and `name`, and use only verified facts in the bio.

```yaml
author: "Coastal Funding Corporation — DSCR"
```

## Custom domain
GoDaddy DNS for cfcdscr.com: `CNAME` record, Name `blog`, Value `cf9880.github.io`. `hugo.toml` has `baseURL = "https://blog.cfcdscr.com/"`, `static/CNAME` contains `blog.cfcdscr.com`, and Pages has the custom domain with Enforce HTTPS.

`static/llms.txt` summarizes this site for AI assistants. Update it if the business details change.
