# Critical Mass

**A digital buying cooperative that lets small and mid-sized manufacturers pool purchasing power across borders.**

Finalist, UNCTAD Supply Chain Innovation Challenge 2026 — 2nd UN Global Supply Chain Forum, Riyadh.

---

## Summary

Small manufacturers rarely order enough to fill a container or meet a supplier's minimum order quantity, so they pay part-load premiums and never learn what their materials cost at scale. Thousands of kilometres away, another firm faces the identical problem the same week. Neither knows the other exists.

Critical Mass is a matching layer that pools fragmented demand into consolidated, competitively bid lots. The platform acts as agent, never principal: each buyer contracts directly with the winning supplier and carries no other buyer's credit risk.

The individual components are established — multi-criteria matching, sealed-bid auctions, Shapley-based gain-sharing, federated learning. The contribution is their assembly into one mechanism for firms too small and too undigitised for any existing platform to reach, plus an intake layer that needs nothing beyond a phone.

## Why existing solutions miss these firms

| Sector | What it does | Why the gap remains |
|---|---|---|
| Freight forwarders | Combine part-loads into containers | Only after the purchasing decision is locked |
| Group purchasing organisations | Pool buying power | Closed membership, single sector and jurisdiction |
| Enterprise procurement platforms | Price discovery | Serve firms already running a procurement function and ERP |
| B2B marketplaces | Buyer-to-supplier discovery | Directories with no incentive to aggregate buyers; every transaction stays bilateral, so no gain-sharing exists |

B2B exchanges were tried and failed in the early 2000s, Covisint the best known. Three reasons, all now addressable: matching heterogeneous small orders was computationally impractical, gain-sharing had no accepted mechanism, and participation demanded systems integration that excluded the firms most in need.

## Mechanism

**Demand intake and lot formation.** A buyer posts a structured demand: product code, quantity, delivery window, origin, destination, order date. Lot formation is posed as a constrained matching problem over product, quantity, route and delivery window, aggregating compatible live requests into lots sized to clear a full container or a supplier's minimum order.

**Sealed-bid supplier scoring.** Each lot opens as a request for quotation to verified suppliers, who submit sealed bids scored on price, reliability, certification, proximity and emissions footprint, weighted to keep smaller suppliers competitive. Awards can split across suppliers, trading efficiency for protection against single-point failure.

**No deadline risk.** The agent aggregates only until the lot reaches a viable threshold or the date arrives. If the date passes without one, the demand releases automatically and the buyer may auction alone at no cost.

**Gain-sharing via Shapley allocation.** Firms recognise pooling's savings but decline to collaborate over how to divide them. Cost and emissions savings are apportioned by marginal contribution under a Shapley-value rule, so a buyer whose volume tips a lot over a full-container threshold is credited accordingly rather than equally with a marginal contributor. The rule is published and fixed in advance, because past ventures collapsed over exactly this question.

**Federated demand forecasting (Phase 2).** Matching only aggregates demand that already exists; anticipating it is the larger prize. A single firm's order history is too thin to forecast from, but the combined histories of thousands are not. A shared demand and lead-time model trains across every participant's data without that data leaving their systems. Activated once cross-firm participation is dense enough to beat any single firm's history, since one anchor's order book is not enough.

**Trust architecture.** Participants never see one another's raw demand, pricing history or inventory; only the agent does, after both sides opt in. Suppliers see lot quantity and delivery window, never who is behind them. Price is set by competitive bidding rather than buyer agreement, and lot formation is capped below concentration thresholds.

**Built for undigitised participants.** Most target firms run no ERP. Intake accepts a mobile form, a structured message in software they already use, or a photographed purchase order read by document understanding. No API integration and no investment beyond a phone.

## Pilot baseline

Iron and steel scrap into Pakistan's foundry industry, from customs records for April 2025 to March 2026.

| Metric | Current, fragmented | Consolidated (modelled) |
|---|---|---|
| Import value | $1.25 billion | Unchanged; savings are per unit |
| Importing firms | 752 | Same firms, pooled |
| Overseas suppliers | 2,327 | Same pool, competing directly |
| Total shipments | 57,384 | ~19,000 at 3-to-1 pooling |
| Shipments per importer per year | ~76 | ~25 |
| Average shipment size | Below benchmark | ~150 t pooled lot |
| Customs filings | 57,384 | ~38,000 or fewer |
| Freight cost impact | Baseline | 15–30% (modelled) |

> Figures are close approximations drawn from customs records, intended to establish the concept's plausibility rather than to forecast outcomes. Shipment, value, importer and supplier counts are customs-record figures; the pooling ratio and freight range are modelled, to be confirmed in a pilot baseline audit.

**Pilot targets, eighteen months:** fifty SMEs onboarded, 150 pooled purchase events, 10–15% procurement saving, measurable freight cost reduction, and a validated CO₂ reduction figure.

## Open problems

The parts of this that are research rather than engineering, and what I would want to work on:

1. **Fixing the characteristic function.** Shapley gives every member a defensible share, but only once *v(S)* is fixed. Almost all the argument with participating firms was about that choice, not about the mathematics. What makes a characteristic function acceptable to participants who can audit their own share?
2. **Allocation at scale.** Exact Shapley computation is exponential in members. Beyond small lots it must be approximated, at which point approximation error becomes payment error rather than explanation error.
3. **Dispute-resistance.** When an allocation is estimated rather than computed, what recourse does a member have who believes their share is wrong? An axiom can be pointed at; an estimator cannot.
4. **Manipulation.** Can a member shape its order stream to inflate its own marginal contribution, and what does that cost the pool?
5. **When does pooling actually help?** Whether pooled cross-firm order histories beat single-firm demand forecasts, under distributions that differ sharply between participants, is an empirical question. It is the subject of my final-year project.

## Role and status

**Technical Lead — AI, data analytics and matching architecture:** Muhammad Imad Khan, BS Data Science, Ghulam Ishaq Khan Institute.
**Project Lead — supply chain strategy and industry implementation:** Usman Ahmed, Group Head of Supply Chain, Qadri Group of Industries, Pakistan.

Qadri Group, a Lahore foundry and heavy-machining operation over 130 years old, is the pilot's anchor participant, supplying its order history as the first demand stream. Governance sits with an independent non-commercial body; the anchor holds no governance seat.

Status: submitted to the UNCTAD Supply Chain Innovation Challenge 2026 and selected as a finalist. Pilot design stage.

## Selected references

Cruijssen et al., "Horizontal Cooperation in Logistics," *Transportation Research E*, 2007 · Vanovermeire et al., "Horizontal Logistics Collaboration," *International Journal of Logistics Research*, 2014 · McMahan et al., "Federated Learning from Decentralized Data," AISTATS, 2017 · Montreuil, "Towards a Physical Internet," *Logistics Research*, 2011 · UNCTAD, *Review of Maritime Transport*, 2025 · OECD, *Trade Facilitation Indicators*, 2025

---

**Contact:** Muhammad Imad Khan · imadkhan1860@gmail.com · [CV](Imad_Khan_CV.pdf)
