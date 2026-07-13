# 2825 Waterstone Drive — Targeted Email Campaign and AI Automation Plan

## Recommendation

Use Google Apps Script as the daily execution layer because the campaign naturally uses Gmail, Google Sheets and Google Drive. Use GitHub as the version-controlled home for prompts, message templates, schemas, campaign rules and Apps Script source code.

Do not let an AI agent send unrestricted daily email. The safe workflow is:

1. AI researches and scores potential professional contacts.
2. Apps Script writes candidates to a Google Sheet.
3. AI generates a personalized draft.
4. The owner or listing representative reviews the draft.
5. Apps Script creates a Gmail draft or sends only an approved message.
6. Replies, opt-outs and follow-ups are logged automatically.

## Initial target list

The first campaign should target relocation professionals and buyer-agent channels, not wholesalers or distressed-property investors.

| Priority | Organization | Representative | Contact |
|---|---|---|---|
| 1 | Atlanta Fine Homes Sotheby’s | Leigh Massey Hayes, CRP | 404-974-4325; leigh@atlantafinehomes.com |
| 2 | Ansley Atlanta | Christi Hernandez, CRP | 404-290-2182; christihernandez@ansleyatlanta.com |
| 3 | Berkshire Hathaway HomeServices GA | Janet Mauldin, CRP/GMS | 678-352-3346; janet.mauldin@bhhsgeorgia.com |
| 4 | Berkshire Hathaway HomeServices GA | Kathy Connelly, SCRP | 678-352-3321; kathy.connelly@bhhsgeorgia.com |
| 5 | Harry Norman Realtors | Stan Baker | 678-491-0402; stan.baker@harrynorman.com |
| 6 | BHGRE Metro Brokers | Kay Oliver, CRP | 404-236-7015; kay.oliver@metrobrokers.com |
| 7 | BHGRE Metro Brokers | Mike Busik | 404-236-7103; mike.busik@metrobrokers.com |
| 8 | Norluxe Realty | Jeremy Norman | 470-223-1981; jnorman@norluxerealty.com |
| 9 | Compass Relocation Group | Mike Roman | 404-771-0826; mike.roman@compassrelocationgroup.com |
| 10 | Focus Relocation | Charles Morrow | 770-714-6184; charlesmorrow@focusrelocation.com |
| 11 | Graebel Relocation | Brian Fudenberg | 612-220-8596; brian.fudenberg@graebel.com |
| 12 | SIRVA | Andrea Whitaker | 804-514-8714; andrea.whitaker@sirva.com |
| 13 | Weichert Workforce Mobility | Jana Smith | 480-371-7700; janasmith@weichertwm.com |
| 14 | AIRES | Steve Alverson | 609-226-0358; salverson@aires.com |

Verify every address and role immediately before sending. The directory is a lead source, not proof that each person still handles this market.

## Campaign cadence

- One-time launch: 14 individually personalized emails.
- Daily thereafter: five new professional contacts per weekday.
- Follow-up: once after 5–7 business days.
- Stop after two unanswered messages.
- Log every send, reply, referral, opt-out and follow-up date.

Potential additional channels include luxury buyer-agent teams, exclusive buyer agents, CRP/SCRP/GMS relocation agents, corporate mobility providers, destination-service firms, executive housing providers, employer mobility departments, private-client brokerages, agent previews, brokerage-office distribution, approved direct mail, and listing-agent-approved paid search/social advertising.

Do not target churches, ethnic associations, schools or demographic groups based on protected characteristics. Target professional housing and relocation functions.

## Email template

**Subject:** Relocation-ready home in South Forsyth — buyer-agent brief

Hello [Name],

I’m sharing a property that may fit an executive relocation, multigenerational household, or buyer seeking substantial work-from-home and guest flexibility.

**2825 Waterstone Drive, Cumming, GA 30041**  
$1,150,000 | 6 bedrooms | 5 full baths

Highlights include a finished terrace level with kitchen, bedroom and full bath; flexible media and recreation spaces; multiple work-from-home zones; rebuilt decks; seasonal wooded and creek outlooks; and Waterstone Falls amenities.

The public listing and buyer-agent packet are available here: [approved link]

If you have a buyer relocating into South Forsyth or North Fulton, I would be glad to provide the relocation brief, floor-by-floor layout, showing instructions and available diligence materials. Please route all inquiries through Lavanya Thadiparthi, Sekhars Realty LLC, 404-808-9978.

If these property notices are not relevant, reply “remove” and I will not contact you again.

Regards,  
[Sender name]  
[Physical mailing address]  
[Email]  
[Phone]

## Compliance gates

Before launch, obtain written approval from the listing agent and broker for the sender identity, email copy, website/one-pager, buyer-agent compensation language, owner-direct outreach, paid advertising, cash-offer requests and inquiry routing.

The signed listing agreement is not currently in this project folder. Do not assume the owner may independently advertise or negotiate. Georgia advertising rules treat websites, email, flyers, social media, email farming and text messaging as advertising media.

Commercial email must use truthful sender information, identify the sender, include a physical mailing address and provide a working opt-out mechanism. Do not send unsolicited marketing SMS. Use SMS only after documented prior consent.

The 3% buyer-agent compensation reference in older project materials must be confirmed in writing before distribution.

## Google Apps Script workflow

Create a Google Sheet with columns:

`Name`, `Organization`, `Role`, `Email`, `Phone`, `Source URL`, `Segment`, `Verified Date`, `Status`, `Last Contacted`, `Next Follow-up`, `Opted Out`, `Draft ID`, `Notes`.

Schedule one daily Apps Script trigger. It should:

1. Select up to five rows with `Status = Ready`.
2. Skip rows missing a verified email or marked opted out.
3. Ask the AI model for a short personalization based only on approved facts.
4. Create Gmail drafts by default.
5. Send only rows marked `Approved to Send`.
6. Apply a Gmail label such as `Waterstone Campaign`.
7. Log the Gmail draft/message ID and timestamp.
8. Process replies and mark opt-outs immediately.

Use a daily cap, duplicate-email check, unsubscribe suppression list, and manual approval gate. Keep the API key in Apps Script Properties or Secret Manager, never in the Sheet or GitHub.

## Tool choices

### Best fit: Google Apps Script + Gmail + Sheets + OpenAI API

Use this when the user wants low cost, Google-native operation and full control. Apps Script handles the daily trigger, Sheets acts as the campaign database, Gmail creates drafts, and the model researches or personalizes only within approved instructions.

### GitHub

Use GitHub for source control, review history, prompt versions, test fixtures, campaign-policy files and deployment documentation. Do not use a public GitHub repository for contact data, private listing documents, API keys or personal information. GitHub Actions can run scheduled jobs, but Gmail authentication and secrets are more complex than Apps Script, and a scheduled action can accidentally send mail without a human review step.

### Zapier

Best for a quick no-code prototype: schedule trigger → Google Sheets → AI step → Gmail draft → log result. It is easier to launch but can become expensive as every research, AI and email action consumes tasks. Use drafts, not automatic sending, initially.

### Make

Best for visual branching and lower-cost multi-step workflows. It supports Gmail, Sheets and AI providers and is a good alternative if the campaign later needs scoring, routing, reply classification and notifications.

### n8n

Best for technical control, self-hosting and complex agent workflows. It can connect Gmail, Google Sheets and GPT, but requires more maintenance, secure hosting, OAuth setup and monitoring.

### HubSpot or another CRM

Use only if the campaign becomes an ongoing lead-management process with many contacts, stages, tasks and reporting needs. Do not buy a CRM just for the initial 14-contact experiment.

## Recommended implementation order

1. Obtain listing-agent/broker written approval.
2. Verify the 14 initial contacts.
3. Create the campaign Sheet and suppression list.
4. Build Apps Script in a private GitHub repository.
5. Generate drafts only.
6. Review and send the first five manually.
7. Inspect replies, bounces and opt-outs for one week.
8. Add a daily trigger only after the workflow behaves correctly.

## Cash-offer alternatives

Mark Spain and Opendoor are worth contacting for no-obligation written cash offers, subject to listing-agent approval. Zillow is primarily a listing and lead-generation channel; its Atlanta cash-offer path routes qualifying sellers to a partner such as Opendoor. Treat these offers as a liquidity floor and compare net proceeds, fees, repairs, concessions, timing and listing-agreement obligations. They should not replace the primary buyer-agent and relocation campaign without a written comparison.

## Source links

- Metro Atlanta Relocation Council: https://www.marcatlanta.org/relocation-management-companies
- Metro Atlanta relocation real-estate providers: https://www.marcatlanta.org/real-estate-relocation-services
- FTC CAN-SPAM guidance: https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide
- Georgia advertising rule: https://www.law.cornell.edu/regulations/georgia/Ga-Comp-R-Regs-R-520-1-.09
- Zapier pricing: https://zapier.com/pricing
- Make AI agents: https://help.make.com/create-your-first-ai-agent
- n8n Gmail/GPT/Sheets workflow: https://n8n.io/workflows/7839-automated-email-classification-and-response-system-with-gmail-gpt-and-sheets/
- Mark Spain Atlanta: https://markspain.com/atlanta
- Opendoor Atlanta: https://www.opendoor.com/sell/atlanta
- Zillow selling options: https://www.zillow.com/sell/
