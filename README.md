# mcp-somatic

**The somatic vocabulary for AI agents.**

This repository defines the machine-readable vocabulary, territory profiles, and agent guidance for building somatic-aware AI systems using the Cathexis Model Context Protocol (MCP) server.

## What This Is

The Cathexis Somatic Ontology (CSO) is a formal vocabulary for representing body-based therapeutic experience in computational systems. It defines 29 anatomical zones, 20 sensation qualities, 7 primary affect systems, 16 territories of human experience, and a Markov blanket framework — all grounded in seven research programs in affective neuroscience and predictive processing.

The MCP server runs locally on the user's iOS device. Your AI agent connects via Bonjour/mDNS on local WiFi and queries structured somatic data with the user's explicit consent.

## Repository Contents

| File | Contents |
|------|----------|
| `SOMATIC_ONTOLOGY.md` | Complete CSO vocabulary: 29 zones, 20 sensation qualities, blanket framework, affect systems, brain regions, ecological layers |
| `TERRITORY_PROFILES.md` | All 16 territory profiles in machine-readable format with affect signatures, blanket patterns, and somatic markers |
| `AGENT_GUIDANCE.md` | How to build somatic-aware agents: permission model, tool reference, territory-specific behavior, safety boundaries |
| `README.md` | This file |

## Quick Start

1. Install Cathexis on an iOS device (App Store)
2. Open Profile → AI Integration → Enable MCP Server
3. Your MCP client discovers the server via Bonjour on local WiFi
4. The user approves the connection and sets permission level (L1–L4)
5. Query somatic data using the 17 published tools

Claude Desktop connects natively. Any MCP-compatible client works.

## Namespace

**CSO Namespace URI:** `https://cathexis.health/ontology/cso/v1.1/`

**BioPortal:** [CXSO on BioPortal](https://bioportal.bioontology.org/ontologies/CXSO) — the ontology's canonical name is **CSO**; it is registered as CXSO on BioPortal only because the acronym CSO was already taken there.

**Zenodo (concept DOI, always resolves to latest):** [10.5281/zenodo.18859896](https://doi.org/10.5281/zenodo.18859896)

Machine-readable formats: OWL, Turtle, JSON-LD — all available at the Zenodo DOI, licensed CC BY 4.0.

## Published Materials

| Document | Location |
|----------|----------|
| Cathexis Somatic Ontology (CSO) — paper + machine-readable artifacts | [Zenodo concept DOI: 10.5281/zenodo.18859896](https://doi.org/10.5281/zenodo.18859896) |
| HEF Clinical Manual v3.0 | [Zenodo concept DOI: 10.5281/zenodo.19157696](https://doi.org/10.5281/zenodo.19157696) |
| Human Experience System (HES) v1.0 | [Zenodo concept DOI: 10.5281/zenodo.20438782](https://doi.org/10.5281/zenodo.20438782) |
| CSO on BioPortal | [CXSO](https://bioportal.bioontology.org/ontologies/CXSO) |
| HEF Community Guide | [cathexis.health/science](https://cathexis.health/science) |
| Provider Integration Guide | [cathexis.health/providers](https://cathexis.health/providers) |

*All Zenodo DOIs above are concept DOIs — they always resolve to the most recent version.*

## License

**Vocabulary layer (this repository):** CC BY 4.0. Use the zones, qualities, territories, and affect-system vocabulary in your agents, products, and research — including commercially. Attribution required; no other restriction. The vocabulary is published openly so that it can be adopted, extended, and built upon without a licensing barrier.

**Clinical implementation (Cathexis app):** Proprietary. The intervention graphs, pattern-detection logic, Bayesian inference pipeline, and therapeutic content are not included in this repository and are not licensed here.

## Version

- **CSO:** v1.1 (March 2026)
- **MCP Server:** 17 tools, 12 resources, 4 prompts
- **App:** Cathexis 2.3.5+ on the App Store

## Links

- **Website:** [cathexis.health](https://cathexis.health)
- **For Developers:** [cathexis.health/developers](https://cathexis.health/developers)
- **App Store:** [Download Cathexis](https://cathexis.health/download)
- **Support:** support@cathexis.health

---

*Sensation before emotion. Curiosity over judgment. Adaptation over pathology.*

*© 2025 Justin DeGarbo / Cathexis Health. Vocabulary licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).*
