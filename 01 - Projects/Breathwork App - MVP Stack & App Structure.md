---
type: project-note
status: active
created: 2026-04-17
updated: 2026-04-17
tags:
  - project
  - breathwork
  - mvp
  - stack
  - architecture
  - openclaw
---

# Breathwork App - MVP Stack & App Structure

## Purpose
Capture the chosen technical direction for the fast personal MVP and outline a simple app structure to build from.

## Chosen MVP Direction
The goal is not to overbuild.

This version is for:
- personal use first
- fast iteration
- proving the daily recommendation loop
- keeping the technical setup lightweight
- using OpenClaw as the Telegram messaging layer

## Recommended MVP Stack

### Core stack
- Node.js
- TypeScript
- SQLite
- node-cron
- OpenClaw for Telegram messaging / interaction

## Why This Stack
### Node.js + TypeScript
- familiar and practical
- good for recommendation and scheduling logic
- keeps the codebase clean as the app grows

### SQLite
- simple and lightweight
- good enough for a personal MVP
- avoids unnecessary setup overhead

### node-cron
- enough for daily scheduled check-ins
- simple and fast for version one

### OpenClaw
- handles the Telegram conversation layer
- reduces the need for separate Telegram bot plumbing
- fits naturally with your current setup

## What This MVP Intentionally Skips
- Payload CMS
- admin panel
- Postgres setup
- subscriptions / monetization
- advanced analytics
- multi-user product complexity beyond basic support
- web frontend
- heavy Telegram framework dependency as the primary integration layer

## MVP Success Condition
The MVP is successful if it can:
1. onboard one user
2. store a basic profile
3. send a daily prompt
4. ask the 3 key questions
5. recommend one practice
6. optionally log whether the practice was completed

## Suggested App Structure

```text
breathwork-bot/
  src/
    core/
      recommendation/
      scheduling/
      onboarding/
      messaging/
    data/
      practices/
      repositories/
    db/
      schema/
      client/
    utils/
    index.ts
  data/
    practices.json
  package.json
  tsconfig.json
  .env
```

## Suggested Folder Roles

### `src/core/`
Main business logic.

Suggested areas:
- onboarding flow logic
- recommendation logic
- scheduling logic
- completion logging logic
- OpenClaw messaging coordination

### `src/data/`
Application data access layer.

Suggested areas:
- practice loading
- user profile repository
- session log repository

### `src/db/`
Database setup and schema.

Suggested contents:
- SQLite connection
- migration or schema definitions

### `data/practices.json`
Initial structured breath practice data.

This could later move into a richer storage system, but for MVP it can remain simple.

## Minimal Data Needs

### users
Suggested fields:
- id
- telegramUserId
- wakeUpTime
- timezone
- experienceLevel
- practicePreference
- preferredSessionLength
- safetyFlags
- onboardingComplete

### sessions
Suggested fields:
- id
- userId
- date
- desiredOutcome
- currentState
- timeAvailable
- recommendedPracticeSlug
- completed
- reflection

### practices
Suggested fields:
- name
- slug
- supports
- energeticLevel
- nervousSystemEffect
- contraindications
- durationOptions
- shortInstructions

## Suggested First Build Order
1. local app shell
2. onboarding flow logic
3. local practice library
4. recommendation function
5. daily scheduling
6. OpenClaw message triggering / response handling
7. session logging
8. polish / testing

## Important Simplicity Rules
- one user can be enough at first
- one daily check-in only
- one recommendation only
- button-based UI where possible
- practice data can start as JSON
- do not build an admin panel yet
- use Telegram Bot API only if OpenClaw leaves a real gap

## Notes
- This stack is intentionally chosen for speed and learning.
- OpenClaw should be treated as the primary Telegram-facing layer for the personal MVP.
- If the bot proves valuable, it can later graduate to a more scalable architecture.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Telegram Bot MVP Build Plan]]
- [[01 - Projects/Breathwork App - Telegram Bot Architecture]]
- [[01 - Projects/Breathwork App - Onboarding Prompts & Button Copy]]
