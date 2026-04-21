# Bloom Credit (bloom-credit)
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
