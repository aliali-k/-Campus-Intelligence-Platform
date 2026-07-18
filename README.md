# Campus Intelligence Platform

> Pulls placement, admission, and startup data together so a college decision is based on numbers, not word of mouth — built to scale across colleges, with IIT Bombay as the first fully-built reference campus.

---

## Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Data Pipeline](#data-pipeline)
- [Startup Directory](#startup-directory)
- [Why IIT Bombay First](#why-iit-bombay-first)
- [My Role](#my-role)
- [Challenges & What I Learned](#challenges--what-i-learned)
- [Roadmap](#roadmap)
- [Status](#status)

---

## Overview

Most information students use to pick a college and branch is anecdotal — forum posts, seniors' word of mouth, outdated PDFs. Campus Intelligence Platform replaces that with a structured, source-traceable dataset: real placement numbers, real admission rank trends, and a real directory of alumni-founded startups, all pulled from official records and organized so every number can be traced back to where it came from.

The platform is designed to scale across colleges. **IIT Bombay is the first fully-built reference campus** — the full pipeline (data ingestion → cleaning → views → directory) was built and validated end-to-end against IIT Bombay's official data before being generalized to onboard additional colleges.

## Key Features

- **Rank-trend views by branch** — deeply nested, raw JoSAA admission data flattened into clean, queryable tables, with views filterable by branch, category, and gender.
- **Data-reliability filtering** — any trend line backed by less than 2 years of historical data is automatically dropped from the view rather than shown and potentially mismisleading a student.
- **Source-traceable placement data** — placement numbers for ~29 branches pulled directly from IIT Bombay's official placement report, with page-reference notes kept alongside the data so every figure can be verified against the source document.
- **20-sector startup directory** — founders mapped to their branch and company across sectors including fintech, healthtech, and deep-tech, structured as a real searchable dataset rather than a static list.
- **Built to generalize** — the ingestion → cleaning → view pipeline built for IIT Bombay is designed to extend to additional colleges without a rebuild.

## Tech Stack

**Frontend**
`React` · `TypeScript` · `TanStack Start`

**Data Visualization**
`Recharts` (rank-trend charts) · `React Spring` (animation) · `Leaflet` (campus/location mapping) · `cobe` · `@fontsource` (custom typography)

**Styling**
`Tailwind CSS` · `Radix UI`

## Data Pipeline

Raw JoSAA admission data arrives deeply nested and inconsistent. The pipeline:

1. **Flattens** the nested structure into a clean, tabular form.
2. **Builds views** on top of it — rank trends segmented by branch, category, and gender.
3. **Filters for reliability** — any branch/category combination with fewer than 2 years of historical data is excluded from trend views, since a 1-year data point can't support a meaningful trend line without misleading the reader.
4. **Cross-references placement data** — official placement report figures are attached with page-reference notes so every number is independently verifiable, not just asserted.

## Startup Directory

A 20-sector directory (fintech, healthtech, deep-tech, and more) mapping founders to their branch and company, structured as an actual searchable dataset — not a static "notable alumni" page — so it can be filtered and queried the same way the placement and admission data can.

## Why IIT Bombay First

Building the full pipeline against one college's real, messy, official data first — rather than designing an abstract schema and hoping it generalizes — meant every part of the pipeline (flattening, view generation, reliability filtering, source-linking) was validated against real-world data quirks before being generalized. IIT Bombay was chosen as that reference campus; the same pipeline is being extended to additional colleges next.

## My Role

Founder & Product Lead. I designed the data-reliability rules (the 2-year minimum for trend lines), the source-traceability approach for placement figures, and the startup-directory schema. Frontend visualization components were built with AI-assisted tooling for implementation speed, with the underlying data architecture and reliability decisions being mine.

## Challenges & What I Learned

- Official data isn't automatically usable data — flattening deeply nested placement/admission records into something queryable was a bigger task than the modeling itself.
- A chart with too little underlying data is worse than no chart — the 2-year minimum filter exists because a misleading trend line is worse than an honest "not enough data yet."
- Designing for one real campus first, rather than an abstract multi-college schema from day one, produced a more robust pipeline once generalization actually started.

## Roadmap

- Onboard additional reference campuses beyond IIT Bombay
- Add year-over-year placement trend comparison across colleges
- Expand the startup directory with funding-stage data

## Status

Actively developed. This repository is a working build, not a finished/polished open-source release — expect ongoing changes.

---
*Built by Nusrat Ali — [LinkedIn](https://www.linkedin.com/in/nusrat-ali-47073b329)*
