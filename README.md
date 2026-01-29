## Yana Sourcing – Upstream Engineering Risk Site

This is a minimal three-page static site intended as an **engineering decision / risk interface** for teams with deployed hardware that are already seeing unexpected failures, drift, or wear. It is not a services brochure.

Pages:
- **Home** (`index.html`): Judgment interface. States that most failures were baked in upstream and names the kinds of irreversible decisions that seeded them.
- **How We Think** (`how-we-think.html`): Judgment logic. Describes what gets examined and what is intentionally ignored when tracing failures back to upstream decisions.
- **Talk** (`talk.html`): Intake interface. A single form that asks only: describe the system, where it is running, and what surprised you.

### Stack and structure

- **HTML/CSS only** – no JavaScript, no build step.
- Single shared stylesheet: `styles.css`.
- Design is intentionally calm, neutral, and memo-like (more engineering review, less product landing).

### Running locally

You can open the site directly from the filesystem:

- On Windows: double-click `index.html` (or open it via your browser’s “Open file” dialog).
- Navigate between pages using the header links (`Home`, `How We Think`, `Talk`).

No local server is required.

### Suggested deployment pattern

The code is static, so any static host works. A low-friction option:

- **Hosting**: GitHub Pages or Netlify (free).
- **Custom domain**: Point your domain’s DNS to the static host (CNAME from `www.your-domain` to the host’s URL).
- **Form handling** (for `talk.html`):
  - Use a form-backend service such as [Formspree](https://formspree.io) or Netlify Forms.
  - Set the `<form>` `action` attribute to the provider’s endpoint to store submissions and trigger email notifications.

This keeps complexity low: no backend code, no database, and minimal ongoing maintenance.

