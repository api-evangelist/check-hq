# Check

Check is an embedded payroll infrastructure platform that lets vertical SaaS, workforce-management, HR, and financial-services companies offer end-to-end U.S. payroll natively inside their own products. Check provides the API, the white-labeled UI, the money movement, and the back-office tax operations so platforms do not have to build them.

Check was founded by the team behind Oyster (acquired by Google in 2015), publicly launched in January 2021 with a USD 35M Series B led by Stripe and Thrive Capital, and announced a USD 75M Series C led by Stripe in 2022. Check is headquartered in New York, NY.

**Corporate site:** [https://www.checkhq.com/](https://www.checkhq.com/)
**Developer docs:** [https://docs.checkhq.com/](https://docs.checkhq.com/)
**Console:** [https://console.checkhq.com/](https://console.checkhq.com/)
**Sandbox:** [https://sandbox.checkhq.com](https://sandbox.checkhq.com)
**GitHub:** [https://github.com/checkhq](https://github.com/checkhq)
**APIs.yml:** [View APIs Index](https://raw.githubusercontent.com/api-evangelist/check-hq/refs/heads/main/apis.yml)

## Scale

- 1M+ employees paid
- 35,000+ businesses powered
- USD 15B+ processed annually
- All 50 U.S. states + D.C.

## Developer Surface

Check exposes four interlocking developer surfaces:

- **[Check Payroll API](https://docs.checkhq.com/reference)** - Versioned REST API (current version `2025-01-01`) covering companies, workplaces, employees, contractors, pay schedules, payroll preview and approval, external and off-cycle payrolls, earnings, post-tax deductions, benefits, net pay splits, bank accounts, payments and money movement, tax parameters, tax filings, tax deposits, employee tax statements (W-2 / W-2C), tax packages, fulfillments, setup and embedded setup, integration partners, webhook configs, communications, and notifications. Bearer-token auth, sandbox simulation endpoints for funding and disbursement, idempotent writes, bulk edit endpoints, and `Accept: application/pdf` for paystubs and paper checks.
- **[Check Components](https://docs.checkhq.com/docs/check-components)** - White-labeled React components for the highest-friction flows: Company Onboard, Run Payroll, Employee Withholdings (W-4), Employee Tax Setup, Company Tax Setup, Company Payment Setup (Plaid + debit authorization), Company Filing Authorization, Filing Preview, Verification Documents, Signatory Agreements, Team Setup, and Full Service Setup Submission.
- **[Check MCP Server](https://docs.checkhq.com/docs/overview-1)** - Model Context Protocol server, available hosted (remote) and self-hosted, exposing the Check API as MCP tools for AI agents and operator copilots.
- **[Check CLI](https://docs.checkhq.com/docs/check-command-line-interface-cli)** - Python CLI installed via `uv tool install`, covering 270 functions across 18 resource groups, designed for scripts and CI/CD with JSON output.

## Authentication and Limits

- **Auth:** Bearer-token (`Authorization: Bearer <API_KEY>`), scoped per environment and partner.
- **Rate limit:** 25 requests/sec per partner, 100 concurrent in-flight requests (not configurable). 429 responses include `Retry-After`; every response carries IETF `RateLimit-Limit` and `RateLimit-Remaining` headers.
- **Pagination, idempotency keys, bulk endpoints, and async preview** are all first-class.

## Webhooks

Check delivers resource-scoped events (`Check-Topic` header) for payrolls, payments, employees, contractors, companies, bank accounts, benefits, post-tax deductions, earning codes and rates, net pay splits, federal EIN verification, tax documents, company filings, requirements, workplaces, pay schedules, processing-status changes, integration access, setups, fulfillments, notifications, and enrollment profiles. See [Webhook Event Types](https://docs.checkhq.com/docs/webhook-event-types).

## Embedded Setup and Operations

Check operates a tiered embedded-setup model. Partners can either:

- Drive setup themselves through the API + Components, or
- Hand off to **Full Service Setup**, where Check operators set up the company, register taxes, migrate from prior payroll providers, and surface remaining blockers via the Requirements API and Onboard Status.

The platform tracks credit limits, funding strikes, processing-period demotions, and bank-account verification document requests at the company level.

## Built-In Integrations

- **Plaid** (bank linking)
- **Next Insurance** (workers' compensation)
- **Clair** (earned wage access)
- **SimplyInsured** (health benefits)
- **Vestwell** / **Human Interest** (401(k))
- **Benbase** (benefits administration)
- OAuth integration framework for partner-to-partner connections

## Notable Partners

Homebase, ServiceTitan, Procare, 7shifts, Housecall Pro, Wave, Zoho, Keka, Zenoti, Playground, Eddy, Miter, Trayd, Warp, Dripos.

## Resources

- **[Documentation](https://docs.checkhq.com/)**
- **[API Reference](https://docs.checkhq.com/reference)**
- **[Quickstart](https://docs.checkhq.com/docs/quickstart)**
- **[Rate Limiting](https://docs.checkhq.com/docs/rate-limiting)**
- **[Webhooks](https://docs.checkhq.com/docs/webhooks-1)**
- **[Changelog](https://www.checkhq.com/resources/changelog)**
- **[Blog](https://www.checkhq.com/resources)**
- **[Help Center](https://help.checkhq.com/)**
- **[Status Page](https://docs.checkhq.com/docs/status-page)**
- **[llms.txt](https://docs.checkhq.com/llms.txt)** (LLM-friendly documentation index)
- **[LinkedIn](https://www.linkedin.com/company/check-technologies)**
- **[Crunchbase](https://www.crunchbase.com/organization/check-2a75)**

## Notable Absences

- No public GitHub repositories at the [checkhq org](https://github.com/checkhq) as of profiling - the CLI and MCP server are distributed but not surfaced as public repos on the org page.
- No public OpenAPI spec download URL on the docs site (the API reference is rendered, not downloadable).
- No public pricing - partner deals are negotiated.

## Maintainers

- Kin Lane (kinlane@gmail.com)
