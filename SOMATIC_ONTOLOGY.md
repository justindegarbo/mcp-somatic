# Cathexis Somatic Ontology (CSO) v1.1 — Developer Reference

**Namespace:** `https://cathexis.health/ontology/cso/v1.1/`
**Published:** Zenodo DOI [10.5281/zenodo.19157529](https://doi.org/10.5281/zenodo.19157529)
**Formats:** OWL (Turtle), OWL/XML, JSON-LD

## Overview

The CSO defines the vocabulary for representing body-based therapeutic experience computationally. It contains 17 classes and 133 individuals organized within a Markov blanket framework (Friston's free energy principle).

An agent that understands the CSO can interpret structured somatic observations: where in the body a sensation is occurring, what quality it has, what neurobiological territory it maps to, and what therapeutic trajectory the user is on.

## Body Zones (29)

Each zone maps to an anatomical region with clinical significance for somatic therapy.

| # | Zone | URI | Clinical Significance |
|---|------|-----|----------------------|
| 1 | Head/Forehead | `cso:headForehead` | Cognitive overload, tension headache, dissociation |
| 2 | Eyes | `cso:eyes` | Hypervigilance, tear suppression, visual narrowing |
| 3 | Jaw/Mouth | `cso:jawMouth` | Clenching, anger suppression, verbal inhibition |
| 4 | Temples | `cso:temples` | Stress response, temporal tension, TMJ referral |
| 5 | Ears | `cso:ears` | Auditory sensitivity, tinnitus under stress |
| 6 | Throat/Neck | `cso:throatNeck` | Voice suppression, swallowing difficulty, vulnerability |
| 7 | Back of Neck | `cso:backOfNeck` | Hypervigilance, fight-or-flight, postural guarding |
| 8 | Left Shoulder | `cso:leftShoulder` | Burden-bearing, emotional weight, protective posture |
| 9 | Right Shoulder | `cso:rightShoulder` | Action-oriented tension, responsibility, effort |
| 10 | Upper Chest | `cso:upperChest` | Anxiety, breath restriction, cardiac awareness |
| 11 | Heart Center | `cso:heartCenter` | Grief, longing, emotional openness/closure |
| 12 | Solar Plexus | `cso:solarPlexus` | Core anxiety, gut instinct, power center |
| 13 | Upper Back | `cso:upperBack` | Emotional armoring, grief storage, postural collapse |
| 14 | Mid-Back | `cso:midBack` | Structural support, fatigue, unexpressed emotion |
| 15 | Lower Back | `cso:lowerBack` | Foundation, safety, chronic pain, support deficit |
| 16 | Left Upper Arm | `cso:leftUpperArm` | Reaching/withdrawing, connection-seeking |
| 17 | Right Upper Arm | `cso:rightUpperArm` | Action, pushing away, boundary-setting |
| 18 | Hands/Fingers | `cso:handsFingers` | Fine motor anxiety, gripping, releasing |
| 19 | Abdomen | `cso:abdomen` | Visceral emotion, nausea, gut-brain axis |
| 20 | Pelvis/Hips | `cso:pelvisHips` | Stability, sexuality, stored trauma, grounding |
| 21 | Left Thigh | `cso:leftThigh` | Forward movement, support, large muscle tension |
| 22 | Right Thigh | `cso:rightThigh` | Forward movement, support, large muscle tension |
| 23 | Knees | `cso:knees` | Flexibility, rigidity, submission, collapse |
| 24 | Calves/Shins | `cso:calvesShins` | Readiness to move, restlessness, grounding |
| 25 | Feet | `cso:feet` | Grounding, foundation, connection to earth |
| 26 | Pelvic Floor | `cso:pelvicFloor` | Trauma storage, safety, autonomic regulation |
| 27 | Inner Ear/Vestibular | `cso:innerEarVestibular` | Balance, disorientation, dissociation |
| 28 | Whole Body | `cso:wholeBody` | Systemic activation, diffuse sensation |
| 29 | Internal/Visceral | `cso:internalVisceral` | Deep organ sensation, interoceptive signals |

**Expansion zones (26-29)** were added in CSO v1.1 based on clinical observation of underrepresented somatic patterns.

## Sensation Qualities (20)

Phenomenological descriptors for what a sensation feels like.

| Quality | URI | Category |
|---------|-----|----------|
| Tightness | `cso:tightness` | Constriction |
| Pressure | `cso:pressure` | Constriction |
| Heaviness | `cso:heaviness` | Weight |
| Lightness | `cso:lightness` | Weight |
| Warmth | `cso:warmth` | Temperature |
| Coolness | `cso:coolness` | Temperature |
| Tingling | `cso:tingling` | Activation |
| Numbness | `cso:numbness` | Absence |
| Pain | `cso:pain` | Nociception |
| Ache | `cso:ache` | Nociception |
| Buzzing | `cso:buzzing` | Activation |
| Pulsing | `cso:pulsing` | Rhythm |
| Churning | `cso:churning` | Movement |
| Hollow | `cso:hollow` | Absence |
| Sharp | `cso:sharp` | Acute |
| Burning | `cso:burning` | Temperature (extreme) |
| Floating | `cso:floating` | Dissociation |
| Trembling | `cso:trembling` | Activation |
| Constriction | `cso:constriction` | Constriction |
| Expansion | `cso:expansion` | Opening |

**Expansion qualities (16-20)** were added in CSO v1.1 for temperature extremes, dissociative states, and autonomic activation patterns.

## Primary Affect Systems (7)

Panksepp's genetically encoded motivational systems. URI convention: UPPERCASE.

| System | URI | Core Function |
|--------|-----|---------------|
| SEEKING | `cso:SEEKING` | Dopaminergic motivation, exploration, anticipation |
| FEAR | `cso:FEAR` | Threat detection, freezing, flight |
| RAGE | `cso:RAGE` | Frustration, assertion, boundary violation response |
| PANIC/GRIEF | `cso:PANIC_GRIEF` | Separation distress, attachment loss |
| CARE | `cso:CARE` | Nurturing, oxytocin-mediated bonding |
| PLAY | `cso:PLAY` | Social learning, joy, rough-and-tumble |
| LUST | `cso:LUST` | Sexual motivation, reproductive drive |

## Brain Regions (19)

Neuroanatomical regions referenced in territory profiles.

| Region | URI | Function |
|--------|-----|----------|
| Anterior Insula | `cso:anteriorInsula` | Interoceptive awareness hub |
| Posterior Insula | `cso:posteriorInsula` | Primary interoceptive cortex |
| Amygdala | `cso:amygdala` | Salience detection, threat processing |
| Anterior Cingulate | `cso:anteriorCingulate` | Conflict monitoring, error detection |
| Prefrontal Cortex | `cso:prefrontalCortex` | Executive function, regulation |
| Orbitofrontal Cortex | `cso:orbitofrontalCortex` | Value computation, decision-making |
| Hippocampus | `cso:hippocampus` | Contextual memory, spatial processing |
| Hypothalamus | `cso:hypothalamus` | Autonomic regulation, body budgeting |
| PAG | `cso:periaqueductalGray` | Pain modulation, defensive behavior |
| Basal Ganglia | `cso:basalGanglia` | Habit formation, procedural learning |
| Nucleus Accumbens | `cso:nucleusAccumbens` | Reward processing, SEEKING system |
| Cerebellum | `cso:cerebellum` | Motor coordination, prediction timing |
| Ventral Striatum | `cso:ventralStriatum` | Reward prediction, motivation |
| Dorsal Striatum | `cso:dorsalStriatum` | Habit execution, procedural memory |
| Thalamus | `cso:thalamus` | Sensory relay, consciousness gating |
| Brain Stem | `cso:brainStem` | Autonomic regulation, arousal |
| Somatosensory Cortex | `cso:somatosensoryCortex` | Body representation, touch processing |
| Temporal Pole | `cso:temporalPole` | Social cognition, emotional memory |
| Ventromedial PFC | `cso:ventromedialPFC` | Self-referential processing, default mode |

## Brain Networks (8)

Distributed functional networks (Pessoa's entangled brain framework).

| Network | URI | Function |
|---------|-----|----------|
| Salience | `cso:salience` | Detecting and prioritizing relevant stimuli |
| Default Mode | `cso:defaultMode` | Self-referential processing, internal narrative |
| Executive | `cso:executive` | Cognitive control, working memory, planning |
| Reward | `cso:reward` | Motivation, reinforcement, pleasure |
| Fear/Threat | `cso:fearThreat` | Threat detection and defensive response |
| Interoceptive | `cso:interoceptive` | Internal body state monitoring |
| Social Cognition | `cso:socialCognition` | Mentalizing, theory of mind |
| Motor | `cso:motor` | Action planning, movement execution |

## Ecological Layers (5)

Bronfenbrenner's ecological model adapted for somatic context.

| Layer | URI | Scope |
|-------|-----|-------|
| Micro | `cso:micro` | Intimate relationships, household |
| Meso | `cso:meso` | Work, school, community organizations |
| Exo | `cso:exo` | Systems that affect but don't contain (healthcare, policy) |
| Macro | `cso:macro` | Culture, economy, political climate |
| Chrono | `cso:chrono` | Life transitions, temporal changes |

## Blanket Components (4)

The Markov blanket framework organizing all entities.

| Component | URI | Contains |
|-----------|-----|----------|
| Internal State | `cso:internalState` | Body zones, sensation qualities, affect systems |
| External State | `cso:externalState` | Ecological layers, world context |
| Sensory State | `cso:sensoryState` | Interoceptive signals, check-in data |
| Active State | `cso:activeState` | Interventions, regulation mechanisms |

## Data Structures

### SomaticDataPoint

A single observation from a check-in.

```json
{
  "@context": "https://cathexis.health/ontology/cso/v1.1/context.jsonld",
  "@type": "SomaticDataPoint",
  "zone": "cso:upperChest",
  "quality": "cso:tightness",
  "intensity": 0.7,
  "timestamp": "2026-03-21T14:30:00Z"
}
```

### SomaticSnapshot

A complete check-in (multiple data points at one timestamp).

```json
{
  "@type": "SomaticSnapshot",
  "timestamp": "2026-03-21T14:30:00Z",
  "dataPoints": [
    { "zone": "cso:upperChest", "quality": "cso:tightness", "intensity": 0.7 },
    { "zone": "cso:solarPlexus", "quality": "cso:churning", "intensity": 0.5 },
    { "zone": "cso:jawMouth", "quality": "cso:pressure", "intensity": 0.6 }
  ],
  "context": ["work_stress", "sleep_poor"],
  "territory": "cso:threat"
}
```

### SomaticTrajectory

A time series of snapshots showing change over days/weeks.

```json
{
  "@type": "SomaticTrajectory",
  "userId": "anonymized-hash",
  "territory": "cso:threat",
  "snapshots": ["...array of SomaticSnapshot..."],
  "trajectory": "improving",
  "confidenceScore": 0.82
}
```

## Cross-Mappings

| CSO Entity | ICD-11 | SNOMED CT | FHIR Resource |
|------------|--------|-----------|---------------|
| SomaticDataPoint | — | 106147001 (Sensation quality) | Observation |
| Territory | F40-F48 (varies) | 404684003 (Clinical finding) | Condition |
| Intervention | — | 362961001 (Procedure) | Procedure |
| Program | — | 243120004 (Regimen/therapy) | CarePlan |

## Version History

| Version | Date | Changes |
|---------|------|---------|
| v1.0 | Feb 2026 | Initial: 24 zones, 15 qualities, 16 territories |
| v1.1 | Mar 2026 | Added: 5 zones (26-29 + whole body), 5 qualities (16-20), brain regions (19), brain networks (8), ecological layers (5), blanket configurations. URI scheme formalized. OWL/JSON-LD published. |
