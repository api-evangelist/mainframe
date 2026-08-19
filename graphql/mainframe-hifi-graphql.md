---
generated: '2026-08-13'
method: searched
source: https://github.com/hifi-finance/hifi-subgraph/blob/main/schema.graphql
ownership_note: >-
  This GraphQL schema is served from hifi.finance / github.com/hifi-finance rather than
  mainframe.co. It is attributed to Mainframe because Mainframe's own homepage lists Hifi as one of
  its four portfolio products, docs.hifi.finance carries the footer "Copyright (c) 2025 Mainframe
  Group Inc.", the MainframeHQ GitHub organization records its Twitter handle as HifiFinance, and
  the github.com/hifi-finance organization holds the repositories for THREE of Mainframe's four
  named portfolio products (hifi, pooled-nft, spreadsheet/Sheet Heads). NOT to be confused with the
  separate catalog entry `hifi` (hifi.com / production.hifibridge.com), a different company doing
  stablecoin money movement.
---

# Mainframe / Hifi Protocol GraphQL

Mainframe Group, Inc. publishes no REST API and no OpenAPI. The only machine-readable contract on
any Mainframe-controlled surface is the **GraphQL schema of the Hifi Protocol subgraph** — the
Graph Protocol index of the Hifi fixed-rate, fixed-term lending protocol.

The SDL is saved verbatim to
[`mainframe-hifi-subgraph-schema.graphql`](mainframe-hifi-subgraph-schema.graphql) (1,939 bytes,
fetched 2026-08-13 from `raw.githubusercontent.com/hifi-finance/hifi-subgraph/main/schema.graphql`,
HTTP 200).

## Hifi Protocol Subgraph

**Documented endpoint:** `https://thegraph.com/hosted-service/subgraph/hifi-finance/hifi`
(published at https://docs.hifi.finance/protocol/developers/data)

**Endpoint status when probed 2026-08-13: HTTP 404.** The Graph's hosted service — the only
endpoint Hifi's developer documentation names — no longer resolves this subgraph. No replacement
Subgraph Studio / decentralized-network endpoint is published in the docs, so the documented
GraphQL surface is **not currently callable**. The schema below is therefore a real contract with
no reachable server, and no live introspection was possible.

**Repository:** https://github.com/hifi-finance/hifi-subgraph (public, last pushed 2021-11-29)

**Documentation:** https://docs.hifi.finance/protocol/developers/data

### Entity types in the schema

| Type | Purpose |
| --- | --- |
| `Position` | A collateral or debt position — user address + token address, amount, token |
| `Token` | A basic ERC-20 token — address, decimals, name, symbol |
| `Hifi` | Singleton overview — listed bonds, listed collaterals, pools, vaults |
| `Vault` | A user's deposited collaterals and outstanding debts, with creation timestamp |
| `Pool` | AMM pool — hToken and underlying reserves, maturity, derived swaps |
| `Swap` | A single pool trade — from/to, hToken and underlying amounts, swap fee, timestamp |

The Graph generates the query root from these `@entity` types; the repository publishes no
explicit `Query` type, which is normal for a subgraph manifest.

## The other documented data path

Alongside the subgraph, https://docs.hifi.finance/protocol/developers/data documents **Multicall**
— batching constant smart-contract calls directly against the deployed Hifi contracts. That is an
on-chain ABI surface, not an HTTP API, and it is not represented here.

## What is NOT here

- No REST API, no OpenAPI/Swagger document on any Mainframe or Hifi host (see
  `../well-known/mainframe-well-known.yml` for the full probe record).
- No introspection result — the documented endpoint 404s, so the SDL comes from the repository
  rather than from a live server.
