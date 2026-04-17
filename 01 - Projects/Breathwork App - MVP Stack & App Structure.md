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

## Recommended MVP Stack

### Core stack
- Node.js
- TypeScript
- Telegraf
- SQLite
- node-cron

## Why This Stack
### Node.js + TypeScript
- familiar and practical
- good for bot logic
- keeps the codebase clean as recommendation logic grows

### Telegraf
- purpose-built for Telegram bots
- fast to get working
- good support for command / button-based interactions

### SQLite
- simple and lightweight
- good enough for a personal MVP
- avoids unnecessary setup overhead

### node-cron
- enough for daily scheduled check-ins
- simple and fast for version one

## What This MVP Intentionally Skips
- Payload CMS
- admin panel
- Postgres setup
- subscriptions / monetization
- advanced analytics
- multi-user product complexity beyond basic support
- web frontend

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
    bot/
      commands/
      handlers/
      keyboards/
      messages/
    core/
      recommendation/
      scheduling/
      onboarding/
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

### `src/bot/`
Telegram-specific bot behavior.

Suggested contents:
- command handlers
- callback/button handlers
- keyboard builders
- message formatting

### `src/core/`
Main business logic.

Suggested areas:
- onboarding flow logic
- recommendation logic
- scheduling logic
- completion logging logic

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
1. Telegram bot shell
2. onboarding flow
3. local practice library
4. recommendation function
5. daily scheduling
6. session logging
7. polish / testing

## Important Simplicity Rules
- one user can be enough at first
- one daily check-in only
- one recommendation only
- button-based UI where possible
- practice data can start as JSON
- do not build an admin panel yet

## Notes
- This stack is intentionally chosen for speed and learning.
- If the bot proves valuable, it can later graduate to a more scalable architecture.
- The best next step after this note is likely the actual project scaffold or a repo setup checklist.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Telegram Bot MVP Build Plan]]
- [[01 - Projects/Breathwork App - Telegram Bot Architecture]]
- [[01 - Projects/Breathwork App - Onboarding Prompts & Button Copy]]
