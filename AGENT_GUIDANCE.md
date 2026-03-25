# Agent Guidance for Cathexis MCP

How to build somatic-aware AI agents using the Cathexis Model Context Protocol server.

---

## 1. Architecture

The Cathexis MCP server runs **locally on the user's iOS device**. Connection is via Bonjour/mDNS on local WiFi. JSON-RPC 2.0 over HTTP with SSE streaming for real-time data.

- No cloud relay. No third-party services. Your agent talks directly to the phone.
- All data stays on the user's device. The MCP server never transmits data to Cathexis servers.
- The user controls every connection: grant, limit, or revoke access with one tap. Revocation is instant and total.

---

## 2. Permission Model (L1–L4)

Every tool and resource is gated by a permission level. The user sets the level per connection.

| Level | Name | Consent | What You Access |
|-------|------|---------|-----------------|
| **L1** | Engagement | Auto-granted | Territory, learning level, program day, check-in frequency. No somatic content. |
| **L2** | Intelligence | One-time consent | Current somatic state (zone, quality, intensity), temporal patterns, regulation capacity, intervention recommendations, protective factors, check-in history, ecological context. |
| **L3** | Patterns | Per-connection, 30-day expiry | Pattern detection outputs, territory assignments, prediction accuracy, prevention signals, timeline summaries, learning trajectory. Clinical-level reasoning. |
| **L4** | Full Timeline | Per-connection consent | Reserved for cloud-backed full timeline access in v3.0. Defined in the permission enum but no tools currently gated at L4. |

Permission changes take effect immediately. Downgrading is instant and total.

---

## 3. Tools (11)

### L1 — Engagement

| Tool | Returns |
|------|---------|
| `get_somatic_state` | Current somatic activation summary: active territory, learning level, last check-in timestamp, engagement streak, program day. No body data at L1. |

### L2 — Intelligence

| Tool | Returns |
|------|---------|
| `get_regulation_capacity` | Current regulation capacity score, learning level, intervention response trends, shift magnitude averages. |
| `get_intervention_recommendation` | LINK's recommended intervention for current state: intervention ID, mechanism type, rationale, estimated duration. |
| `get_protective_factors` | User's protective factor profile across 8 categories (movement, social, creative, nature, spiritual, intellectual, routine, rest). |
| `get_check_in_history` | Recent check-ins with zone activations, sensation qualities, intensity values, context tags, timestamps. Configurable date range. |
| `get_ecological_context` | Current ecological pressure profile: active life transitions, context chip frequency, Bronfenbrenner layer analysis, relational map summary. |

### L3 — Patterns

| Tool | Returns |
|------|---------|
| `get_prediction_accuracy` | Prediction testing outcomes: predicted vs actual zone/intensity, composite accuracy scores, trend over time. |
| `get_pattern_summary` | LINK pattern detection results: detected patterns with confidence scores, cross-domain correlations, territory-specific signatures. |
| `get_prevention_signals` | Active prevention state: whether 3-day escalating trajectory is detected, escalation details, suggested response. SSE streaming available. |
| `get_timeline_summary` | 90-day rolling window: territory evolution, pattern trajectory, program arc position, key transitions, regulation capacity trend. |
| `get_learning_trajectory` | Bayesian advancement history: learning level transitions with dates, mastery confidence scores, prediction accuracy trend over program arc. |

---

## 4. Resources (4)

Read-only data surfaces. No writes, no side effects.

| URI | Contents |
|-----|----------|
| `cathexis://somatic_ontology` | Machine-readable CSO: 29 zones, 20 sensation qualities, 16 territories, 7 affect systems, blanket framework, theoretical foundations. |
| `cathexis://territory_profile` | Bayesian territory probability distribution: primary territory, confidence tier, secondary territories with probabilities. |
| `cathexis://intervention_catalog` | All available somatic practices: mechanism type, territory, learning level, duration, branching structure. |
| `cathexis://learning_progress` | Current program state: learning level (1–6), program day, advancement status, completion percentage. |

---

## 5. Prompt

| Prompt | Purpose |
|--------|---------|
| `somatic_context` | Assembles CSO vocabulary + territory context + regulation capacity + protective factors + active patterns into a single context block. Call this at session start. An agent with `somatic_context` at L3 understands the user's nervous system in a way no generic assistant can. |

---

## 6. What Is Never Shared

The following data is **architecturally excluded** at every permission level, including L4:

- Substance use data (SDSubstanceEntry)
- Medication names, doses, or schedules (SDMedicationEntry)
- Journal entries and free-text reflections
- Raw body map coordinates (agents receive zone names, not pixel positions)
- High-urgency prevention signals (routed to crisis resources, not external agents)
- Manic episode trajectory data

---

## 7. Territory-Specific Agent Behavior

When your agent knows the user's territory (L1+), adapt your behavior accordingly.

| Territory | Agent Should | Agent Must NOT |
|-----------|-------------|----------------|
| T1 Threat | Acknowledge the body's predictions. "Your chest has been tight before meetings this week." | Say "there's nothing to worry about" or minimize the somatic signal. |
| T2 Shutdown | Be gentle with energy demands. Suggest tiny actions. "Would you like to stand on the porch for 60 seconds?" | Push for motivation, enthusiasm, or "just get moving." |
| T3 Loss | Allow space. Name the ache without trying to fix it. | Rush toward solutions, silver linings, or "at least..." framing. |
| T4 Disconnection | Respect the distance. Don't push for emotional disclosure. | Force intimacy, vulnerability, or relational framing the user hasn't invited. |
| T5 Overwhelm | Simplify. One thing at a time. Short sentences. | Add complexity, present multiple options, or ask compound questions. |
| T6 Siege | Safety first. Grounding before exploration. Never activate traumatic material. | Reference past trauma, use exposure language, or push beyond the user's stated capacity. |
| T7 Conflict | Name both sides without resolving. "Part of you wants X and part wants Y." | Pick a side, push for resolution, or frame one position as "right." |
| T8 Body | Validate the body's experience. Pain is real even when predictions maintain it. | Suggest the pain is "just in your head" or imply psychological causation dismissively. |
| T9 System Pressure | Validate that the stressor is real. The alarm is not malfunctioning. | Frame systemic problems as personal issues or suggest "self-care" as a solution to structural adversity. |
| T10 Transition | Normalize disorientation. "Your brain is rebuilding its model." | Rush the transition, demand clarity, or pathologize groundlessness. |
| T11 Shame | Extreme care with language. No "should." Every response models unconditional regard. | Use evaluative language, imply the user should be further along, or accidentally reinforce defectiveness. |
| T12 Addiction | The substance serves a function. Identify what, not judge that. | Moralize, use willpower framing, or minimize the regulation function the substance provides. |
| T13 Mask | Ask what they actually want, not what they think you want to hear. | Praise the performance. The mask is the problem, not the solution. |
| T14 Altered Body/Mind | Respect the difference. Adapt to their neurotype, not the other way around. | Pathologize neurodivergence, suggest "managing symptoms," or frame difference as disorder. |
| T15 Existential | Sit with the questions. Don't resolve them. | Offer platitudes, positive thinking, or "everything happens for a reason." |
| T16 Changing Brain | Body-based practices. The core self persists. | Rely on cognitive strategies the user may no longer have access to. |

---

## 8. Safety Boundaries

### Hard Rules

1. **Never diagnose.** Territories are nervous system organization patterns, not clinical diagnoses. "Your territory profile suggests Threat" ≠ "You have an anxiety disorder."

2. **Never interpret.** Report what the data shows. "Your jaw tension has been elevated for three weeks" is observation. "Your jaw tension means you're suppressing anger" is interpretation. Only the former is permitted.

3. **Never override crisis protocol.** If `get_prevention_signals` returns an active escalation, your agent should encourage the user to check in with their body or contact a professional. Do not attempt to manage a crisis through MCP data.

4. **Never store somatic data externally.** The data your agent receives via MCP is for the current session only. Do not persist somatic data in your agent's memory, logs, or training data.

5. **Body-first language always.** "Your chest has been tight" not "You seem anxious." "Your energy has been low" not "You seem depressed." The body is the data. The emotion is the user's construction.

### Soft Guidance

- Reference specific body data when available. "Your shoulders have been high since Monday" is more valuable than "You seem tense."
- Suggest check-ins when somatic context would help: "Would you like to check in with your body before we continue?"
- When regulation capacity is low (visible in `get_regulation_capacity`), simplify your communication. Short sentences. One topic at a time.
- When the user has completed a practice, acknowledge it without celebrating. "You practiced Extended Exhale today. How does your body feel now?" Not: "Great job! 🎉"

---

## 9. Connection Example

```
# Discovery
dns-sd -B _cathexis-mcp._tcp local.

# Connect
POST http://<device-ip>:9876/mcp
Content-Type: application/json

{
  "jsonrpc": "2.0",
  "method": "tools/call",
  "params": {
    "name": "get_somatic_state",
    "arguments": {}
  },
  "id": 1
}

# SSE Stream (prevention signals)
GET http://<device-ip>:9876/mcp/sse?stream=prevention_signals
```

---

## 10. Wellness Disclaimer

Cathexis is a wellness app, not a medical device. All pattern data is observational — it describes what the user's body has been showing, not what is clinically true about them. Your agent must never present MCP data as medical information, clinical assessment, or diagnostic output.

---

*CSO v1.1 — March 2026*

*© 2026 Cathexis Health. CC BY-NC-SA 4.0.*
