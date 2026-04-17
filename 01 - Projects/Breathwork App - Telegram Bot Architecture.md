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
---

# Breathwork App - Telegram Bot Architecture

## Purpose
Sketch the practical architecture for a first version of the Breathwork App as a Telegram bot.

## Product Shape
Version one should be simple and reliable.

Core loop:
1. User completes onboarding
2. Bot stores profile and wake-up time
3. Bot sends a daily check-in
4. User answers short prompts
5. Bot recommends one practice
6. User optionally completes the practice and gives lightweight feedback

## Core Components

### 1. Telegram Bot Interface
Responsibilities:
- receive user messages and button selections
- send onboarding prompts
- send daily check-ins
- deliver practice recommendations
- collect simple feedback

Likely interaction style:
- button-based prompts
- short responses
- minimal free-text input

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

## 3. Practice Library
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

## 4. Recommendation Engine
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

## 5. Scheduling Layer
Responsibilities:
- trigger daily messages based on wake-up time
- respect timezone
- avoid duplicate sends
- allow future support for additional reminders

Could later support:
- midday reset
- pre-sleep prompt
- custom reminders

## 6. Response / Session Logging
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
- Telegram Bot API
- simple app backend
- database for users, practices, and logs
- scheduler / cron for wake-up messages

Potential implementation paths:
- lightweight Node/TypeScript backend
- Payload-based content management for practices if desired later
- separate bot logic service if the system grows

## Recommended V1 Simplicity Rules
- only one daily primary check-in
- only one recommended practice per interaction
- no complicated branching at first
- no giant knowledge dump in the chat
- keep buttons and flows tight

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
- The first version should optimize for usefulness and consistency, not feature volume.
- The architecture should stay simple enough to ship, but structured enough to grow.
- Practice metadata quality will matter as much as the software architecture.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Bot Flow]]
- [[01 - Projects/Breathwork App - Practice Data Model]]
- [[01 - Projects/Breathwork App - Recommendation Logic]]
