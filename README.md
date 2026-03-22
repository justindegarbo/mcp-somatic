# mcp-somatic

**Somatic Intelligence Vocabulary for AI Agents**

A structured vocabulary and agent guidance specification for building somatic-aware AI systems using the Model Context Protocol (MCP).

## What This Is

This repository defines the vocabulary, territory profiles, and integration patterns that enable AI agents to understand, interpret, and respond to human somatic (body-based) data. It is the developer-facing companion to the [Cathexis Somatic Ontology (CSO)](https://doi.org/10.5281/zenodo.19157529), the first published formal ontology for computational somatic therapeutics.

## Contents

| File | Purpose |
|------|---------|
| `SOMATIC_ONTOLOGY.md` | Developer reference for CSO v1.1: 29 body zones, 20 sensation qualities, URI scheme, data structures, and integration patterns |
| `TERRITORY_PROFILES.md` | All 16 territories of human experience in machine-readable format: predictive patterns, affect configurations, somatic signatures, network configurations |
| `AGENT_GUIDANCE.md` | How to build somatic-aware agents: connection patterns, data interpretation, clinical safety constraints, response guidelines |
| `README.md` | This file |

## Theoretical Foundation

The vocabulary is grounded in seven major research programs:

1. **Constructed emotion theory** (Barrett) — emotions are constructed from interoceptive signals, not triggered by events
2. **Predictive processing / active inference** (Friston) — the brain generates probabilistic models and updates them through prediction error
3. **Primary affect systems** (Panksepp) — seven genetically encoded motivational systems (SEEKING, FEAR, RAGE, PANIC/GRIEF, CARE, PLAY, LUST)
4. **Somatic markers** (Damasio) — body states serve as decision-making signals
5. **Neuropsychoanalysis** (Solms) — consciousness arises from subcortical affect systems
6. **The entangled brain** (Pessoa) — brain function emerges from dynamic, distributed network coalitions, not single regions
7. **Memory systems** (Kandel, Nader, Schiller, Ecker) — reconsolidation as the mechanism for therapeutic change

## Namespace

All CSO terms resolve under: `https://cathexis.health/ontology/cso/v1.1/`

Machine-readable formats (OWL, JSON-LD, Turtle) are published alongside the White Paper on Zenodo.

## Connection to Cathexis

The Cathexis iOS app exposes an MCP server that AI agents can connect to over the local network. When connected, agents can:

- Read the user's somatic check-in history (with explicit user permission)
- Access pattern detection results from the clinical intelligence system
- Retrieve territory profiles and therapeutic trajectory data
- Stream real-time somatic state changes via SSE

This repository provides the vocabulary an agent needs to interpret that data meaningfully.

## Clinical Safety

**This vocabulary describes somatic experience. It does not qualify an agent to provide therapy.**

Any agent consuming somatic data must:

- Never diagnose, label, or pathologize the user's experience
- Never override or contradict the platform's clinical intelligence system
- Respect the user's permission level (L1/L2/L3) and never request elevation
- Treat all somatic data as sensitive health information
- Defer to licensed clinicians for all clinical decisions

See `AGENT_GUIDANCE.md` for complete safety constraints.

## License

This repository is private. All content is proprietary to Cathexis Health.

**Academic publications:** The Cathexis Somatic Ontology White Paper and HEF Clinical Manual are published under CC BY-NC-SA 4.0 on Zenodo.

**Future open-source timeline:** Selected vocabulary components (zone taxonomy, sensation qualities, basic territory definitions) are planned for open-source release under CC BY-NC-SA 4.0 after the Cathexis platform reaches version 3.0 and the first validation study is published. Detection algorithms, clinical decision thresholds, intervention routing logic, and safety gate parameters will remain proprietary.

## Citation

```
DeGarbo, J. (2026). A somatic ontology for computational therapeutics:
Formalizing body-based experience for digital mental health (Version 2.0).
Cathexis Health. https://doi.org/10.5281/zenodo.19157529
```

## Contact

support@cathexis.health

CATHEXIS is a trademark of Justin DeGarbo.
