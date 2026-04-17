---
type: project-note
status: active
created: 2026-04-17
updated: 2026-04-17
tags:
  - project
  - breathwork
  - data-model
  - app
---

# Breathwork App - Practice Data Model

## Purpose
Define the structure of a single breath practice entry so the knowledge base can later support app logic, recommendations, and user-facing guidance.

## Core Principle
Each practice should be stored in a way that supports:
- human readability in Life OS
- future app / bot recommendation logic
- easy expansion over time
- safety and nuance

## Recommended Fields Per Practice

### Identity
- `name`
- `alternateNames`
- `slug`
- `category`

### Short Description
- `summary`
- `whyUseIt`

### Effects / Classification
- `energeticLevel`
- `carbonDioxideEffect`
- `nitricOxideEffect`
- `nervousSystemEffect`
- `guna`
- `nadi`
- `vayu`

### User Outcome Tags
These are especially important for recommendations.
- `supports`
  - energy
  - calm
  - focus
  - balance
  - grounding
  - sleep
  - emotional regulation
  - spiritual practice

### Use Cases
- `bestFor`
- `avoidWhen`
- `idealTimeOfDay`
- `recommendedContexts`

### Difficulty / Accessibility
- `difficulty`
- `experienceLevel`
- `defaultDuration`
- `durationOptions`

### Instructions
- `shortInstructions`
- `longInstructions`
- `cueingNotes`

### Safety
- `contraindications`
- `modifications`
- `retentionInvolved` (yes / no)
- `intensityLevel`

### Metadata
- `source`
- `notes`
- `confidenceLevel`

## Suggested Value Patterns

### energeticLevel
- significantly calming
- moderately calming
- mildly calming
- balancing
- mildly energizing
- moderately energizing
- significantly energizing

### difficulty
- beginner
- beginner-intermediate
- intermediate
- advanced

### intensityLevel
- gentle
- moderate
- strong

### experienceLevel
- beginner
- intermediate
- experienced

## Example Practice Entry Shape

```yaml
name: Alternate Nostril Breathing
alternateNames:
  - Nadi Shodhana
slug: alternate-nostril-breathing
category: balancing
summary: A balancing breath practice that supports steadiness, clarity, and nervous system regulation.
whyUseIt: Useful when the user wants balance, clarity, or a centered state.
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
  - seeking balance
  - preparing for meditation
avoidWhen:
  - severe congestion
idealTimeOfDay:
  - morning
  - midday
  - evening
recommendedContexts:
  - daily regulation
  - transition between activities
  - spiritual practice
difficulty: beginner
defaultDuration: 5 minutes
durationOptions:
  - 2 min
  - 5 min
  - 10 min
shortInstructions: Inhale through one nostril, exhale through the other, then alternate sides in a smooth rhythm.
longInstructions: ...
cueingNotes:
  - keep the breath gentle
  - do not force the rhythm
contraindications:
  - significant nasal blockage
modifications:
  - practice without retention
retentionInvolved: no
intensityLevel: gentle
source: Pranayama effects directory
notes: Useful foundational balancing practice.
confidenceLevel: medium
```

## Recommended Category Types
Practices may also benefit from a simple top-level category like:
- calming
- balancing
- energizing
- cleansing
- meditative
- cooling
- heating

## App-Oriented Notes
The fields most useful for bot recommendations will likely be:
- `supports`
- `energeticLevel`
- `nervousSystemEffect`
- `contraindications`
- `difficulty`
- `defaultDuration`
- `shortInstructions`

## Notes
- The app does not need every field on day one, but the model should be designed for growth.
- It is better to structure practices well now than retrofit meaning later.
- This note can later evolve into actual app schema or database models.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Bot Flow]]
- [[03 - Resources/Reference/Pranayama Effects Directory]]
