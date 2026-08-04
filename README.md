# Bloom Credit (bloom-credit)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Bloom Credit is a fintech infrastructure company providing API access to consumer credit data from all three major credit bureaus (Equifax, Experian, TransUnion). The platform enables fintechs, lenders, and financial services applications to retrieve credit reports, credit scores, trade line data, and enroll consumers in real-time credit monitoring. Bloom Credit provides multi-language SDKs (Python, Ruby, TypeScript, R, Go) and supports the Metro 2 credit reporting format.

**URL:** [https://bloomcredit.io](https://bloomcredit.io)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Credit Bureau, Credit Reports, Credit Scores, Fintech, Lending, Personal Finance

## Timestamps

- **Created:** 2025-02-24
- **Modified:** 2026-04-19

## APIs

### Bloom Credit API
RESTful API providing access to consumer credit data from Equifax, Experian, and TransUnion. Supports consumer registration with consent, tri-bureau credit report retrieval, FICO and VantageScore credit scores, trade line data, and real-time credit monitoring with webhook alerts.

**Human URL:** [https://bloomcredit.io/](https://bloomcredit.io/)

#### Tags:

 - Credit Bureau, Credit Reports, Credit Scores, Fintech, Lending

#### Properties

- [Documentation](https://bloomcredit.io/)
- [OpenAPI](openapi/bloom-credit-api-openapi.yaml)
- [NaftikoCapability](capabilities/bloom-credit-credit-intelligence.yaml)
- [SpectralRules](rules/bloom-credit-spectral-rules.yml)
- [Vocabulary](vocabulary/bloom-credit-vocabulary.yaml)

## Common Properties

- [Website](https://bloomcredit.io/)
- [GitHub Organization](https://github.com/bloomcredit)
- [Python SDK](https://github.com/bloomcredit/bloomPy)
- [TypeScript SDK](https://github.com/bloomcredit/bloomTypescript)
- [Terms of Service](https://bloomcredit.io/terms)
- [Privacy Policy](https://bloomcredit.io/privacy)

## Features

| Name | Description |
|------|-------------|
| Tri-Bureau Credit Reports | Pull full credit reports from Equifax, Experian, and TransUnion in a single API call with structured trade line, inquiry, and public record data. |
| Credit Score Retrieval | Access FICO 8, VantageScore 3.0, and other scoring models from all three major credit bureaus for comprehensive creditworthiness assessment. |
| Trade Line Data | Retrieve individual account and trade line records including payment history, balances, credit limits, and account status across bureaus. |
| Real-Time Credit Monitoring | Enroll consumers in monitoring subscriptions that trigger webhook alerts for new accounts, inquiries, derogatory marks, and score changes. |
| Consumer Consent Management | Built-in consumer registration and consent workflow ensuring FCRA-compliant access to credit bureau data with auditable consent records. |
| Multi-Language SDKs | Official SDKs for Python, TypeScript, Ruby, R, and Go enabling rapid integration into existing fintech and data science workflows. |

## Use Cases

| Name | Description |
|------|-------------|
| Loan Underwriting | Lenders pull tri-bureau credit reports and scores during loan origination to assess creditworthiness and determine loan terms. |
| Credit Building Apps | Consumer fintech applications provide users with free credit score monitoring and personalized recommendations to improve their credit profiles. |
| Tenant Screening | Property management platforms use Bloom Credit to run credit checks during rental application processing. |
| Credit Counseling | Financial advisors and credit counselors access full credit reports and trade line data to create personalized debt management plans. |
| Account Origination | Financial institutions use credit data during account opening to verify identity and assess risk for credit card and deposit products. |

## Integrations

| Name | Description |
|------|-------------|
| Equifax | Direct integration with Equifax for credit report and score data including FICO 8 and other proprietary scoring models. |
| Experian | Direct integration with Experian for credit reports, FICO scores, and VantageScore data with real-time data freshness. |
| TransUnion | Direct integration with TransUnion for credit reports and scores with support for TransUnion-specific data attributes. |
| Plaid | Complementary integration where Bloom Credit's credit data can be combined with Plaid's bank account and income verification for full financial profiles. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Bloom Credit API](openapi/bloom-credit-api-openapi.yaml)

### JSON Schema

- [Consumer](json-schema/bloom-credit-consumer-schema.json)
- [Credit Score](json-schema/bloom-credit-credit-score-schema.json)
- [Trade Line](json-schema/bloom-credit-trade-line-schema.json)
- [Monitoring Enrollment](json-schema/bloom-credit-monitoring-enrollment-schema.json)

### JSON Structure

- [Consumer](json-structure/bloom-credit-consumer-structure.json)
- [Credit Score](json-structure/bloom-credit-credit-score-structure.json)
- [Trade Line](json-structure/bloom-credit-trade-line-structure.json)
- [Monitoring Enrollment](json-structure/bloom-credit-monitoring-enrollment-structure.json)

### JSON-LD

- [Bloom Credit Context](json-ld/bloom-credit-context.jsonld)

### Examples

- [Consumer Example](examples/bloom-credit-consumer-example.json)
- [Credit Score Example](examples/bloom-credit-credit-score-example.json)
- [Trade Line Example](examples/bloom-credit-trade-line-example.json)
- [Monitoring Enrollment Example](examples/bloom-credit-monitoring-enrollment-example.json)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Bloom Credit API](capabilities/shared/bloom-credit-api.yaml) — 6 operations for consumer registration, credit reports, scores, trade lines, and monitoring

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Bloom Credit Credit Intelligence](capabilities/bloom-credit-credit-intelligence.yaml) | Bloom Credit API | 6 | Fintech Developers, Lenders and Underwriters, Credit Counselors, Consumer Finance Apps |

## Vocabulary

- [Bloom Credit Vocabulary](vocabulary/bloom-credit-vocabulary.yaml) — Unified taxonomy mapping 5 resources, 4 actions, 1 workflow, and 4 personas across operational (OpenAPI) and capability (Naftiko) dimensions

## Rules

- [Bloom Credit Spectral Rules](rules/bloom-credit-spectral-rules.yml) — 30 rules across 12 categories enforcing Bloom Credit API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
