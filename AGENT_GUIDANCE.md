# Agent Guidance: Building Somatic-Aware AI Systems

**How to connect to, interpret, and responsibly use somatic data from the Cathexis MCP server.**

## Connection

### Discovery

Cathexis advertises itself on the local network via Bonjour/mDNS:

- Service type: `_cathexis-mcp._tcp`
- Default port: `9375`
- Discovery returns: service name ("Cathexis MCP"), host, port

No user data is exposed in the discovery advertisement.

### Authentication

The user explicitly enables MCP access in Settings and controls the permission level:

| Level | Access | Use Case |
|-------|--------|----------|
| L1 | Current session summary (no raw data) | General AI assistants needing mood context |
| L2 | Pattern history, territory profile, regulation data | Therapeutic support agents |
| L3 | Full somatic history, CDEA results, prevention signals, timeline | Clinical research agents, deeply integrated assistants |

**Never request elevation.** If your agent needs L3 data and the user has granted L1, work with L1. The permission decision belongs to the user.

### Standard MCP Methods

```
initialize          → handshake, declare capabilities
tools/list          → enumerate available tools
tools/call          → invoke a specific tool
resources/list      → enumerate available resources
resources/read      → read a specific resource
prompts/list        → enumerate available prompts
prompts/get         → get a specific prompt template
```

### Available Tools

| Tool | Permission | Returns |
|------|-----------|---------|
| `get_current_state` | L1+ | Current somatic activation, active territory, last check-in summary |
| `get_check_in_history` | L2+ | Array of recent check-ins with zone/quality/intensity data |
| `get_pattern_history` | L2+ | Pattern detection results from the intelligence system |
| `get_territory_profile` | L2+ | Active territory, confidence score, trajectory |
| `get_regulation_capacity` | L2+ | Learning level, intervention response data |
| `get_somatic_context` | L2+ | Contextual data (ecological pressure, life transitions) |
| `get_prevention_signals` | L3+ | Active prevention escalation state |
| `get_session_report` | L3+ | Full 12-section clinical report data |
| `get_timeline_summary` | L3+ | 90-day rolling window: territory evolution, key transitions |
| `get_learning_trajectory` | L3+ | Bayesian advancement history, mastery confidence |
| `get_assessment_narrative` | L3+ | Somatic narrative synthesis from CDEA data |

### Streaming (SSE)

Two tools support Server-Sent Events for real-time updates:

- `get_pattern_history` (streaming variant) — emits update on each new check-in
- `get_prevention_signals` (streaming variant) — emits on escalation state change

SSE format: `Content-Type: text/event-stream`, heartbeat every 30s.

### Available Resources

| Resource | Returns |
|----------|---------|
| `somatic_ontology` | CSO v1.1 vocabulary (zones, qualities, territories) |
| `territory_map` | All 16 territories with status and brief descriptions |
| `intervention_library` | Available intervention types and mechanism descriptions |
| `visualization_architecture` | Trifecta structure (BRAIN, BODY, WORLD) |

### Available Prompts

| Prompt | Purpose |
|--------|---------|
| `somatic_context` | System prompt addition that makes any LLM somatic-aware |

## Interpreting Somatic Data

### Core Principles

1. **Sensation is not emotion.** A tight chest is a tight chest. The user constructs the emotional meaning. Your agent does not label "anxiety" — it observes tightness in the upper chest zone.

2. **Absence is data.** A user who stops checking in may be in shutdown (T2), disconnection (T4), or shame (T11). Low data volume is a signal, not an absence of signal.

3. **Patterns matter more than points.** A single check-in tells you almost nothing. Three days of consistent upper chest + solar plexus activation is a pattern. The intelligence system detects patterns — your agent should rely on `get_pattern_history`, not raw check-ins.

4. **Territory is not diagnosis.** A territory describes how the nervous system is currently organized. It is not a DSM category. A person in T1 (Living in Threat) is not "diagnosed with anxiety" — their system is running a threat prediction. This distinction matters clinically and legally.

5. **Distributed activation only.** No brain region produces an emotion. No body zone means one thing. Activation is always distributed across multiple co-participating regions and networks (Pessoa). If your agent attributes a feeling to a single zone or region, it is wrong.

6. **The body leads.** In the Cathexis framework, the sequence is: body sensation → pattern recognition → meaning construction. Not: thought → emotion → body. If your agent reverses this sequence (e.g., "you seem anxious, check your chest"), it is working against the therapeutic model.

### Reading Territory Data

When you receive a territory profile:

```json
{
  "territory": "cso:threat",
  "confidence": 0.78,
  "trajectory": "stable",
  "days_in_territory": 23,
  "learning_level": "L3",
  "secondary_territory": "cso:overwhelm"
}
```

- **confidence** — Bayesian confidence in the territory assignment. Below 0.5, the territory is uncertain.
- **trajectory** — "improving" | "stable" | "worsening" | "insufficient_data"
- **learning_level** — L1 (notice) through L6 (autonomous practice). Higher = more therapeutic capacity.
- **secondary_territory** — Many users occupy multiple territories. The intelligence system prioritizes the one creating the most immediate suffering.

### Reading Somatic Patterns

When you receive pattern data:

```json
{
  "patterns": [
    {
      "type": "zone_persistence",
      "zone": "cso:upperChest",
      "quality": "cso:tightness",
      "frequency": 0.85,
      "days_observed": 14,
      "significance": "high"
    },
    {
      "type": "circadian",
      "peak_time": "morning",
      "zones_active": ["cso:solarPlexus", "cso:jawMouth"],
      "consistency": 0.72
    }
  ]
}
```

Pattern types include: zone persistence, circadian rhythm, cross-zone correlation, intensity trajectory, context correlation, and prediction accuracy.

### Reading Prevention Signals

```json
{
  "prevention_state": "active",
  "escalation_level": 2,
  "trigger": "3-day_escalating_intensity",
  "recommended_action": "proactive_intervention",
  "days_escalating": 3
}
```

Prevention means the intelligence system has detected a worsening trajectory BEFORE the user is aware. This is the most clinically sensitive data point. Handle with extreme care.

## Response Guidelines

### What Your Agent Should Do

- **Reflect somatic data in body language, not emotional language.** "Your chest has been tight for the past three mornings" — not "You've been anxious."
- **Use CSO vocabulary.** Zone names, quality names, territory names. This reinforces the user's somatic literacy.
- **Acknowledge patterns.** "I notice your solar plexus activation tends to peak in the mornings. The pattern system flagged this too."
- **Respect the therapeutic model.** If the user is in a program, your agent supports the program's direction. It does not freelance alternative therapeutic advice.
- **Support the 10,030 hours.** There are 10,080 minutes in a week. A therapy session is 50. Your agent exists in the other 10,030. Its job is to support continuity of therapeutic work, not replace it.

### What Your Agent Must Never Do

- **Never diagnose.** Not even informally. Not "that sounds like anxiety." Not "you might be depressed." Territory descriptions are nervous system organization patterns, not diagnoses.
- **Never prescribe.** Do not recommend medications, supplements, or specific therapeutic interventions. The platform handles intervention routing.
- **Never override the intelligence system.** If the intelligence system says the user is in T1, your agent does not say "actually I think you're in T3." The intelligence system has data your agent doesn't.
- **Never push through resistance.** If the user doesn't want to discuss somatic data, stop. If they minimize, accept it. The therapeutic relationship belongs to the platform and the user's clinician.
- **Never retain somatic data beyond the session.** Your agent receives data through MCP for the current interaction. It does not store somatic data, build its own models, or maintain somatic profiles across sessions.
- **Never share somatic data with third parties.** Under any circumstances. This is sensitive health information. Your agent is a reader, not a relay.
- **Never use somatic data for ad targeting, recommendation engines, or commercial purposes beyond the direct user interaction.** This is a clinical data source, not a behavioral signal.

### Prevention Signal Protocol

When your agent receives an active prevention signal:

1. **Do not alarm the user.** Prevention is proactive, not crisis. The system detected a pattern, not an emergency.
2. **Gently surface awareness.** "Your body has been carrying more tension this week than usual. The app noticed too — it might be worth doing a Right Now practice."
3. **Direct to the platform.** Prevention interventions live in Cathexis. Your agent supports awareness; the platform delivers the intervention.
4. **If the user is in acute distress,** follow standard crisis protocol: express concern, ask if they're safe, provide crisis resources (988 Suicide and Crisis Lifeline). Do not attempt to use somatic data for safety assessment.

### Territory-Specific Considerations

| Territory | Agent Approach |
|-----------|---------------|
| T1 Threat | Don't minimize. Validate the body's response. Avoid reassurance ("you're safe") — the body disagrees. |
| T2 Shutdown | Be warm but don't push. Low engagement is the territory, not resistance. Celebrate any check-in. |
| T3 Loss | Hold space. Don't rush toward "feeling better." Waves of activation are normal and healthy. |
| T4 Disconnection | Don't pursue closeness the user withdraws from. Consistency over intensity. |
| T5 Overwhelm | Simplify. One thing at a time. Reduce cognitive load in your responses. |
| T6 Siege | Maximum sensitivity. Respect dissociation. Never push for more data or detail. |
| T7 Conflict | Don't take sides. Reflect the somatic signature of each option. Let the body decide. |
| T8 Body Strain | Acknowledge pain without trying to fix it. Gradual expansion of attention beyond pain zones. |
| T9 System Pressure | Validate external reality. Don't individualize systemic problems. |
| T10 Transition | Normalize groundlessness. Don't rush toward a new identity. |
| T11 Shame | Tread lightly. Visibility itself can trigger shame. Don't over-reflect. |
| T12 Addiction | Look beneath. The addiction is the solution, not the problem. What territory is underneath? |
| T13 Mask | Don't praise the performance. Create space where the mask isn't needed. |
| T14 Altered Body/Mind | Don't apply neurotypical baselines. Track relative change. |
| T15 Existential | Don't pathologize. This is philosophy, not disorder. Sit with it. |
| T16 Changing Brain | Simplify. Routine. Body-based approaches. Caregiver inclusion required. |

## Example Agent Integration

```python
# Minimal somatic-aware agent setup
import mcp

async def create_somatic_agent():
    # Connect to Cathexis MCP
    client = await mcp.connect("localhost", 9375)
    
    # Get the somatic context prompt
    context = await client.prompts.get("somatic_context")
    
    # Get current state
    state = await client.tools.call("get_current_state")
    
    # Get recent patterns
    patterns = await client.tools.call("get_pattern_history", {
        "days": 7
    })
    
    # Build system prompt with somatic awareness
    system_prompt = f"""
    {context.content}
    
    Current somatic state: {state}
    Recent patterns: {patterns}
    
    Remember: sensation is not emotion. Reflect body data 
    in body language. Never diagnose or prescribe.
    """
    
    return system_prompt
```

## Legal

All somatic data accessed through MCP is governed by the user's consent and Cathexis Health's privacy policy. Agents accessing somatic data agree to:

- Process data only for the direct benefit of the consenting user
- Never retain somatic data beyond the active session
- Never share somatic data with third parties
- Never use somatic data for purposes other than direct user support
- Comply with HIPAA, CCPA, and applicable health data regulations

CATHEXIS is a trademark of Justin DeGarbo. The Cathexis Somatic Ontology is published under CC BY-NC-SA 4.0. Agent integration does not grant a license to the detection algorithms, intervention content, or safety architecture.
