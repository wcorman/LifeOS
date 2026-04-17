---
type: project-note
status: active
created: 2026-04-17
updated: 2026-04-17
tags:
  - project
  - breathwork
  - telegram
  - architecture
  - bot
  - openclaw
---

# Breathwork App - Telegram / OpenClaw Architecture

## Purpose
Sketch the practical architecture for a first version of the Breathwork App with OpenClaw as the messaging layer.

## Architecture Shift
The core change is this:
- OpenClaw handles the Telegram messaging layer
- the breathwork app handles profile storage, practice data, recommendation logic, and scheduling logic

This means the project does not need to treat Telegraf as the primary interface layer for the personal MVP.

## Product Shape
Version one should still be simple and reliable.

Core loop:
1. User completes onboarding
2. System stores profile and wake-up time
3. OpenClaw sends a daily check-in
4. User answers short prompts
5. Recommendation logic chooses one practice
6. OpenClaw delivers the recommendation
7. User optionally completes the practice and gives lightweight feedback

## Core Components

### 1. OpenClaw Messaging Layer
Responsibilities:
- send onboarding prompts
- send daily check-ins
- receive button selections or replies
- deliver practice recommendations
- collect lightweight follow-up responses

Likely interaction style:
- button-based prompts
- short responses
- minimal free-text input

Telegram Bot API remains available as a fallback if lower-level Telegram plumbing is ever needed.

### 2. User Profile Layer
This stores persistent user information.

Suggested profile fields:
- telegramUserId
- displayName
- wakeUpTime
- timezone
- experienceLevel
- practicePreference
- preferredSessionLength
- sensitivityFlags
- onboardingComplete

### 3. Practice Library
This is the structured database of breath practices.

Suggested fields:
- id
- name
- alternateNames
- supports
- energeticLevel
- nervousSystemEffect
- contraindications
- durationOptions
- difficulty
- shortInstructions
- longInstructions
- notes

This layer should come from the practice data model already being developed in Life OS.

### 4. Recommendation Engine
Responsibilities:
- receive daily user inputs
- apply safety filters
- match desired outcome
- adjust for current state
- match time available
- return one recommended practice

Inputs:
- current state
- desired outcome
- time available
- user profile
- practice library

Output:
- selected practice
- brief explanation
- instructions
- optional note / caution

### 5. Scheduling Layer
Responsibilities:
- trigger daily messages based on wake-up time
- respect timezone
- avoid duplicate sends
- allow future support for additional reminders

Could later support:
- midday reset
- pre-sleep prompt
- custom reminders

### 6. Response / Session Logging
Useful to store:
- date
- prompt sent
- user responses
- practice recommended
- whether user completed it
- optional user feedback

This creates value later for:
- habit tracking
- personalization
- analytics
- better recommendations

## Suggested V1 User Flow

### Onboarding
- welcome message
- explain what the bot does
- ask wake-up time
- ask experience level
- ask preferred length
- ask practice preference
- ask sensitivity / safety questions
- confirm setup complete

### Daily Check-In
Prompt sequence:
1. What are you needing most right now?
2. How do you feel right now?
3. How much time do you have?

Then:
- recommend one practice
- explain why
- provide instructions
- optionally ask: Did you do it?

## Suggested Tech Shape
This does not need to be overcomplicated in version one.

Possible stack:
- OpenClaw for messaging / Telegram interaction
- simple local app backend or script layer
- database for users, practices, and logs
- scheduler / cron for wake-up messages or OpenClaw-compatible timing flow

Potential implementation paths:
- lightweight Node/TypeScript backend with OpenClaw integration
- OpenClaw-first orchestration with local storage and recommendation logic
- Telegram Bot API only where OpenClaw does not cover a needed interaction

## Recommended V1 Simplicity Rules
- only one daily primary check-in
- only one recommended practice per interaction
- no complicated branching at first
- no giant knowledge dump in the chat
- keep buttons and flows tight
- prefer OpenClaw-native messaging where possible

## Future Architecture Expansions
Later the bot could include:
- saved favorite practices
- streak tracking
- adaptive recommendations
- practice history
- longer guided sessions
- premium / subscription features
- web app companion

## Notes
- OpenClaw should be treated as the primary conversation and delivery layer for the personal MVP.
- Telegram Bot API is still available if more direct plumbing is needed later.
- Practice metadata quality will matter as much as the software architecture.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Bot Flow]]
- [[01 - Projects/Breathwork App - Practice Data Model]]
- [[01 - Projects/Breathwork App - Recommendation Logic]]
