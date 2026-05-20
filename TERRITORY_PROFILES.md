# Territory Profiles

Machine-readable profiles for all 16 territories of the Human Experience Framework.

Each profile describes how a nervous system is organized — not a diagnosis. Most people occupy multiple territories simultaneously.

---

## Schema

```json
{
  "territory": "string — Territory code",
  "number": "int — T1–T16",
  "name": "string — Display name",
  "core_prediction": "string — The brain's high-confidence prediction driving the pattern",
  "affect_signature": {
    "primary": ["string — Panksepp systems elevated or suppressed"],
    "pattern": "string — How affect systems interact"
  },
  "blanket_pattern": {
    "type": "string — porosity | rigidity | damage | boundary | mismatch | limit",
    "description": "string — Markov blanket state"
  },
  "somatic_markers": ["string — Common body zone activations"],
  "sensation_qualities": ["string — Common sensation qualities"],
  "clinical_risk": "low | moderate | high | critical",
  "status": "shipping | planned | deferred"
}
```

---

## T1: Living in Threat

```json
{
  "territory": "threat",
  "number": 1,
  "name": "Living in Threat",
  "core_prediction": "Danger is coming. Safety is temporary.",
  "affect_signature": {
    "primary": ["FEAR↑", "SEEKING↓", "PLAY↓"],
    "pattern": "Threat detection system dominates. Exploration and spontaneity suppressed."
  },
  "blanket_pattern": {
    "type": "porosity",
    "description": "Blanket too thin — external signals flood internal state."
  },
  "somatic_markers": ["upperChest", "jaw", "shoulders", "stomach", "neckFront"],
  "sensation_qualities": ["tightness", "pressure", "buzzing", "heat", "pulsing"],
  "clinical_risk": "moderate",
  "status": "shipping"
}
```

## T2: Living in Shutdown

```json
{
  "territory": "shutdown",
  "number": 2,
  "name": "Living in Shutdown",
  "core_prediction": "Nothing I do will matter. Effort and outcome are disconnected.",
  "affect_signature": {
    "primary": ["SEEKING↓↓", "PLAY↓"],
    "pattern": "Motivation system suppressed. The brain conserves energy because it predicts effort won't produce reward."
  },
  "blanket_pattern": {
    "type": "rigidity",
    "description": "Blanket too thick — external signals dampened, internal state flat."
  },
  "somatic_markers": ["wholeBody", "upperChest", "lowerBack", "eyes"],
  "sensation_qualities": ["heaviness", "numbness", "ache", "cold", "stillness"],
  "clinical_risk": "moderate",
  "status": "shipping"
}
```

## T3: Living in Loss

```json
{
  "territory": "loss",
  "number": 3,
  "name": "Living in Loss",
  "core_prediction": "What was central to my world is gone. The model includes what is no longer there.",
  "affect_signature": {
    "primary": ["PANIC/GRIEF↑", "SEEKING variable"],
    "pattern": "Separation distress active. SEEKING oscillates between searching for what's lost and collapsing."
  },
  "blanket_pattern": {
    "type": "damage",
    "description": "Blanket torn — a structural piece of the model is missing."
  },
  "somatic_markers": ["upperChest", "throat", "stomach", "eyes"],
  "sensation_qualities": ["ache", "hollow", "heaviness", "tightness", "pressure"],
  "clinical_risk": "moderate",
  "status": "shipping"
}
```

## T4: Living in Disconnection

```json
{
  "territory": "disconnection",
  "number": 4,
  "name": "Living in Disconnection",
  "core_prediction": "Depending on others is not safe. The need for connection is dangerous.",
  "affect_signature": {
    "primary": ["PANIC/GRIEF suppressed", "CARE↓"],
    "pattern": "Attachment signal dampened. The need is present but the signal has been turned down."
  },
  "blanket_pattern": {
    "type": "rigidity",
    "description": "Blanket too thick — self-sufficiency as defense against relational pain."
  },
  "somatic_markers": ["upperChest", "shoulders", "hands", "stomach"],
  "sensation_qualities": ["numbness", "cold", "hollow", "contraction"],
  "clinical_risk": "moderate",
  "status": "planned"
}
```

## T5: Living in Overwhelm

```json
{
  "territory": "overwhelm",
  "number": 5,
  "name": "Living in Overwhelm",
  "core_prediction": "Too much is happening. Regulatory capacity is exceeded.",
  "affect_signature": {
    "primary": ["All systems competing"],
    "pattern": "Multiple emotional systems firing simultaneously. Undifferentiated activation storm."
  },
  "blanket_pattern": {
    "type": "porosity",
    "description": "Blanket too thin — everything gets through, nothing is filtered."
  },
  "somatic_markers": ["upperChest", "headScalp", "stomach", "jaw", "wholeBody"],
  "sensation_qualities": ["buzzing", "heat", "pressure", "trembling", "nausea"],
  "clinical_risk": "moderate",
  "status": "shipping"
}
```

## T6: Living Under Siege

```json
{
  "territory": "siege",
  "number": 6,
  "name": "Living Under Siege",
  "core_prediction": "The past is still happening. The danger is not over.",
  "affect_signature": {
    "primary": ["FEAR locked", "All potentially dysregulated"],
    "pattern": "Traumatic memory fires in present tense. Contextual encoding disrupted."
  },
  "blanket_pattern": {
    "type": "damage",
    "description": "Blanket torn — past intrudes through the boundary."
  },
  "somatic_markers": ["upperChest", "stomach", "throat", "wholeBody", "hands"],
  "sensation_qualities": ["tightness", "numbness", "trembling", "cold", "floating", "pain"],
  "clinical_risk": "critical",
  "status": "shipping"
}
```

## T7: Living in Conflict

```json
{
  "territory": "conflict",
  "number": 7,
  "name": "Living in Conflict",
  "core_prediction": "Two things are true simultaneously and they contradict each other.",
  "affect_signature": {
    "primary": ["SEEKING vs FEAR", "RAGE vs FEAR", "PANIC/GRIEF vs FEAR"],
    "pattern": "Competing high-confidence predictions. Neither can win. Paralysis from bilateral activation."
  },
  "blanket_pattern": {
    "type": "boundary",
    "description": "Blanket misshapen — the boundary between competing needs is unclear."
  },
  "somatic_markers": ["solarPlexus", "upperChest", "jaw", "shoulders", "stomach"],
  "sensation_qualities": ["tightness", "pressure", "heat", "ache", "contraction"],
  "clinical_risk": "moderate",
  "status": "shipping"
}
```

## T8: Living in the Body Under Strain

```json
{
  "territory": "body",
  "number": 8,
  "name": "Living in the Body Under Strain",
  "core_prediction": "My body is the problem. The body is a source of suffering, not information.",
  "affect_signature": {
    "primary": ["Variable by presentation"],
    "pattern": "Brain maintains high-confidence pain/body prediction that persists after tissue healing or distorts body perception."
  },
  "blanket_pattern": {
    "type": "mismatch",
    "description": "Existential/neurological — the brain's body model doesn't match the body's reality."
  },
  "somatic_markers": ["variable — depends on pain/image/eating presentation"],
  "sensation_qualities": ["pain", "tightness", "ache", "numbness", "pressure"],
  "clinical_risk": "moderate",
  "status": "shipping"
}
```

## T9: Living in a System Under Pressure

```json
{
  "territory": "systemPressure",
  "number": 9,
  "name": "Living in a System Under Pressure",
  "core_prediction": "The stress is real. The environment is genuinely adverse.",
  "affect_signature": {
    "primary": ["System-appropriate response (not pathological)"],
    "pattern": "Threat predictions are accurate. The alarm is not malfunctioning. The building is actually on fire."
  },
  "blanket_pattern": {
    "type": "porosity",
    "description": "Blanket too thin — but appropriately so. The external state IS threatening."
  },
  "somatic_markers": ["shoulders", "jaw", "upperBack", "lowerBack", "headScalp"],
  "sensation_qualities": ["tightness", "heaviness", "ache", "pressure", "heat"],
  "clinical_risk": "low",
  "status": "shipping",
  "clinical_note": "NEVER frame regulation as 'calming down.' Frame as 'building resources for staying present in a hard situation.'"
}
```

## T10: Living in Transition

```json
{
  "territory": "transition",
  "number": 10,
  "name": "Living in Transition",
  "core_prediction": "My model of the world is obsolete. The operating system is being rewritten while I still need to function.",
  "affect_signature": {
    "primary": ["SEEKING disrupted", "PANIC/GRIEF active"],
    "pattern": "Global model revision. Every familiar context generates mismatch. Groundlessness as primary somatic signature."
  },
  "blanket_pattern": {
    "type": "boundary",
    "description": "Blanket misshapen — the old shape no longer fits, the new shape hasn't formed."
  },
  "somatic_markers": ["stomach", "upperChest", "feet", "wholeBody"],
  "sensation_qualities": ["floating", "hollow", "heaviness", "buzzing", "nausea"],
  "clinical_risk": "moderate",
  "status": "shipping",
  "clinical_note": "Distinct from T3: T3 = specific object lost. T10 = entire predictive model obsolete."
}
```

## T11: Living in Shame

```json
{
  "territory": "shame",
  "number": 11,
  "name": "Living in Shame",
  "core_prediction": "I am fundamentally defective. If people really saw me, they would leave.",
  "affect_signature": {
    "primary": ["PANIC/GRIEF active", "Self-model damage"],
    "pattern": "Parasympathetic withdrawal response: shrinking, heat in face, gaze aversion. Social submission signal."
  },
  "blanket_pattern": {
    "type": "damage",
    "description": "Blanket torn — the self-model itself is wounded."
  },
  "somatic_markers": ["forehead", "eyes", "upperChest", "stomach", "throat"],
  "sensation_qualities": ["heat", "contraction", "heaviness", "hollow", "nausea"],
  "clinical_risk": "high",
  "status": "planned",
  "clinical_note": "The word 'should' is banned in T11 content. Every string reviewed for inadvertent shame amplification."
}
```

## T12: Living in Addiction and Compulsion

```json
{
  "territory": "addiction",
  "number": 12,
  "name": "Living in Addiction and Compulsion",
  "core_prediction": "This substance/behavior reliably changes my state when nothing else does.",
  "affect_signature": {
    "primary": ["SEEKING hijacked"],
    "pattern": "Reward architecture captured. Natural pleasure sources precision-weighted downward. Craving is SEEKING activating toward predicted reward."
  },
  "blanket_pattern": {
    "type": "boundary",
    "description": "Blanket misshapen — the boundary between need and compulsion is blurred."
  },
  "somatic_markers": ["stomach", "upperChest", "throat", "hands", "jaw"],
  "sensation_qualities": ["pulsing", "heat", "tightness", "buzzing", "ache"],
  "clinical_risk": "critical",
  "status": "planned",
  "clinical_note": "Day 1 withdrawal risk screening required. Withdrawal indicators → immediate ResourceCatalog escalation. No program content until medical safety confirmed."
}
```

## T13: Living Behind a Mask

```json
{
  "territory": "mask",
  "number": 13,
  "name": "Living Behind a Mask",
  "core_prediction": "My authentic self is unacceptable. The performance is the only safe option.",
  "affect_signature": {
    "primary": ["SEEKING intact but misdirected", "PLAY↓"],
    "pattern": "Self-monitoring system oriented externally. Interoceptive signal overridden by social performance signal."
  },
  "blanket_pattern": {
    "type": "rigidity",
    "description": "Blanket too thick — authentic signals cannot reach the surface."
  },
  "somatic_markers": ["jaw", "shoulders", "upperChest", "throat"],
  "sensation_qualities": ["tightness", "numbness", "hollow", "contraction"],
  "clinical_risk": "moderate",
  "status": "planned",
  "clinical_note": "L1 innovation: two-body-scan — first the 'social body' (performance), then the 'deeper body' (underneath). The gap is the therapeutic data."
}
```

## T14: Living With an Altered Body/Mind

```json
{
  "territory": "alteredBodyMind",
  "number": 14,
  "name": "Living With an Altered Body/Mind",
  "core_prediction": "My brain/body works differently from what the world expects. The mismatch is exhausting.",
  "affect_signature": {
    "primary": ["Context-dependent"],
    "pattern": "Brain's predictions are accurate for how the nervous system actually works. The pathology is in the fit, not the person."
  },
  "blanket_pattern": {
    "type": "mismatch",
    "description": "Environment-person mismatch — the world was designed for a different neurological profile."
  },
  "somatic_markers": ["variable — depends on neurotype and condition"],
  "sensation_qualities": ["buzzing", "heaviness", "pressure", "pain", "numbness"],
  "clinical_risk": "low",
  "status": "planned",
  "clinical_note": "NEVER pathologize. NEVER frame as 'managing symptoms.' Frame as 'building capacity to work WITH how your system operates.'"
}
```

## T15: Living in Existential Confrontation

```json
{
  "territory": "existential",
  "number": 15,
  "name": "Living in Existential Confrontation",
  "core_prediction": "The prediction error is not an error. I am accurately perceiving fundamental features of human existence.",
  "affect_signature": {
    "primary": ["Variable — high engagement, accurate perception"],
    "pattern": "Implicit buffering predictions (the world is meaningful, death is far away) have failed. Full awareness floods in."
  },
  "blanket_pattern": {
    "type": "limit",
    "description": "Model limit — the brain encounters what it cannot predict or resolve."
  },
  "somatic_markers": ["upperChest", "stomach", "throat", "wholeBody"],
  "sensation_qualities": ["heaviness", "hollow", "ache", "stillness", "expansion"],
  "clinical_risk": "moderate",
  "status": "planned",
  "clinical_note": "Program cannot and should not resolve existential realities. Builds capacity to be present with them. Distinguish carefully from T2 (shutdown)."
}
```

## T16: Living With a Changing Brain

```json
{
  "territory": "changingBrain",
  "number": 16,
  "name": "Living With a Changing Brain",
  "core_prediction": "My brain's model of its own cognitive capacity no longer matches actual performance.",
  "affect_signature": {
    "primary": ["Variable — cognitive capacity shifts"],
    "pattern": "Every failed cognitive prediction (word not found, purpose forgotten) generates prediction error, frustration, and fear."
  },
  "blanket_pattern": {
    "type": "limit",
    "description": "Progressive change — the model must continuously update as capacity shifts."
  },
  "somatic_markers": ["headScalp", "forehead", "upperChest", "hands"],
  "sensation_qualities": ["pressure", "tightness", "numbness", "buzzing", "heaviness"],
  "clinical_risk": "high",
  "status": "deferred",
  "clinical_note": "Deferred to v4.0. Core self (body-based, moment-to-moment) persists even through significant cognitive decline. Body-based practices remain accessible when cognitive ones do not."
}
```

---

*CSO v1.1 — Updated May 2026*

*© 2026 Cathexis Health. CC BY-NC-SA 4.0.*
