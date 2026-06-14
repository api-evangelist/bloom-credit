# Bloom Credit GraphQL Schema

## Overview

This conceptual GraphQL schema models the Bloom Credit API, which provides fintech infrastructure for accessing consumer credit data from all three major credit bureaus — Equifax, Experian, and TransUnion. The schema covers consumer registration with consent, tri-bureau credit report retrieval, FICO and VantageScore credit scores, tradeline data, public records, collections, inquiries, disputes, fraud alerts, credit freezes, and real-time monitoring with webhooks.

Source: https://api.bloomcredit.io/docs/

## Schema File

[bloom-credit-schema.graphql](bloom-credit-schema.graphql)

## Type Groups

### Authentication and Access

| Type | Description |
|------|-------------|
| `APIKey` | API key credential with scopes and expiration |
| `Token` | OAuth-style access token returned after authentication |

### Consumer Identity

| Type | Description |
|------|-------------|
| `Consumer` | Top-level consumer record with identity, consent, and linked reports |
| `ConsumerDetails` | Consumer with credit summary and data freshness metadata |
| `ConsumerIdentity` | Full PII — name, SSN, DOB, addresses, phone, email |
| `SSN` | Social Security Number with full, last-four, and masked variants |
| `DOB` | Date of birth with day/month/year and formatted string |
| `Address` | Street address with type (current, previous) flag |
| `ConsentDetails` | FCRA consent record tied to a consumer and permissible purpose |
| `PermissiblePurpose` | FCRA permissible purpose code and description |

### Credit Reports

| Type | Description |
|------|-------------|
| `CreditReport` | Bureau-specific report pulled for a consumer |
| `CreditReportDetails` | Full report contents — scores, tradelines, inquiries, records |
| `DataFreshnessDate` | When the report was pulled and when it expires |

### Credit Scores

| Type | Description |
|------|-------------|
| `CreditScore` | Score record with bureau, model, value, and factors |
| `ScoreModel` | Scoring model name, version, provider, and range |
| `ScoreRange` | Minimum and maximum values for a scoring model |
| `ScoreFactor` | Code and description of a positive or negative score factor |
| `FICO` | FICO score with version, bureau, factors, and date |
| `VantageScore` | VantageScore with version, bureau, factors, and date |

### Tradelines

| Type | Description |
|------|-------------|
| `Tradeline` | Individual account record from a bureau |
| `TradelineDetails` | Creditor, account type, dates, balance, limit, payment history |
| `TradelineType` | Enum: REVOLVING, INSTALLMENT, MORTGAGE, OPEN, COLLECTION, OTHER |
| `AccountHistory` | Month-by-month payment status for an account |
| `PaymentHistory` | Single month payment status with days-late detail |
| `Balance` | Account balance with currency and date |
| `CreditLimit` | Credit limit amount and currency |
| `OpenDate` | Month and year an account was opened |
| `CloseDate` | Month and year an account was closed |

### Inquiries

| Type | Description |
|------|-------------|
| `Inquiry` | Credit inquiry record from a bureau |
| `InquiryDetails` | Creditor, bureau, inquiry type, date, and purpose |
| `InquiryType` | Enum: HARD, SOFT |
| `InquiryDate` | Day, month, year, and formatted date of an inquiry |

### Public Records

| Type | Description |
|------|-------------|
| `PublicRecord` | Court or government record affecting credit |
| `PublicRecordType` | Enum: BANKRUPTCY, JUDGEMENT, TAX_LIEN, CIVIL_SUIT, OTHER |
| `BankruptcyDetails` | Chapter, filed/discharge/dismiss dates, assets, liabilities |
| `Judgement` | Case number, filed date, amount, plaintiff, court |
| `TaxLien` | Filed/released dates, amount, taxing authority |

### Collections

| Type | Description |
|------|-------------|
| `Collection` | Collection account record |
| `CollectionDetails` | Collector, original creditor, account type, dates, amount |
| `CollectionAmount` | Original and current collection balance with currency |

### Summary Types

| Type | Description |
|------|-------------|
| `CreditSummary` | Bureau-level rollup of scores, utilization, age, and inquiries |
| `AccountSummary` | Counts of open, closed, delinquent, and collection accounts |
| `TotalAccounts` | Total account count broken down by type |
| `AccountTypeCount` | Count of accounts for a specific tradeline type |
| `OpenAccounts` | Open account count with total balance and credit limit |
| `DelinquentAccounts` | Delinquent account count and total delinquent amount |
| `UtilizationRate` | Overall and per-account credit utilization |
| `AccountUtilization` | Utilization rate for a single account |
| `OldestAccount` | Oldest account open date, creditor, type, and age in months |
| `NewestAccount` | Newest account open date, creditor, type, and age in months |
| `AgeOfCredit` | Average, oldest, and newest account age in months |
| `HardInquiries` | Hard inquiry counts for 12 months, 24 months, and total |

### Disputes and Fraud

| Type | Description |
|------|-------------|
| `Dispute` | Dispute filed against a bureau item |
| `DisputeDetails` | Item, bureau, reason, supporting docs, timeline |
| `DisputeStatus` | Enum: SUBMITTED, IN_REVIEW, RESOLVED, CLOSED, ESCALATED |
| `FraudAlert` | Active fraud alert on a consumer's bureau file |
| `CreditFreeze` | Credit freeze status per bureau |

### Monitoring and Webhooks

| Type | Description |
|------|-------------|
| `MonitoringDetails` | Real-time credit monitoring enrollment and configuration |
| `Webhook` | Webhook endpoint registration for monitoring alerts |

## Operations

### Queries

- `consumer(id)` — fetch a single consumer record
- `consumers(limit, offset, status)` — list consumers with pagination
- `consumerDetails(id)` — consumer with credit summary and freshness metadata
- `creditReport(id)` — fetch a credit report by ID
- `creditReports(consumerId, bureau)` — list reports for a consumer, optionally filtered by bureau
- `creditScore(consumerId, bureau, model)` — fetch a specific score
- `creditScores(consumerId)` — all scores across bureaus for a consumer
- `tradeline(id)` — fetch a single tradeline
- `tradelines(consumerId, bureau)` — list tradelines for a consumer
- `inquiry(id)` / `inquiries(consumerId, bureau, type)` — inquiry lookup
- `publicRecord(id)` / `publicRecords(consumerId, bureau, type)` — public records
- `collection(id)` / `collections(consumerId, bureau)` — collection accounts
- `creditSummary(consumerId, bureau)` — bureau-level credit summary
- `accountSummary(consumerId, bureau)` — account count summary
- `dispute(id)` / `disputes(consumerId, status)` — disputes
- `fraudAlert(id)` / `fraudAlerts(consumerId)` — fraud alerts
- `creditFreeze(consumerId, bureau)` / `creditFreezes(consumerId)` — freezes
- `monitoringDetails(consumerId)` — monitoring enrollment status
- `webhook(id)` / `webhooks` — webhook configuration
- `apiKey(id)` / `apiKeys` — API key management

### Mutations

- `createConsumer` / `updateConsumer` / `deleteConsumer` — consumer lifecycle
- `pullCreditReport` — trigger a bureau report pull with permissible purpose
- `createDispute` / `updateDisputeStatus` — dispute management
- `activateFraudAlert` / `removeFraudAlert` — fraud alert management
- `freezeCredit` / `thawCredit` — credit freeze management
- `enrollMonitoring` / `cancelMonitoring` — monitoring enrollment
- `createWebhook` / `updateWebhook` / `deleteWebhook` — webhook management
- `generateToken` — exchange an API key for an access token

## Named Types Count

This schema defines **63 named types** (excluding input types and enums used as arguments):

Consumer, ConsumerDetails, ConsumerIdentity, SSN, DOB, Address, ConsentDetails, PermissiblePurpose, CreditReport, CreditReportDetails, DataFreshnessDate, CreditScore, ScoreModel, ScoreRange, ScoreFactor, FICO, VantageScore, Tradeline, TradelineDetails, AccountHistory, PaymentHistory, Balance, CreditLimit, OpenDate, CloseDate, Inquiry, InquiryDetails, InquiryDate, PublicRecord, BankruptcyDetails, Judgement, TaxLien, Collection, CollectionDetails, CollectionAmount, CreditSummary, AccountSummary, TotalAccounts, AccountTypeCount, OpenAccounts, DelinquentAccounts, UtilizationRate, AccountUtilization, OldestAccount, NewestAccount, AgeOfCredit, HardInquiries, Dispute, DisputeDetails, FraudAlert, CreditFreeze, MonitoringDetails, Webhook, APIKey, Token, Query, Mutation

Enums: Bureau, TradelineType, InquiryType, PublicRecordType, DisputeStatus
