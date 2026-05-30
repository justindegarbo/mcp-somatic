# Cathexis Somatic Ontology (CSO) v1.1

**Namespace:** `https://cathexis.health/ontology/cso/v1.1/`

**BioPortal:** [CXSO](https://bioportal.bioontology.org/ontologies/CXSO)

**Zenodo DOI:** [10.5281/zenodo.20448395](https://doi.org/10.5281/zenodo.20448395)

---

## 1. Body Zones (29)

Anatomical regions for somatic check-in. Each zone maps to a position on the interactive body map silhouette. Users tap to select zones and report sensation quality + intensity.

### Canonical Zones

| # | CSO Term | Code (`BodyZone`) | Display Name | Body Region |
|---|----------|-------------------|--------------|-------------|
| 1 | `cso:headScalp` | `headScalp` | Head / Scalp | Head |
| 2 | `cso:forehead` | `forehead` | Forehead | Head |
| 3 | `cso:eyes` | `eyes` | Eyes | Head |
| 4 | `cso:jaw` | `jaw` | Jaw | Head |
| 5 | `cso:mouthLips` | `mouthLips` | Mouth / Lips | Head |
| 6 | `cso:throat` | `throat` | Throat | Neck |
| 7 | `cso:neckFront` | `neckFront` | Neck (Front) | Neck |
| 8 | `cso:neckBack` | `neckBack` | Neck (Back) | Neck |
| 9 | `cso:shoulders` | `shoulders` | Shoulders | Upper Body |
| 10 | `cso:upperChest` | `upperChest` | Upper Chest | Torso |
| 11 | `cso:solarPlexus` | `solarPlexus` | Solar Plexus | Torso |
| 12 | `cso:stomach` | `stomach` | Stomach | Torso |
| 13 | `cso:lowerAbdomen` | `lowerAbdomen` | Lower Abdomen | Torso |
| 14 | `cso:upperBack` | `upperBack` | Upper Back | Back |
| 15 | `cso:lowerBack` | `lowerBack` | Lower Back | Back |
| 16 | `cso:upperArms` | `upperArms` | Arms (Upper) | Arms |
| 17 | `cso:forearms` | `forearms` | Forearms | Arms |
| 18 | `cso:hands` | `hands` | Hands | Arms |
| 19 | `cso:hips` | `hips` | Hips | Lower Body |
| 20 | `cso:upperLegs` | `upperLegs` | Upper Legs | Legs |
| 21 | `cso:knees` | `knees` | Knees | Legs |
| 22 | `cso:lowerLegs` | `lowerLegs` | Lower Legs | Legs |
| 23 | `cso:feet` | `feet` | Feet | Legs |
| 24 | `cso:pelvicFloor` | `pelvicFloor` | Pelvic Floor | Torso |
| 25 | `cso:vestibular` | `vestibular` | Vestibular / Balance | Head (Internal) |
| 26 | `cso:heart` | `heart` | Heart | Torso (Internal) |
| 27 | `cso:diaphragm` | `diaphragm` | Diaphragm | Torso (Internal) |
| 28 | `cso:wholeBody` | `wholeBody` | Whole Body | Global |
| 29 | `cso:unspecified` | `unspecified` | Can't Pinpoint | Unlocalized |

Zones 24–27 (pelvicFloor, vestibular, heart, diaphragm) were added in v2.3 to support interoceptive awareness of deep body structures and equilibrium. Zone 28 (wholeBody) captures diffuse, non-localizable activation. Zone 29 (unspecified) captures "I feel something but can't say where" — itself clinically significant data.

---

## 2. Sensation Qualities (20)

Phenomenological descriptors for what the user notices in a body zone. These are raw interoceptive signal descriptions, not emotions. The sensation is the data; the emotion is the user's construction.

### Original Qualities (15)

| # | CSO Term | Code (`SensationQuality`) | Display Name | Animation Family |
|---|----------|--------------------------|--------------|-----------------|
| 1 | `cso:tightness` | `tightness` | Tightness | concentric |
| 2 | `cso:heat` | `heat` | Heat | radial |
| 3 | `cso:cold` | `cold` | Cold | crystalline |
| 4 | `cso:pressure` | `pressure` | Pressure | gradient |
| 5 | `cso:tingling` | `tingling` | Tingling | particle |
| 6 | `cso:numbness` | `numbness` | Numbness | desaturate |
| 7 | `cso:pain` | `pain` | Pain | pulse |
| 8 | `cso:heaviness` | `heaviness` | Heaviness | gradient |
| 9 | `cso:lightness` | `lightness` | Lightness | particle |
| 10 | `cso:pulsing` | `pulsing` | Pulsing | pulse |
| 11 | `cso:hollow` | `hollow` | Hollow | outline |
| 12 | `cso:buzzing` | `buzzing` | Buzzing | particle |
| 13 | `cso:nausea` | `nausea` | Nausea | wave |
| 14 | `cso:ache` | `ache` | Ache | radial |
| 15 | `cso:vibration` | `vibration` | Vibration | concentric |

### Expansion Qualities (5, added v2.3)

| # | CSO Term | Code | Display Name | Animation Family | Clinical Significance |
|---|----------|------|--------------|-----------------|----------------------|
| 16 | `cso:stillness` | `stillness` | Stillness | desaturate | Positive signal in T2 (arrival, not absence) and T15 (presence without action) |
| 17 | `cso:expansion` | `expansion` | Expansion | radial | Positive regulation signal — spaciousness, distinct from heat (which has urgency) |
| 18 | `cso:contraction` | `contraction` | Contraction | concentric | Withdrawal, bracing, protective narrowing — T4, T11 signature |
| 19 | `cso:floating` | `floating` | Floating | particle | Groundlessness (T10) or dissociative lightness (T6) — distinct from lightness (which has buoyancy) |
| 20 | `cso:trembling` | `trembling` | Trembling | particle | Somatic discharge — regulatory (post-activation) or distress (T6 freeze-thaw, T5 spillover) |

---

## 3. Markov Blanket Framework

Every data entity in the Cathexis architecture maps to one of four blanket components derived from Karl Friston's free energy principle. This is the internal organizing architecture — never surfaced to users by name.

| Component | CSO Term | What It Contains |
|-----------|----------|-----------------|
| **Internal State** | `cso:InternalState` | Body sensations, zone activations, sensation qualities, intensity, affect system activation |
| **External State** | `cso:ExternalState` | Context chips, ecological layers, relational map entries, life transitions, HealthKit biometrics |
| **Sensory** | `cso:SensoryState` | Check-in observations, prediction outcomes, assessment responses — the boundary between world and self |
| **Active** | `cso:ActiveState` | Intervention responses, real-world experiment outcomes, regulation practices — the user acting on the world |

---

## 4. Primary Affect Systems (7)

Panksepp's subcortical circuits. These are not constructed emotions — they are genetically encoded functional systems present across all mammals.

| System | CSO Term | Function | Somatic Signature |
|--------|----------|----------|-------------------|
| **SEEKING** | `cso:SEEKING` | Dopaminergic motivation, exploration, curiosity | Forward-leaning activation, upper body energization |
| **RAGE** | `cso:RAGE` | Frustration-anger response | Jaw tension, fist clenching, heat in upper body |
| **FEAR** | `cso:FEAR` | Threat detection and avoidance | Chest tightness, shallow breathing, freeze or flight readiness |
| **LUST** | `cso:LUST` | Sexual and appetitive drive | Pelvic/lower body warmth, whole-body activation |
| **CARE** | `cso:CARE` | Nurturing, attachment, bonding | Chest warmth, arm readiness, softening |
| **PANIC/GRIEF** | `cso:PANIC_GRIEF` | Separation distress, loss response | Chest ache, throat constriction, hollow feeling |
| **PLAY** | `cso:PLAY` | Social joy, boundary-testing, spontaneity | Lightness, whole-body buzzing, facial activation |

PLAY suppression is a sensitive clinical marker — a life without play indicates chronic nervous system strain. PLAY reactivation is a marker of program success across territories.

---

## 5. Brain Regions (19)

Anatomical regions rendered in the Neural Net visualization as Bézier paths on SwiftUI Canvas. Activation is always distributed across co-participating regions — never single-region emotion attribution (Barrett + Pessoa design constraint).

| # | Region | Functional Label | Blanket Component |
|---|--------|-----------------|-------------------|
| 1 | Prefrontal Cortex | Prediction & Evaluation | sensory |
| 2 | Anterior Cingulate | Conflict & Error Monitoring | sensory |
| 3 | Posterior Cingulate | Self-Reflection | sensory |
| 4 | Hippocampus | Memory & Context | sensory |
| 5 | Thalamus | Sensory Gateway | sensory |
| 6 | Amygdala | Threat & Salience Detection | sensory |
| 7 | Insula (Anterior) | Body Awareness | internalState |
| 8 | Insula (Posterior) | Body Signal Processing | internalState |
| 9 | Somatosensory Cortex | Touch & Body Mapping | internalState |
| 10 | Hypothalamus | Body Regulation | internalState |
| 11 | Brainstem | Core Survival Systems | internalState |
| 12 | Dorsolateral PFC | Context Processing | externalState |
| 13 | Temporal Pole | Emotional Memory & Meaning | externalState |
| 14 | Lateral Temporal Cortex | Language & Sound Processing | externalState |
| 15 | Parietal Cortex | Spatial Awareness | externalState |
| 16 | Occipital Cortex | Visual Processing | externalState |
| 17 | Motor Cortex | Movement & Regulation | active |
| 18 | Basal Ganglia | Habits & Motivation | active |
| 19 | Cerebellum | Coordination & Timing | active |

---

## 6. Functional Networks (11)

Brain regions group into functional networks. These are the labels users see — never raw anatomical names.

| Network | Primary Component | What It Does |
|---------|------------------|-------------|
| Self-Reflection | sensory | Generates the continuous sense of self. Active during mind-wandering, autobiographical memory, self-referential processing. |
| Attention & Priority | externalState | Detects what matters right now. Switches between internal body signals and external events based on salience. |
| Focus & Planning | externalState | Holds goals in working memory, plans sequences, inhibits irrelevant signals. |
| Body Sensing | internalState | Reads the body's current state. Interoceptive awareness of heart rate, gut signals, breath, temperature. |
| Threat Response | sensory | Detects threat and generates survival responses. Rapid, subcortical, often before conscious awareness. |
| Motivation & Drive | active | Generates curiosity, wanting, approach behavior. The engine behind exploration and goal pursuit. |
| Social Connection | externalState | Reads other people. Infers intentions, tracks social context, models relational dynamics. |
| Learning & Memory | sensory | Consolidates new experiences into lasting patterns. Contextualizes current experience with past. |
| Movement & Regulation | active | Coordinates movement, timing, and autonomic regulation. Body-based regulatory actions. |
| Attachment & Loss | internalState | Processes separation distress and reunion signals. Monitors proximity to attachment figures. |
| Play & Spontaneity | active | Generates social joy, boundary-testing, physical play. Suppression is a clinical marker of chronic strain. |

Networks overlap — the same region participates in multiple networks with different roles. What you experience emerges from the pattern of activation across networks, not from any single one.

---

## 7. Ecological Context Layers (5)

Based on Bronfenbrenner's ecological systems theory, adapted for somatic context tracking. Each layer corresponds to a set of context chips that the user tags during daily check-ins.

| Layer | CSO Term | Scope | Context Chips |
|-------|----------|-------|---------------|
| **Microsystem** | `cso:micro` | Intimate relationships | Partner, Family, Close Friend |
| **Mesosystem** | `cso:meso` | Daily environments | Work/School, Commute, Social Event, Home Environment |
| **Exosystem** | `cso:exo` | Indirect systems | Healthcare, Financial, Legal, Workplace Policies |
| **Macrosystem** | `cso:macro` | Cultural/societal | News/Media, Political Climate, Cultural Pressure |
| **Chronosystem** | `cso:chrono` | Time/transitions | Life transitions (13 types tracked: new relationship, job change, relocation, health change, loss, pregnancy, graduation, retirement, divorce, new child, financial change, legal situation, other) |

---

## 8. Territories (16)

The Human Experience Framework organizes psychological experience into 16 territories. Each territory describes a pattern of nervous system organization — not a diagnosis.

| # | Territory | Code | Primary Affect Signature | Blanket Pattern |
|---|-----------|------|--------------------------|-----------------|
| T1 | Living in Threat | `threat` | FEAR↑ SEEKING↓ PLAY↓ | Too thin (porosity) |
| T2 | Living in Shutdown | `shutdown` | SEEKING↓↓ PLAY↓ | Too thick (rigidity) |
| T3 | Living in Loss | `loss` | PANIC/GRIEF↑ SEEKING variable | Torn (damage) |
| T4 | Living in Disconnection | `disconnection` | PANIC/GRIEF suppressed, CARE↓ | Too thick (rigidity) |
| T5 | Living in Overwhelm | `overwhelm` | All systems competing | Too thin (porosity) |
| T6 | Living Under Siege | `siege` | FEAR locked, all potentially dysregulated | Torn (damage) |
| T7 | Living in Conflict | `conflict` | SEEKING vs FEAR, or RAGE vs FEAR | Misshapen (boundary) |
| T8 | Living in the Body Under Strain | `body` | Variable by presentation | Existential/neurological |
| T9 | Living in a System Under Pressure | `systemPressure` | System-appropriate (not pathological) | Too thin (porosity) |
| T10 | Living in Transition | `transition` | SEEKING disrupted, PANIC/GRIEF active | Misshapen (boundary) |
| T11 | Living in Shame | `shame` | PANIC/GRIEF + self-model damage | Torn (damage) |
| T12 | Living in Addiction and Compulsion | `addiction` | SEEKING hijacked | Misshapen (boundary) |
| T13 | Living Behind a Mask | `mask` | SEEKING intact but misdirected, PLAY↓ | Too thick (rigidity) |
| T14 | Living With an Altered Body/Mind | `alteredBodyMind` | Context-dependent | Environment-person mismatch |
| T15 | Living in Existential Confrontation | `existential` | Variable — high engagement, accurate perception | Model limit |
| T16 | Living With a Changing Brain | `changingBrain` | Variable — cognitive capacity shifts | Progressive change |

**Currently shipping programs (2.3.5):** T1, T2, T3, T5, T6, T7, T8, T9, T10 (9 territories). T4, T11–T15 shipping throughout 2026. T16 deferred to v4.0.

---

## 9. Theoretical Foundations

Seven research programs, not wellness branding.

| Theorist | Framework | Role in Cathexis |
|----------|-----------|-----------------|
| Lisa Feldman Barrett | Constructed Emotion Theory | Emotions are brain constructions from interoceptive data + context, not discovered essences |
| Karl Friston | Predictive Processing / Active Inference | The brain minimizes prediction error through perception (updating beliefs) and action (changing the world) |
| Jaak Panksepp | Primary Affect Systems | Seven subcortical emotional circuits (SEEKING, RAGE, FEAR, LUST, CARE, PANIC/GRIEF, PLAY) |
| Antonio Damasio | Somatic Markers | Body states guide decision-making; feelings are the conscious reading of body predictions |
| Mark Solms | Neuropsychoanalysis | Consciousness is affective at its core; the feeling of being alive arises from brainstem homeostatic processes |
| Luiz Pessoa | Entangled Brain | No single brain region is "for" any emotion; function emerges from network co-participation |
| Eric Kandel | Memory Systems & Reconsolidation | Memories become labile when reactivated; prediction error during reconsolidation enables updating (with Nader, Schiller, Ecker) |

Essential addition: **Bud Craig** — interoception framework. The pathway from body signal to conscious feeling.

---

*CSO v1.1 — Updated May 2026*

*© 2026 Cathexis Health. CC BY-NC-SA 4.0.*
