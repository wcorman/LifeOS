---
type: project-note
status: active
created: 2026-04-17
updated: 2026-04-17
tags:
  - project
  - breathwork
  - data-model
  - examples
---

# Breathwork App - Structured Practice Examples

## Purpose
Test the practice data model by converting a few real techniques into structured entries.

These are not final medical or facilitation-grade records yet. They are working examples to help validate the app model.

---

## Practice Example 1
```yaml
name: Alternate Nostril Breathing
alternateNames:
  - Nadi Shodhana
slug: alternate-nostril-breathing
category: balancing
summary: A balancing breath practice that supports steadiness, clarity, and nervous system regulation.
whyUseIt: Useful when the user wants balance, focus, or a more centered state.
energeticLevel: balancing
carbonDioxideEffect: mild increase
nitricOxideEffect: mild increase
nervousSystemEffect: parasympathetic / ventral vagal complex
guna: sattva
nadi: sushumna
vayu: prana
supports:
  - balance
  - focus
  - calm
bestFor:
  - feeling scattered
  - seeking steadiness
  - preparing for meditation
avoidWhen:
  - severe nasal congestion
idealTimeOfDay:
  - morning
  - midday
  - evening
recommendedContexts:
  - daily regulation
  - transition between activities
  - spiritual practice
difficulty: beginner
defaultDuration: 5 min
durationOptions:
  - 2 min
  - 5 min
  - 10 min
shortInstructions: Inhale through one nostril, exhale through the other, then alternate sides in a slow and steady rhythm.
longInstructions: Sit comfortably, use the fingers to alternate nostrils, and keep the breath relaxed and even without strain.
cueingNotes:
  - keep the breath smooth
  - do not force the rhythm
  - stay relaxed in the face and shoulders
contraindications:
  - significant nasal blockage
modifications:
  - practice without retention
retentionInvolved: no
intensityLevel: gentle
source: Pranayama effects directory
notes: Foundational balancing practice with broad usability.
confidenceLevel: medium
```

---

## Practice Example 2
```yaml
name: Bhramari
alternateNames:
  - Humming Bee Breath
slug: bhramari
category: calming
summary: A calming humming breath practice that can help soothe the nervous system and quiet mental agitation.
whyUseIt: Useful when the user wants calm, grounding, or relief from mental overstimulation.
energeticLevel: moderately calming
carbonDioxideEffect: mild increase
nitricOxideEffect: significant increase
nervousSystemEffect: parasympathetic / dorsal vagal complex
guna: tamas
nadi: ida
vayu: udana
supports:
  - calm
  - grounding
  - emotional regulation
bestFor:
  - feeling anxious
  - feeling overstimulated
  - needing to settle the mind
avoidWhen:
  - discomfort with humming or sound-based practices
idealTimeOfDay:
  - evening
  - after stress
  - before sleep
recommendedContexts:
  - nervous system downshifting
  - calming after stimulation
  - pre-rest practice
difficulty: beginner
defaultDuration: 5 min
durationOptions:
  - 2 min
  - 5 min
  - 10 min
shortInstructions: Inhale gently through the nose and exhale with a smooth humming sound.
longInstructions: Sit comfortably, soften the jaw and face, inhale through the nose, and let the exhale become a steady hum that you can feel in the head and chest.
cueingNotes:
  - let the hum be smooth, not forced
  - keep the exhale comfortable
  - feel the vibration rather than performing it
contraindications:
  - none noted yet
modifications:
  - shorten the exhale if it feels strained
retentionInvolved: no
intensityLevel: gentle
source: Pranayama effects directory
notes: Strong candidate for calm / anxiety-support recommendations.
confidenceLevel: medium
```

---

## Practice Example 3
```yaml
name: Kapalabhati
alternateNames:
  - Skull Shining Breath
slug: kapalabhati
category: energizing
summary: A strong cleansing and energizing breath practice with active exhalations.
whyUseIt: Useful when the user wants a significant increase in energy and alertness.
energeticLevel: significantly energizing
carbonDioxideEffect: significant decrease
nitricOxideEffect: mild decrease
nervousSystemEffect: sympathetic
guna: rajas
nadi: pingala
vayu: udana
supports:
  - energy
  - alertness
  - activation
bestFor:
  - sluggishness
  - low energy
  - need for activation
avoidWhen:
  - anxiety / panic sensitivity
  - dizziness
  - high sensitivity to strong stimulation
idealTimeOfDay:
  - morning
  - early day
recommendedContexts:
  - morning activation
  - pre-work energy boost
  - when the user is heavy / sluggish but stable
difficulty: intermediate
defaultDuration: 2 min
durationOptions:
  - 1 min
  - 2 min
  - 5 min
shortInstructions: Use active, rhythmic exhalations through the nose with passive inhales.
longInstructions: Sit upright, keep the spine tall, and begin a steady rhythm of sharp exhalations powered by the abdomen while allowing the inhale to happen naturally.
cueingNotes:
  - keep the chest relatively steady
  - drive the breath from the lower abdomen
  - stop if dizziness arises
contraindications:
  - panic sensitivity
  - dizziness history
  - pregnancy
  - high blood pressure
modifications:
  - reduce pace and total rounds
  - substitute with a gentler energizing practice if needed
retentionInvolved: no
intensityLevel: strong
source: Pranayama effects directory
notes: Important test case for safety-aware filtering in recommendations.
confidenceLevel: medium
```

## Notes
- These examples help test whether the chosen fields are actually useful.
- They also highlight where future refinement is needed, especially around contraindications and facilitation detail.
- The next step could be converting the remaining practices one by one or defining a database-friendly JSON version.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Practice Data Model]]
- [[01 - Projects/Breathwork App - Recommendation Logic]]
- [[03 - Resources/Reference/Pranayama Effects Directory]]
