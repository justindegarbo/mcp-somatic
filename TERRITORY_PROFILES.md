# Territory Profiles — Machine-Readable Reference

**16 territories of human experience.** Each represents a distinct neurobiological pattern of suffering with a characteristic predictive model, affect configuration, somatic signature, and network configuration. Derived from the Human Experience Framework (HEF). Full clinical detail in the [HEF Clinical Manual](https://doi.org/10.5281/zenodo.19157697).

## Schema

Each territory profile uses this structure:

```yaml
territory:
  id: T1
  uri: cso:threat
  name: Living in Threat
  status: live | planned | deferred
  version: 2.2
  predictive_pattern: string
  primary_affects: [FEAR, SEEKING_suppressed]
  network_configuration:
    locked_hubs: [amygdala]
    hyperactive: [salience, fearThreat]
    suppressed: [defaultMode, executive]
  somatic_signature:
    primary_zones: [upperChest, solarPlexus, jawMouth]
    primary_qualities: [tightness, pressure, buzzing]
  dsm_correspondences: [F41.1, F43.10]
  change_mechanism: prediction_error
  learning_levels: [L1, L2, L3, L4, L5, L6]
```

## Territory 1: Living in Threat

- **URI:** `cso:threat`
- **Status:** Live (2.2)
- **Predictive pattern:** The world is dangerous. Hypervigilance is survival. Relaxation is exposure.
- **Primary affects:** FEAR (dominant), SEEKING (suppressed)
- **Network configuration:** Amygdala-locked salience network dominance. Default mode suppressed (can't rest). Executive partially available but hijacked for threat scanning. Interoceptive network hyperactive (body as alarm system).
- **Somatic signature:** Upper chest tightness, solar plexus pressure, jaw clenching, shoulder elevation, shallow rapid breathing, tingling in extremities
- **DSM correspondences:** F41.1 Generalized anxiety, F41.0 Panic disorder, F43.10 PTSD (if trauma-related), F40.10 Social anxiety
- **Change mechanism:** Prediction error — generate enough safe experiences to update the threat model
- **Key insight for agents:** This user's body is running a continuous threat scan. Somatic data will show persistent activation in upper body zones. Pattern will be consistent across check-ins with low variability until therapeutic change begins.

## Territory 2: Living in Shutdown

- **URI:** `cso:shutdown`
- **Status:** Live (2.2)
- **Predictive pattern:** Nothing will work. Effort is futile. The system has collapsed.
- **Primary affects:** SEEKING (critically suppressed), PANIC/GRIEF (chronic, low-grade)
- **Network configuration:** Reward network offline (nucleus accumbens hypoactive). Default mode dominant but in ruminative loop. Executive degraded. Motor system suppressed (psychomotor retardation).
- **Somatic signature:** Heaviness (whole body), numbness, chest hollowness, limb heaviness, reduced interoceptive clarity, fatigue unrelated to exertion
- **DSM correspondences:** F32 Major depressive episode, F34.1 Persistent depressive disorder
- **Change mechanism:** SEEKING reactivation — smallest possible prediction errors to restart dopaminergic motivation
- **Key insight for agents:** Low data volume expected (fewer check-ins). When data appears, look for heaviness + numbness + hollow. Absence of data IS data in this territory.

## Territory 3: Living in Loss

- **URI:** `cso:loss`
- **Status:** Live (2.2)
- **Predictive pattern:** The model of the world includes someone/something that is no longer there. The system keeps predicting their presence.
- **Primary affects:** PANIC/GRIEF (acute), SEEKING (searching behavior)
- **Network configuration:** Default mode hyperactive (replaying memories, searching for lost object). Hippocampus generating prediction errors (expecting presence, finding absence). Anterior insula processing the somatic weight of loss.
- **Somatic signature:** Heart center ache, throat constriction, chest heaviness, waves of warmth/crying, hollow abdomen, sudden sharp sensations
- **DSM correspondences:** F43.21 Adjustment disorder with depressed mood, prolonged grief (proposed)
- **Change mechanism:** Model updating — the predictive model must slowly incorporate the permanent absence while preserving the meaning
- **Key insight for agents:** Somatic data will show high variability (waves of activation). Heart center and throat are dominant zones. Intensity spikes may correlate with time-of-day or contextual triggers.

## Territory 4: Living in Disconnection

- **URI:** `cso:disconnection`
- **Status:** Planned (2.3)
- **Predictive pattern:** Closeness is predicted as dangerous. Vulnerability will be punished. Self-sufficiency is the only safety.
- **Primary affects:** PANIC/GRIEF (suppressed — the system needs connection but has learned not to seek it), CARE (receiving is threatening)
- **Network configuration:** Social cognition network disengaged from interoceptive network. Default mode active but dissociated from emotional processing. Amygdala responsive to intimacy cues (not just threat cues).
- **Somatic signature:** Chest numbness, reduced interoceptive clarity, tension in hands/arms (holding back), throat constriction during vulnerability, warmth avoidance
- **DSM correspondences:** Attachment-related presentations, avoidant patterns
- **Change mechanism:** Trust-building through micro-vulnerability — the longest therapeutic arc in the framework
- **Key insight for agents:** This user may produce low-affect somatic data even when internal distress is high. Numbness IS the signal. Look for discrepancy between reported wellbeing and somatic flatness.

## Territory 5: Living in Overwhelm

- **URI:** `cso:overwhelm`
- **Status:** Live (2.2)
- **Predictive pattern:** The system's processing capacity has been exceeded. Inputs outpace the ability to integrate them.
- **Primary affects:** Multiple systems competing simultaneously (FEAR + RAGE + PANIC/GRIEF), SEEKING fragmented
- **Network configuration:** Salience network overwhelmed (everything flagged as urgent). Executive network in cascade failure. Interoceptive network flooded. Default mode fragmented.
- **Somatic signature:** Diffuse whole-body activation, head pressure, chest tightness AND churning, simultaneous contradictory sensations, tingling + numbness co-occurring
- **DSM correspondences:** F43.20 Adjustment disorder with anxiety, stress-related presentations
- **Change mechanism:** Containment — reducing the prediction error load to a processable level, then systematically addressing one stream at a time
- **Key insight for agents:** High-volume, high-variability somatic data. Multiple zones active simultaneously. The signature is chaos, not a specific pattern. Containment is the first priority.

## Territory 6: Living Under Siege

- **URI:** `cso:siege`
- **Status:** Live (2.2)
- **Predictive pattern:** Fragmented prediction — the model itself has been damaged. The system cannot generate reliable predictions about safety.
- **Primary affects:** FEAR (dominant, fragmented), PANIC/GRIEF (dissociated), RAGE (often suppressed)
- **Network configuration:** Amygdala hyperactive with hippocampal disconnection (threat without context). Default mode fragmented (narrative discontinuity). Executive intermittently available. Dissociation as active inference (reducing unbearable prediction error).
- **Somatic signature:** Dissociative numbness alternating with acute activation, pelvic floor tension, throat constriction, body areas that go "offline," startle responses in somatic data
- **DSM correspondences:** F43.10 PTSD, F43.12 Complex PTSD, F44 Dissociative disorders
- **Change mechanism:** Safety establishment first, then titrated prediction error within the window of tolerance
- **Key insight for agents:** Highest clinical sensitivity territory. Somatic data may show sudden state changes (activation to numbness). NEVER push for more data. Respect missing data as protective.

## Territory 7: Living in Conflict

- **URI:** `cso:conflict`
- **Status:** Planned (2.3)
- **Predictive pattern:** Competing predictions of equal weight — two or more models demanding contradictory action. Paralysis results from irresolvable prediction conflict.
- **Primary affects:** SEEKING (split between options), RAGE (suppressed frustration), FEAR (of choosing wrong)
- **Network configuration:** Executive network oscillating between competing action plans. Anterior cingulate hyperactive (conflict monitoring at maximum). Basal ganglia frozen (procedural system cannot select an action).
- **Somatic signature:** Solar plexus churning, jaw tension, shoulder tension (bilateral), restlessness in legs, pressure in head/temples
- **DSM correspondences:** Perfectionism, indecision, people-pleasing presentations
- **Change mechanism:** Clarifying which prediction is authentic versus which is imposed — somatic resonance as the decision signal
- **Key insight for agents:** Bilateral symmetry in somatic data (both shoulders, both arms). Solar plexus is the discriminating zone. Look for churning that resolves when one option is held in mind.

## Territory 8: Living in the Body Under Strain

- **URI:** `cso:bodyStrain`
- **Status:** Live (2.2)
- **Predictive pattern:** The body itself is the source of unpredictable threat. Pain predictions drive avoidance, avoidance drives deconditioning, deconditioning increases pain.
- **Primary affects:** FEAR (of pain/sensation), SEEKING (suppressed by pain avoidance)
- **Network configuration:** Interoceptive network hypersensitive (precision weighting on pain signals extremely high). PAG dysregulated. Motor network inhibited (fear-avoidance). Somatosensory cortex expanded for pain regions.
- **Somatic signature:** Pain zones dominant, tension surrounding pain areas (guarding), reduced movement-related sensations, intensity ratings higher than other territories
- **DSM correspondences:** Chronic pain conditions, somatic symptom disorder, fibromyalgia presentations
- **Change mechanism:** Graded somatic exposure — slowly reducing the precision weighting on pain predictions through safe body engagement
- **Key insight for agents:** Intensity ratings will be higher than other territories. Focus zones will be consistent and specific. Look for gradual expansion of body awareness beyond pain zones as therapeutic signal.

## Territory 9: Living in a System Under Pressure

- **URI:** `cso:systemPressure`
- **Status:** Planned (2.3)
- **Predictive pattern:** The threat is accurate and external — systemic stressors, discrimination, caregiving burden, financial precarity. The nervous system is correctly reading the environment.
- **Primary affects:** FEAR (reality-based), RAGE (at injustice), CARE (depleted from caregiving)
- **Network configuration:** Salience network accurately calibrated (not hyperactive — the threats are real). Executive network overtaxed by coping demands. Default mode suppressed by constant vigilance. Hypothalamus chronically activated (allostatic load).
- **Somatic signature:** Chronic upper back/shoulder tension, jaw clenching, fatigue, headaches, lower back strain, stomach distress
- **DSM correspondences:** Adjustment disorder, burnout, caregiver stress
- **Change mechanism:** Ecological intervention — the somatic patterns won't resolve without addressing the environmental sources. Somatic work focuses on regulation capacity under ongoing stress.
- **Key insight for agents:** Context chips are essential for this territory. Somatic data without ecological context will look like T1 (threat). The distinguishing factor is that the threat prediction is ACCURATE.

## Territory 10: Living in Transition

- **URI:** `cso:transition`
- **Status:** Planned (2.3)
- **Predictive pattern:** Pervasive model obsolescence — the previous model of the world no longer works and no replacement has formed. Groundlessness.
- **Primary affects:** PANIC/GRIEF (for the lost model), SEEKING (tentative, directionless), FEAR (of the unknown)
- **Network configuration:** Default mode in reconstruction (old self-narrative dissolving). Hippocampus generating high prediction error (environment no longer matches expectations). Executive available but without clear objectives.
- **Somatic signature:** Floating/ungrounded sensations, chest hollowness, feet/leg instability, variable patterns that shift daily, reduced body clarity
- **DSM correspondences:** Adjustment disorder, identity disturbance, life transition presentations
- **Change mechanism:** Tolerate the groundlessness while the new model builds — somatic anchoring as the stable base during reconstruction
- **Key insight for agents:** High variability across days. No stable somatic pattern is the pattern. Life transition data from context chips is critical for interpretation.

## Territory 11: Living in Shame

- **URI:** `cso:shame`
- **Status:** Planned (2.3)
- **Predictive pattern:** Core self-model: "I am fundamentally defective." All social interactions filtered through this prediction. Exposure = annihilation.
- **Primary affects:** PANIC/GRIEF (existential), FEAR (of being seen), RAGE (turned inward)
- **Network configuration:** Default mode locked in negative self-referential processing. Social cognition network hyperactive (constant monitoring of others' reactions). Anterior insula processing visceral shame response. Executive used for concealment rather than engagement.
- **Somatic signature:** Face/neck flushing (even without visible blushing), chest collapse, gaze aversion (reported as eye/head tension), stomach churning, impulse to shrink/hide (whole body constriction)
- **DSM correspondences:** Social anxiety (shame-based), avoidant personality patterns
- **Change mechanism:** Exposure to being seen without the predicted annihilation — the prediction error that "I was visible and survived"
- **Key insight for agents:** Somatic data may be sparse (shame inhibits reporting). Look for upper chest + face/neck + stomach co-activation. Shame often co-occurs with other territories (T1, T4, T6).

## Territory 12: Living in Addiction and Compulsion

- **URI:** `cso:addiction`
- **Status:** Planned (2.3)
- **Predictive pattern:** SEEKING system hijacked — the substance/behavior has become the predicted solution to an underlying territory's distress. The cycle: underlying territory activates → craving → use → temporary relief → underlying territory returns.
- **Primary affects:** SEEKING (hijacked toward substance/behavior), underlying territory affect
- **Network configuration:** Reward network dominated by substance/behavior prediction. Prefrontal regulation degraded. Basal ganglia encoding compulsive routine. The underlying territory's network configuration runs beneath.
- **Somatic signature:** Craving has a somatic signature (usually in the zone associated with the underlying territory, plus hands/mouth/stomach). Post-use: brief somatic relief followed by return of underlying pattern.
- **DSM correspondences:** F10-F19 Substance use disorders, F63 Impulse control disorders
- **Change mechanism:** Identify and treat the underlying territory — the addiction is the active inference solution, not the problem
- **Key insight for agents:** Always look for the territory BENEATH the addiction. The somatic data during craving often reveals the underlying territory's signature. T12 never exists alone.

## Territory 13: Living Behind a Mask

- **URI:** `cso:mask`
- **Status:** Planned (2.3)
- **Predictive pattern:** Core prediction: authentic self is unacceptable. Performance is survival. The gap between performed self and felt self generates chronic somatic tension.
- **Primary affects:** FEAR (of exposure), SEEKING (for validation of performed self), PANIC/GRIEF (for the hidden self)
- **Network configuration:** Executive network chronically engaged in performance maintenance. Default mode split (performed narrative vs. suppressed authentic processing). Social cognition hyperactive for audience monitoring.
- **Somatic signature:** Jaw tension (controlling expression), throat constriction (controlling voice), chest split (felt vs. performed), facial tension, exhaustion from chronic performance
- **DSM correspondences:** Burnout, identity disturbance, some personality disorder presentations
- **Change mechanism:** Safe contexts where the mask can lower — moments where authenticity doesn't produce the predicted punishment
- **Key insight for agents:** Look for somatic discrepancy: reported state ("I'm fine") contradicted by somatic data (chest tightness, jaw tension, throat constriction). The gap IS the territory.

## Territory 14: Living With an Altered Body/Mind

- **URI:** `cso:alteredBodyMind`
- **Status:** Planned (2.3)
- **Predictive pattern:** The body or mind operates differently from the dominant model. The pathology is not in the person — it's in the fit between the person and the environment's expectations.
- **Primary affects:** RAGE (at mismatch), PANIC/GRIEF (for lost normality or unachievable normality), SEEKING (for accommodation and understanding)
- **Network configuration:** Varies widely by presentation. Common: interoceptive network processing signals that don't match the expected model, executive network compensating for processing differences, social cognition navigating non-standard interaction patterns.
- **Somatic signature:** Highly individual. The key is the person's relationship to their body's signals, not the signals themselves. Sensory sensitivities, fatigue patterns, and pain patterns specific to condition.
- **DSM correspondences:** Neurodevelopmental disorders, chronic illness, acquired disability
- **Change mechanism:** Recalibrating the self-model to include the body/mind as it IS rather than as it "should be" — reducing the prediction error between expected and actual embodiment
- **Key insight for agents:** Do NOT interpret somatic data through a neurotypical lens. Baseline patterns will be unique to the individual. Track relative change, not absolute values.

## Territory 15: Living in Existential Confrontation

- **URI:** `cso:existential`
- **Status:** Planned (2.3)
- **Predictive pattern:** Accurate perception of mortality, meaninglessness, isolation, or freedom (Yalom's four existential concerns). The anxiety is philosophically valid, not pathological.
- **Primary affects:** FEAR (of nonexistence), SEEKING (for meaning), PANIC/GRIEF (for the finite)
- **Network configuration:** Default mode in expanded processing (big-picture, abstract). Prefrontal areas engaged in meaning-making. Salience network may be quiet (the threat is abstract, not immediate). Interoceptive network processing the somatic weight of awareness.
- **Somatic signature:** Chest heaviness without panic qualities, hollow sensation (existential emptiness is felt in the body), whole-body awareness, groundlessness without acute distress
- **DSM correspondences:** Existential crisis, post-trauma meaning reconstruction, terminal illness adjustment
- **Change mechanism:** The somatic encounter with groundlessness itself — learning to inhabit the body knowing it is temporary
- **Key insight for agents:** This is not pathology. Somatic data will show contemplative activation, not threat activation. Do not route toward anxiety interventions. The work is integration, not reduction.

## Territory 16: Living With a Changing Brain

- **URI:** `cso:changingBrain`
- **Status:** Deferred (4.0)
- **Predictive pattern:** The predictive model itself is deteriorating. Cognitive decline creates a progressive gap between prediction and reality. The person may or may not be aware of the gap.
- **Primary affects:** FEAR (of loss of self), PANIC/GRIEF (for lost capacities), SEEKING (for familiar patterns)
- **Network configuration:** Progressive network degradation pattern-dependent on diagnosis. Default mode losing coherence. Executive declining. Hippocampal function degrading (new predictions harder to form). Core affect systems relatively preserved (emotional capacity outlasts cognitive).
- **Somatic signature:** Confusion-related tension, agitation patterns, preserved somatic responses to familiar stimuli, increasing reliance on body-based (procedural) memory as declarative fades
- **DSM correspondences:** Neurocognitive disorders (all stages)
- **Change mechanism:** Core self vs. autobiographical self distinction — somatic work targets the preserved core self while the autobiographical self changes
- **Key insight for agents:** Requires caregiver integration (4.0 architecture). The user may not be the primary data reporter. Simplified interfaces, preserved routines, and body-based (not cognitive) approaches.
