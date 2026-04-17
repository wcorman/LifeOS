---
type: project-note
status: active
created: 2026-04-17
updated: 2026-04-17
tags:
  - project
  - breathwork
  - telegram
  - mvp
  - build-plan
---

# Breathwork App - Telegram Bot MVP Build Plan

## Purpose
Turn the breathwork bot idea into a realistic MVP build sequence that can be executed step by step.

## MVP Goal
Build a simple Telegram bot that:
- onboards a user
- stores their basic profile
- sends a daily check-in
- asks a few questions
- recommends one breath practice
- optionally records completion / simple feedback

## MVP Scope
### Must-have
- Telegram bot setup
- onboarding flow
- user profile storage
- daily check-in prompts
- recommendation logic
- practice library
- basic scheduling
- simple completion logging

### Nice-to-have later
- multiple reminders per day
- practice history dashboard
- streaks
- premium features
- web app layer
- advanced personalization

## Recommended Build Sequence

### Phase 1 - Foundation
- Create the Telegram bot
- Choose implementation stack
- Set up repo and environment
- Define database structure
- Load the initial practice library

### Phase 2 - Onboarding
- Build welcome flow
- Build wake-up time capture
- Build onboarding questions
- Save user profile data
- Confirm onboarding complete

### Phase 3 - Daily Check-In
- Trigger a daily message based on wake-up time
- Ask desired outcome
- Ask current state
- Ask time available
- pass inputs into recommendation logic

### Phase 4 - Recommendation Engine
- Apply safety filters
- match practice by desired outcome
- adjust for current state
- adjust for duration
- return one recommended practice
- send explanation and instructions

### Phase 5 - Completion / Feedback
- Ask whether user completed the practice
- optionally ask how they feel afterward
- log basic response data

### Phase 6 - Stability / Polish
- handle missing onboarding data
- handle skipped days
- prevent duplicate daily sends
- improve message clarity
- test edge cases

## Suggested MVP Data Needs
### User table / collection
- user id
- Telegram id
- wake-up time
- timezone
- experience level
- practice preference
- preferred session length
- safety flags
- onboarding complete

### Practice table / collection
- practice id
- name
- supports
- energetic level
- nervous system effect
- contraindications
- duration options
- short instructions
- long instructions

### Session log table / collection
- user id
- date
- desired outcome
- current state
- time available
- recommended practice
- completed yes/no
- optional reflection

## MVP Decision Rules
To keep version one simple:
- recommend only one practice per check-in
- use button-based flows as much as possible
- keep onboarding short
- keep the daily check-in to 3 questions
- avoid building too much admin tooling before the flow works

## Technical Choices To Make Soon
- language / framework
- database choice
- hosting / deployment
- scheduler approach
- how practice data is stored and edited

## Recommended Development Mindset
- ship usefulness first
- test on yourself first
- keep the first version narrow
- improve recommendation quality over time
- avoid overbuilding before the behavior is validated

## First Real Milestone
A strong first milestone would be:
- one user (Wes)
- one daily prompt
- 3 to 5 practices in the library
- working recommendation logic
- completion logging

If that works consistently, the product becomes real.

## Notes
- This MVP should be optimized for learning, not completeness.
- The first version only needs to prove that the interaction is useful and repeatable.
- If the daily loop feels genuinely supportive, there is a strong foundation to build on.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Bot Flow]]
- [[01 - Projects/Breathwork App - Telegram Bot Architecture]]
- [[01 - Projects/Breathwork App - Onboarding Prompts & Button Copy]]
- [[01 - Projects/Breathwork App - Recommendation Logic]]
