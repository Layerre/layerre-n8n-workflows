# Layerre n8n Workflow Templates

Community workflow templates using the [n8n Layerre node](https://www.npmjs.com/package/n8n-nodes-layerre) for image generation at scale with [Layerre](https://layerre.com).

## Templates

**[Quick Start](templates/quick-start.json)** – Create template from a Canva design, then create a single variant. Good for learning. Needs: Layerre API key, Canva design.

**[Spreadsheet to Layerre Images](templates/spreadsheet-to-layerre-variants.json)** – Bulk personalized images using **Google Sheets (Get Rows)**. One row per variant. Preconfigured with the [Layerre Sheets Example](https://docs.google.com/spreadsheets/d/1x8X_qZaoXkrIKGVlhCC25du8ht42UKinRPtmjThpTSE/edit?usp=sharing) (2 columns: **Text**, **Image**). Needs: Layerre API key, Canva template, Google Sheet credentials.

**[Webhook to Layerre to Slack](templates/webhook-to-layerre-to-slack.json)** – **Webhook** (e.g. form submissions, Typeform, Tally) → create one personalized image per request → **Slack** (post to channel) and **Respond to Webhook** (return image URL). Needs: Layerre API key, Canva template, Slack credentials.

**[Airtable to Layerre Images](templates/airtable-to-layerre-to-airtable.json)** – **Airtable (List records)** → create one variant per record → **Airtable (Update)** to write the rendered image URL back into each record. Needs: Layerre API key, Canva template, Airtable credentials.

## Setup

1. **Install the node:** `npm install n8n-nodes-layerre` then restart n8n.
2. **API key:** [layerre.com/app/settings/api](https://layerre.com/app/settings/api) – create a key (starts with `lyr_`).
3. **In n8n:** Credentials → Add Credential → "Layerre API" → paste key.

Import a workflow JSON in n8n (Workflows → Import from File), add your credentials, and follow the sticky notes in the canvas. For the Spreadsheet to Variants template, you can [make a copy of the example Google Sheet](https://docs.google.com/spreadsheets/d/1x8X_qZaoXkrIKGVlhCC25du8ht42UKinRPtmjThpTSE/edit?usp=sharing) (columns: **Text**, **Image**) and connect it in the Get Rows node.

## Common issues

- **Unauthorized:** Check API key in credentials; no extra spaces.
- **Template not found:** Use the template ID from the "Create Template" node output, or pick from the dropdown.
- **Layer not found:** Re-create the template if you changed the Canva design.
- **Timeout on large runs:** Process in smaller batches (e.g. Split in Batches node).

## Contributing

Submit templates via pull request. Required: sticky notes for overview and steps, markdown with `## H2` headings, no hardcoded API keys, descriptive node names, real use case. See [n8n template guidelines](https://n8n.notion.site/Template-submission-guidelines-9959894476734da3b402c90b124b1f77).

## Links

- [Layerre docs](https://layerre.com/docs) · [n8n-nodes-layerre](https://github.com/layerre/n8n-nodes-layerre) · [n8n docs](https://docs.n8n.io) · [n8n community](https://community.n8n.io) · [Layerre support](mailto:hello@layerre.com)

[MIT](LICENSE)
