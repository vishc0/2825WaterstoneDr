# Deployment, short-link, QR and circulation playbook

## Recommended setup

Use this hierarchy:

1. **Owned domain:** a short property domain such as `2825Waterstone.com`, if available.
2. **Durable campaign path:** print the QR and short text URL as `2825Waterstone.com/tour`.
3. **Website host:** Netlify Drop for the fastest first launch, or Cloudflare Pages if Git-based maintenance is likely.
4. **Analytics:** use privacy-conscious host analytics or a clearly disclosed analytics tool only if the value justifies it.

The owned `/tour` URL is preferable to putting a third-party shortener on permanent printed material: the destination can later be changed at the domain level without reprinting, and the property brand remains visible.

## Hosting options

| Option | Best use | Initial URL | Notes |
|---|---|---|---|
| Netlify Drop | Fastest launch from this local folder | `project-name.netlify.app` | Drag and drop the `Website` folder; repeat to update. Add a custom domain later. |
| Cloudflare Pages | Long-term static hosting and strong DNS integration | `project-name.pages.dev` | Direct Upload supports drag and drop. If automatic Git deployments are wanted, start with Git integration because a Direct Upload project cannot later be converted to Git integration. |
| GitHub Pages | A public repository and simple version-controlled hosting | `account.github.io/repository` | Good if public source and Git workflow are acceptable; custom-domain setup is more manual. |
| Conventional web host | Existing hosting account or agent brokerage infrastructure | Custom | Upload by the provider's file manager/SFTP; more operational overhead for a one-page site. |

### Fastest launch: Netlify Drop

1. Confirm all pre-launch checks in `README.md`.
2. Sign in at <https://app.netlify.com/drop>.
3. Drag this entire `Website` folder into the upload area.
4. Claim the site and choose a readable site name if available.
5. Test the supplied `netlify.app` URL on a phone and desktop.
6. Connect the selected custom domain in the Netlify domain settings.
7. Force HTTPS and choose one canonical hostname (`www` or apex) once DNS is active.

### Cloudflare alternative

Use Pages Direct Upload for manual folder/ZIP updates. If the site will live in Git and be changed regularly, create a Git-integrated Pages project from the start.

Official references:

- Netlify Drop: <https://docs.netlify.com/start/quickstarts/netlify-drop-quickstart/>
- Cloudflare Pages Direct Upload: <https://developers.cloudflare.com/pages/get-started/direct-upload/>
- Cloudflare Pages custom domains: <https://developers.cloudflare.com/pages/configuration/custom-domains/>

## TinyURL and QR options

### Best permanent-print workflow

1. Register the chosen property domain.
2. Create `/tour` as a redirect to the live site or make it the site's canonical page.
3. Generate a high-error-correction QR code pointing to the full HTTPS `/tour` URL.
4. Put the readable URL directly below the code; never make the QR the only path.
5. Test from iPhone and Android, in bright and dim light, at the exact final printed size.
6. Print a single proof before the full run.

Recommended minimums for a handout: roughly 1.0–1.25 inches square, dark code on a plain light background, a clear quiet zone around it, and no image placed over the code unless thoroughly tested.

### When to use TinyURL or Bitly

Use a managed short link if launch must happen before a domain is purchased or if click reporting and an editable destination are worth the third-party dependency. Keep the slug property-specific, for example `tinyurl.com/2825waterstone` if available. Confirm whether editing the destination, analytics and custom QR styling require a paid plan before printing.

- TinyURL QR feature: <https://tinyurl.com/app/features/qr-code-generator>
- TinyURL plan comparison: <https://tinyurl.com/app/pricing>
- Bitly plan comparison: <https://bitly.com/pages/pricing>

Do not print any QR code until the destination is live, HTTPS works, mobile layout is verified and the redirect will be retained for the full marketing period.

## Where to circulate

Coordinate every channel with the listing representative and listing agreement. Use the same canonical URL and track channels with optional UTM labels rather than creating multiple public pages.

### Highest priority: buyer-agent discovery

| Channel | Asset | Action |
|---|---|---|
| Both MLS records | Branded/unbranded property URL as MLS rules allow | Ask the agent to add the permitted virtual-tour/site field and synchronize FMLS/GAMLS. |
| Showing follow-up | Mobile property link and one-page fact sheet | Send automatically or manually to every showing agent; ask for one specific feedback item. |
| Broker and agent open houses | QR tabletop card and concise property sheet | Invite South Forsyth, Alpharetta, Johns Creek, luxury and relocation-producing agents. |
| Brokerage offices | Agent-facing PDF/QR card | Ask managing brokers for permission to share internally or place in an agent resource area. |
| Agent groups and newsletters | One strong hero image, three facts, URL | Use local REALTOR, luxury, relocation and buyer-agent groups where promotion is allowed. Avoid repetitive posting. |

### Relocation and corporate-transfer channels

- Give the listing representative a relocation packet with the site link, MLS sheets, floor-plan/measurement support, update list, HOA summary and showing procedure.
- Ask the brokerage which relocation networks, referral platforms and certified relocation specialists it already participates in; submission through an established network is more credible than cold mass email.
- Contact destination-service and relocation professionals serving North Fulton, South Forsyth and the GA-400 corridor with an agent-to-agent introduction focused on transfer-friendly logistics and flexible space.
- Ask local corporate-housing providers, mortgage lenders, title partners and HR mobility contacts whether they maintain compliant housing-resource boards or agent referral lists.
- Publish a neutral LinkedIn post that is easy for local recruiters, mobility professionals and employees to share. Focus on the home and commute corridor, not personal attributes of an imagined buyer.

### Local physical circulation

- Approved open-house sign-in area, brochure box and QR tabletop signs.
- Listing brokerage and cooperating brokerage offices with permission.
- Mortgage, title, relocation, temporary-housing and corporate-apartment partner offices with permission.
- Community bulletin boards at participating local businesses where real-estate notices are allowed.
- Direct mail through USPS Every Door Direct Mail or a properly addressed/postage-paid campaign if the agent recommends a geographic farm.

Do **not** place unstamped flyers inside mailboxes. USPS restricts mailbox use to authorized, postage-paid mail. Do not place material on private property or in businesses, HOA areas or offices without permission.

## Fair-housing and compliance guardrails

- Describe the property, verified amenities, transportation access and flexible spaces—not a preferred buyer's race, color, religion, national origin, sex, familial status, disability or other protected characteristic.
- Do not use platform targeting that excludes or favors protected groups. Use broad geography and professional context where compliant.
- Keep Equal Housing Opportunity language on the webpage and printed materials.
- Confirm MLS advertising, photography, brokerage, commission and seller-direct-marketing rules with the listing representative before release.

Official references:

- HUD guidance on housing advertising through digital platforms: <https://www.hud.gov/sites/dfiles/FHEO/documents/FHEO_Guidance_on_Advertising_through_Digital_Platforms.pdf>
- USPS mailbox access notice: <https://about.usps.com/news/state-releases/tx/2010/tx_2010_0909.htm>

## Print package to produce after the URL is final

- 8.5 × 11 inch two-sided property handout
- 5 × 7 inch agent/relocation card
- Tabletop QR sign for open houses
- Social-share image sized for LinkedIn and agent groups
- Unbranded relocation PDF if MLS/agent rules require it

Each piece should use the same hero image, address, price/status, four verified differentiators, Equal Housing Opportunity language, listing representative contact, readable URL and tested QR code.

