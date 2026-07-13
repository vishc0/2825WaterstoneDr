# 2825 Waterstone Drive property website

This folder is a self-contained static website. It has no build step, package manager, tracking code, form database, or external font dependency.

## Preview

Open `index.html` in a browser. For the most accurate local preview, run a simple local web server from this directory if one is available.

## Deploy

The quickest launch is Netlify Drop: upload this entire `Website` folder at <https://app.netlify.com/drop>. Cloudflare Pages Direct Upload is a strong alternative. See `DEPLOYMENT_AND_DISTRIBUTION.md` for the recommended URL and QR workflow.

## Before public launch

- Confirm the list price and active status have not changed.
- Ask the listing representative to approve the public wording and contact routing.
- Confirm Lavanya Thadiparthi's displayed name, brokerage and phone number.
- Confirm the two-car garage wording against the realtor's current listing before launch.
- Replace the school assignments if Forsyth County Schools gives different current assignments.
- Decide whether to keep the explicit 6,377-sq-ft number before appraisal/professional measurement support is added.
- Obtain permission to reuse the professional listing photographs outside the MLS syndication system if the photography agreement requires it.
- Add the final custom domain to the Open Graph and structured-data URLs after launch.
- Test every link and telephone button on mobile.

## Content guardrails

- Do not describe the terrace level as a legal apartment or separate dwelling unless a qualified professional verifies that status.
- Do not publish inspection reports, security details, permit commentary, seller documents or personal contact information.
- Treat the 150-person gathering statement as owner-reported event history, not a representation of permitted occupancy, fire capacity or event use.
- Treat fall color and July 4 horizon-fireworks language as owner-reported seasonal experiences, not guaranteed views or event access.
- Verify the backyard gate and stair configuration before final publication; describe it as access/enclosure, not a security guarantee.
- Verify the fruit-tree inventory and seasonal condition before final publication; do not imply guaranteed yield or availability.
- Verify the Dave's Creek adjacency and all distance statements before final publication.
- Keep “creekside setting” wording unless a survey or official source confirms legal creek frontage.
- Keep advertising neutral and focused on property features, location and use cases. Avoid audience targeting or language based on any Fair Housing protected characteristic.
- Direct offers, showings and compensation questions through the listing representative and the applicable MLS process.

## Files

- `index.html` — all public page content and search/social metadata
- `styles.css` — responsive design and print styling
- `script.js` — mobile navigation, photo lightbox and current year
- `assets/images/` — selected listing photographs copied for the website
- `netlify.toml` — optional response headers used by Netlify
- `DEPLOYMENT_AND_DISTRIBUTION.md` — launch, QR and circulation playbook
- `CONTENT_STRATEGY_AND_BUYER_PERSONAS.md` — multi-reviewer content strategy, persona messaging, claims discipline and prioritized improvements
- `BUYER_RELOCATION_BRIEF_SAMPLE.md` — concise buyer/relocation handoff sample
- `AGENT_FACT_VERIFICATION_SHEET.md` — internal verification checklist sample

The visual theme uses Google Fonts Playfair Display for editorial/luxury headlines and DM Sans for clean body and interface text, with local fallbacks if fonts are unavailable.
