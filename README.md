# Northstar — Wealth Engineering Workspace

Independent interview demonstration prepared for Wenting Wang's Thrivent Engineering Manager conversations. Not affiliated with or endorsed by Thrivent. All financial data, clients, metrics, incidents, and delivery records are synthetic.

## Run immediately
Open `index.html` in a modern browser. No installation, compilation, API key, or external service is needed. Browser storage behavior under file:// varies; use GitHub Pages or `python3 -m http.server 8000` for predictable persistence.

## Deploy to GitHub Pages (simplest option)
1. Create a GitHub repository, for example `wealth-engineering-demo`.
2. Extract this ZIP. Upload the CONTENTS of `thrivent-engineering-demo` to the repository root. `index.html`, `app.js`, `engine.js`, and `styles.css` must be at the root, not inside another folder.
3. Commit the files to `main`.
4. Open repository Settings → Pages → Build and deployment.
5. Choose **Deploy from a branch**, branch **main**, folder **/(root)**, and Save.
6. Wait for deployment, then use the site's link shown by GitHub Pages. Do not use the repository code URL as the demo URL.

Relative asset links and hash routes work under a GitHub repository subpath. No SPA rewrite or custom domain is needed. Include `.nojekyll` if uploading using Git or a client that supports dotfiles.

### Optional GitHub Actions deployment
The ZIP includes `.github/workflows/pages.yml`. Instead of branch deployment, select **GitHub Actions** under Settings → Pages and run **Deploy GitHub Pages** from the Actions tab. The workflow deploys on pushes to `main` and supports manual runs. Choose either deployment method; you do not need both. GitHub Pages availability and public/private repository support depend on your account and organization settings.

## Features
- Overview of synthetic account data, initiative delivery, and service health.
- Search/filter accounts, inspect sample allocation, and export sample CSV.
- Add initiatives, update status, and retain local changes in browser storage.
- Run a simulated incident recovery; account reconciliation and assistant responses update together.
- Draft an incident communication without sending it.
- Release-readiness checklist, people leadership agreements, and build/buy criteria.
- Reference AWS architecture connecting ingestion, Python transformation, S3, PostgreSQL, APIs, monitoring, and CI/CD.
- Local chatbot with account lookup, leadership summary, incident drafts, architecture explanations, and source labels.

## Assistant behavior and limitations
The chatbot is **deterministic JavaScript intent matching and retrieval**, not an LLM. It uses current in-memory demo state and curated text. It cannot reason about arbitrary documents, access enterprise data, run tools against AWS, execute trades, or provide financial recommendations. Responses have source labels referring to demo screens, not externally verified citations. Conversation messages are session-only; workspace state persists locally. Use synthetic inputs only.

A real AI version needs a server-side authenticated gateway, secret management, permission-aware retrieval, model evaluation, prompt-injection defenses, audit controls, rate limiting, monitoring, and approval boundaries. Never put a model API key in GitHub Pages JavaScript. This package does not implement those production capabilities.

## Five-minute interview walkthrough
1. **Overview:** Explain how account accuracy, delivery commitments, and service health connect engineering work to client outcomes.
2. **Accounts:** Search `Morgan`, open AC-1002, and identify its reconciliation exception.
3. **Service health:** Review the recovery runbook and click the simulated validation and recovery action. Explain why replay requires duplicate-safe writes and reconciliation.
4. **Assistant:** Ask `What needs my attention?` or `Draft incident update`. Show that responses reflect the updated state and remain drafts.
5. **Delivery:** Add an initiative or change its status. Discuss roadmap trade-offs, capacity, and product partnership.
6. **Team / Architecture:** Discuss ownership, coaching, release gates, and how a production AWS system would differ from this static demonstration.

## Data & operating boundaries
State is local to the browser/origin and is not synchronized between people or devices. This is not a secure client portal, production audit log, banking system, or deployed cloud architecture. Reset clears the demo state and checklist. Real service metrics and actual recovery evidence must come from production systems.

## Validation
- JavaScript syntax checks passed.
- Assistant checks cover account lookup, state-sensitive summaries, architecture, unsupported requests, and financial-action refusal.
- Browser verified dashboard rendering, account search/detail, simulated incident recovery, and assistant draft reflecting the resolved state.
- Responsive CSS included; narrow-screen rendering has not been browser-verified.
