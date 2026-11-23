# CareNova landing page

This is the landing page for CareNova, an app that helps Sri Lankan families find and book a trusted carer for an elderly or sick relative. You can see it live at [carenova.lk](https://carenova.lk).

We built it for our Software Development Group Project (Group CS78) at IIT, in partnership with the University of Westminster. The app itself is still in development.

## What's in the folder

```
care-nova-landing-page/
├── index.html    # the whole website
└── README.md     # this file
```

The whole site is one file. The design, the code and the logo are all inside `index.html`, so there's nothing else to install or download.

## What the page shows

- A short intro to CareNova with a phone preview of the app
- Our promise: "Care that feels like family, for the people who raised us"
- Why care at home matters in Sri Lanka, with a chart of the ageing population
- The main features: matching carers to a condition, daily care logs, an SOS button, backup carers, training badges, booking and payment
- How it works, for families and for carers
- Safety information and a FAQ
- A waitlist sign-up form

The page works in Sinhala, Tamil and English, and it adjusts to phones, tablets and computers. It uses the same cream, black and green colours as our Figma prototype, with a few soft glowing touches. The animations turn off by themselves if someone has "reduce motion" switched on in their settings.

## How to open it

Double-click `index.html`. It opens in your browser.

The fonts come from Google Fonts, so the page looks best when you're online. Without internet it still works, just with your computer's default fonts.

If you want to test it the way it runs online, you can start a small local server with Python:

```bash
python -m http.server 8000
```

Then go to `http://localhost:8000` in your browser.

## How it's hosted

The site runs on Cloudflare Pages, which is free. The domain `carenova.lk` was bought from LK Domain Registry and points to Cloudflare.

The full setup steps are in `CareNova_Cloudflare_Hosting_Guide.pdf`. In short:

1. Upload the folder to Cloudflare Pages.
2. Add `carenova.lk` to Cloudflare and copy the two nameservers it gives you.
3. Put those nameservers in your LK Domain Registry account.
4. Connect `carenova.lk` and `www.carenova.lk` to the Pages project.

## How to update the site

1. Make your changes in `index.html` and check them in your browser.
2. In Cloudflare, open Workers & Pages, then the `carenova` project, then click "Create a new deployment".
3. Upload the folder again. Keep the file name as `index.html`.

If you still see the old page, press Ctrl+F5 to refresh.

## Changing the colours

The colours are set in one place, in the block called `LIGHT THEME` near the bottom of the `<style>` section in `index.html`. Change a colour there and it changes everywhere on the page.

| Name | Colour | What it's for |
|---|---|---|
| `--cream` | `#F3F0E8` | Top section and footer background |
| `--paper` | `#FFFFFF` | Page background and cards |
| `--butter` | `#FBF0B5` | Yellow highlight cards and soft glows |
| `--ink` | `#111111` | Headings and main buttons |
| `--muted` | `#55564F` | Normal paragraph text |
| `--blue` | `#1F7A4A` | The green accent (ticks, active tabs, "Nova" in the logo) |
| `--sos` | `#D9534F` | The emergency button only |

The accent is still called `--blue` in the code because the page used to be blue. It holds the green colour now, so you can leave the name as it is.

To change any text, open `index.html` and search for the words you want to change. Each section has a comment above it, like `<!-- FEATURES -->`, to help you find your way.

## Before launch: the waitlist form

The sign-up form doesn't send emails to the team yet. Right now it only saves the email in the visitor's own browser, so we can't see who signed up.

To fix this, connect the `submitWaitlist()` function near the bottom of `index.html` to a real service. A free form service like Formspree is the easiest option. Firebase or our own Spring Boot backend would also work.

## Team

Group CS78:

- Nimsara Rajapakse (Leader)
- Samidi Wedage
- Malki Ovindi
- Thisath Samarawickrama
- Nadil Athuraliya

## Sources

The population numbers on the page come from:

- [Sunday Times (2026), Growing old before growing rich](https://www.sundaytimes.lk/260830/news/growing-old-before-growing-rich-preparing-lanka-for-an-ageing-future-653676.html)
- [Asia Insurance Review (2025), Over-60s by 2040](https://www.asiainsurancereview.com/News/View-NewsLetter-Article/id/93420/type/Conferences/Gallery)
- [AsiaNews (2025), Sri Lanka's ageing population](https://www.asianews.it/en/south-asia/sri-lanka/as-sri-lanka-s-population-ages-the-vulnerability-of-senior-citizens-grows)

© 2026 CareNova. A university project, not a live service yet.
