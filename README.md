# SAF-T BG Bridge Showcase

This repository presents the concept and planned architecture of a SAF-T preparation bridge for Bulgarian accounting data.

> This is a public showcase repository.  
> It does not contain production code, client data, real accounting exports, mappings, validation logic or internal business know-how.

## Purpose

The introduction of SAF-T reporting creates a major operational challenge for accounting offices and accounting software users.

The goal of SAF-T BG Bridge is to help transform accounting system exports into structured, reviewable and controllable preparation workflows before generating or validating an audit-file candidate.

The project is designed from the perspective of real accounting practice: source data, missing fields, mapping risks, manual confirmations, validation checks and accountant review.

## Initial focus

The first implementation target is accounting data exported from Megasoft.

The architecture is designed so that other accounting systems may be tested later, provided they can deliver the required accounting, document and master-data exports.

## Core idea

SAF-T BG Bridge is not planned as a simple “one-click XML generator”.

It is planned as a preparation and validation layer between accounting software exports and the final SAF-T audit file.

The system should help accountants answer the practical questions:

- Do we have the required source data?
- Which fields are missing?
- Which mappings are confirmed?
- Which values are derived by rule?
- Which records require manual review?
- Which parts are blocked until source data is completed?

## Planned architecture

The project is structured around three working modules:

### Monthly Accounting and Documents Module

Covers the monthly SAF-T scope, including:

- Header;
- MasterFiles;
- GeneralLedgerEntries;
- SourceDocuments;
- VAT and document-related data;
- accounting entries and control totals.

### Annual Assets Module

Covers the annual SAF-T assets scope, including:

- fixed assets;
- depreciation data;
- acquisition and disposal transactions;
- accounting and tax depreciation controls;
- asset readiness reports.

### On-Demand Stocks Module

Covers the on-demand stock and inventory scope, including:

- products;
- units of measure;
- warehouses;
- physical stock;
- stock movements;
- stock movement lines;
- product and movement type mappings.

## Key principles

### Source-data first

The system should not invent accounting, tax, document, counterparty, product, stock or asset data.

Each field should have a traceable status, such as:

- available from source;
- derived by rule;
- enriched from external source;
- manually confirmed;
- missing;
- blocked.

### Review before generation

The accountant must be able to review missing data, mapping decisions, validation warnings and control differences before any final output is generated.

### Separation of accounting entries and source documents

The project distinguishes between:

- accounting entries as recorded in the accounting system;
- source documents such as invoices, payments, assets and stock movements.

This distinction is important because SAF-T may require more document-level detail than standard accounting entries provide.

## Data readiness workflow

The first milestone is planned as a data readiness and mapping module.

It should produce:

- readiness report;
- missing fields report;
- account mapping report;
- counterparty enrichment report;
- invoice line risk report;
- asset readiness report;
- stock readiness report;
- validation issues report.

## Business value

The project is intended to help accounting teams:

- prepare earlier for SAF-T requirements;
- identify gaps in accounting and document data;
- understand whether existing software exports are sufficient;
- reduce manual uncertainty;
- document mapping and confirmation decisions;
- avoid blind generation of incomplete audit files;
- create a controlled review workflow before submission.

## Current status

Architecture and scope planning stage.

Initial guides have been prepared for:

- master architecture and scope;
- monthly accounting and documents;
- annual assets;
- on-demand stock movements.

The next development step is a data readiness and mapping prototype for Megasoft exports.

## Data safety

This public repository is a showcase only.

Production code, real accounting data, client exports, mappings, validation rules and internal implementation details are private.
