# Rio's Cafe — website

One-page site plus a full menu page. Plain HTML and CSS: no frameworks, no
external fonts, no JavaScript libraries. That is deliberate — the whole page
arrives in one request, which is fast, and speed is a genuine ranking factor.

Built by Wilf Cartwright.

## Live address

Currently **https://rioscafe.clonal.health** (hosted free on GitHub Pages).

This is a temporary practice address on a family domain. The plan is to move to
the cafe's own domain, e.g. `rioscafe.co.uk`.

## IMPORTANT: moving to a new address

The SEO tags contain the site's **full** web address in 24 places — canonical
links, Open Graph URLs, the sitemap, robots.txt, and the structured data. They
all have to change together.

A canonical tag left pointing at a dead address is **worse than none at all**,
because it tells Google "the real version of this page lives over there" —
and sends it somewhere that no longer exists.

So don't hand-edit them. Run:

```
python3 set-domain.py rioscafe.co.uk
grep -r "clonal.health" .        # should find nothing
```

Then follow the checklist the script prints. The golden rule when retiring the
old address: **remove the pointer before the house.** Take the custom domain off
GitHub first, then delete the DNS record, or you leave a dangling record that
someone else could claim (subdomain takeover).

## What's in here

| File | What it is |
|---|---|
| `index.html` | The main page |
| `menu.html` | Full menu and prices |
| `qr-card.html` | Printable QR card for the tables (set to `noindex`) |
| `qr-code.png` / `.svg` | QR code — **regenerate whenever the address changes** |
| `social-card.png` | 1200x630 preview image shown when the link is shared |
| `favicon.svg`, `apple-touch-icon.png` | Browser tab and phone home-screen icons |
| `sitemap.xml`, `robots.txt` | Tell search engines what exists |
| `set-domain.py` | Repoints every address in one command |

## SEO that's already done

- `CafeOrCoffeeShop` structured data — address, phone, hours, price range,
  payment types, area served, dog friendly / outdoor seating / takeaway
- `FAQPage` structured data on all six real Q&As — can earn an expanded
  Google result with dropdowns
- `Menu` structured data on all 9 sections and 56 items, with real prices
- `BreadcrumbList`, `WebSite`
- Canonical links, Open Graph and Twitter cards, favicons
- Sitemap and robots.txt

## Still to do

- **Google Business Profile** — the cafe must claim this themselves. It matters
  more than everything above put together for "cafe near me" searches. Keep the
  name, address and phone identical to this site.
- **Photos** — the site currently has none. Ask the cafe for 5 or 6. Name the
  files properly (`rios-cafe-full-english.jpg`, not `IMG_4471.jpg`) and write
  real `alt` text.
- **Exact map coordinates** — `geo` is deliberately left out rather than
  guessed. Grab the real latitude/longitude from Google Maps and add it.
- Submit the sitemap to Google Search Console and Bing Webmaster Tools (free).
