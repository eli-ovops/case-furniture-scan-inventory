# Furniture scan-based inventory

A per-carton barcode inventory system connecting receiving, stock transfers, dispatch and corrections for a furniture brand.

## Background

The client needed to follow cartons across warehouse locations without counting a retried submission twice. Transfers and corrections also needed to preserve consistent stock quantities.

## My role

I led the requirements and workflow design, developed the system with an AI-assisted workflow, and handled testing and maintenance.

## Architecture / Tech stack

A TypeScript / React interface connects to Cloudflare Workers and a D1 database. The workflows cover per-carton scanning, receiving, transfers, dispatch, permissions and undo/correction operations.

## Hard parts

- **Repeated requests.** I implemented duplicate-submission protection and checked retried operations so the same request would not be counted again.
- **Stock consistency across locations.** I checked the source quantity, destination quantity and total stock when validating transfers, as well as rejection of insufficient stock.
- **Correcting mistakes without losing the original operation.** Undo/correction flows were tied back to the original transaction, with checks around permissions and resubmission.

## Outcome

The system was delivered. Existing local and cloud test records cover the inventory loop, repeated submissions and insufficient-stock cases; these are historical test records, not a claim of current live operation.

[Project record](https://www.eliai.cn/cases/p09.html)

This is an anonymised case study. Client source code, customer identities and operational data are not included.
