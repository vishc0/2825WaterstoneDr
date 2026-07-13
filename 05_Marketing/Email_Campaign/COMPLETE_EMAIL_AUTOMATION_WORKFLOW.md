# 2825 Waterstone Drive — Complete Email Automation Workflow

## Recommended architecture

- **Google Sheets:** campaign database
- **Google Apps Script:** daily scheduler and Gmail integration
- **Gmail:** drafts, sending, replies and opt-outs
- **OpenAI API or Gemini API:** research, scoring and personalization
- **Private GitHub repository:** scripts, prompts, templates and version history
- **Google Drive:** approved property materials

Use GitHub for version control, not as the primary daily execution engine. Apps Script is better suited to Gmail and Sheets automation.

## 1. Obtain approval

Before automation, obtain written approval from the listing agent and broker for:

- Direct owner outreach
- Email copy
- Website and one-pager
- Buyer-agent compensation language
- Daily follow-ups
- Cash-offer requests
- Inquiry routing
- Paid advertising

The signed listing agreement is not currently in the project folder.

## 2. Create the campaign Sheet

Create these columns:

`Name`, `Organization`, `Role`, `Email`, `Phone`, `Source URL`, `Segment`, `Verified Date`, `Status`, `Last Contacted`, `Next Follow-up`, `Opted Out`, `Draft ID`, `Response`, `Notes`

Recommended statuses:

- Research
- Needs verification
- Ready
- Draft created
- Approved to send
- Sent
- Replied
- Follow-up due
- Opted out
- Do not contact

## 3. Build the contact pool

Research professional contacts from:

- Relocation-management companies
- Corporate mobility providers
- Luxury buyer-agent teams
- CRP/SCRP/GMS relocation agents
- Exclusive buyer agents
- Corporate housing providers
- Destination-service companies
- Executive relocation departments
- Private-client brokerages

Do not scrape private consumer information or target demographic, religious or ethnic groups.

## 4. AI research step

Each day, the AI should:

1. Find new professional contacts.
2. Confirm the organization handles relocation, buyer representation or executive housing.
3. Capture the public source URL.
4. Identify the person’s role.
5. Score the contact from 1–5.
6. Explain why the property may fit their clients.
7. Reject investors, wholesalers and irrelevant contacts.
8. Add only verified candidates to the Sheet.

The AI must use approved property facts only.

## 5. Contact verification

Before a contact becomes `Ready`:

- Verify the email on the organization’s public website or professional directory.
- Confirm the person’s role.
- Confirm that the organization serves Atlanta, North Fulton, South Forsyth or corporate relocation.
- Record the verification date.
- Never send to unverified scraped addresses.

## 6. Personalization step

The AI generates:

- One subject line
- One short personalized opening
- The approved property summary
- A clear agent-routing instruction
- A compliant opt-out line

It must not invent buyer-agent compensation, permits, waterfront status, legal apartment status, guaranteed views, additional bedrooms or investment returns.

## 7. Draft creation

Apps Script should create Gmail drafts by default.

Daily limits:

- Five new drafts or messages
- One follow-up per day maximum
- No repeated contact before the follow-up date
- No send if `Opted Out = Yes`
- No send if listing-agent approval is missing

## 8. Human approval

Review Gmail drafts and approve only messages that:

- Use correct facts
- Have a verified recipient
- Include brokerage/listing-agent routing
- Avoid unsupported claims
- Include a physical mailing address
- Include an opt-out instruction

Change the row status to `Approved to send` only after review.

## 9. Sending

Apps Script sends only approved rows.

Log the following for every message:

- Timestamp
- Gmail message ID
- Recipient
- Subject
- Campaign segment
- Follow-up date

Commercial email must use truthful sender information and an opt-out mechanism under CAN-SPAM. Do not automate cold SMS; marketing texts require documented consent and create materially higher compliance risk.

## 10. Reply processing

A second daily workflow should inspect replies and classify them as:

- Interested buyer
- Referral opportunity
- Requests packet
- Requests showing
- Not relevant
- Remove me
- Bounce
- Out of office

When a recipient requests removal:

1. Set `Opted Out = Yes`.
2. Set status to `Do not contact`.
3. Add the address to a suppression list.
4. Prevent all future sends.

## 11. Follow-up workflow

After 5–7 business days:

- If there is no reply, create one brief follow-up draft.
- If there is still no reply after the second message, mark `No response`.
- Do not continue daily emailing the same contact.

## 12. Daily report

Each morning, generate a report containing:

- New contacts researched
- Drafts created
- Messages sent
- Replies received
- Interested contacts
- Follow-ups due
- Bounces
- Opt-outs
- Errors
- Recommended next action

## Automation options

### Google Apps Script + Google Sheets + Gmail + API

Best for this campaign because it is inexpensive, Google-native and easy to audit.

### Zapier

Fastest no-code option:

`Schedule → Google Sheets → AI → Gmail draft → Sheet log`

Use it for a prototype, but task-based pricing may become expensive.

### Make

Good for branching logic, scoring, reply classification and multi-step workflows.

### n8n

Best for technical control, self-hosting and complex AI workflows. It requires more maintenance and secure hosting.

### GitHub Actions

Useful for scheduled research jobs, validation and code deployment. Do not use it for unrestricted email sending because Gmail authentication and human approval are more complicated.

## Recommended implementation order

1. Obtain listing-agent approval.
2. Create the Google Sheet.
3. Add and verify the first 14 relocation contacts.
4. Build Apps Script in a private GitHub repository.
5. Run AI research in test mode.
6. Generate Gmail drafts only.
7. Manually review and send the first five.
8. Test reply and opt-out handling.
9. Enable daily drafts.
10. Enable automatic sending only for explicitly approved rows.

## Compliance references

- FTC CAN-SPAM guidance: https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide
- Georgia advertising rule: https://www.law.cornell.edu/regulations/georgia/Ga-Comp-R-Regs-R-520-1-.09
- Zapier pricing: https://zapier.com/pricing
- Make AI agents: https://help.make.com/create-your-first-ai-agent
- n8n Gmail/GPT/Sheets workflow: https://n8n.io/workflows/7839-automated-email-classification-and-response-system-with-gmail-gpt-and-sheets/
