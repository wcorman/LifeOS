---
type: project-note
status: active
created: 2026-04-17
updated: 2026-04-17
tags:
  - project
  - breathwork
  - bot
  - telegram
  - product-flow
---

# Breathwork App - Bot Flow

## Purpose
Define how the Telegram bot should onboard users and guide them through a simple daily recommendation flow.

## Product Principle
The bot should feel:
- simple
- supportive
- safe
- consistent
- easy to respond to

The goal is to help users actually practice, not overwhelm them with too many questions.

## Core Product Idea
Users set a preferred wake-up time, and the bot reaches out each day with a short check-in to recommend a breath practice.

The recommendation should be based on:
- current state
- desired outcome
- time available
- user profile / safety considerations

## Onboarding Flow
These questions should be asked once when the user first sets up the bot.

### 1. Wake-up time
Ask:
- What time would you like your daily breathwork check-in?

### 2. Experience level
Ask:
- Are you a beginner, intermediate, or experienced with breath practices?

### 3. Practice preference
Ask:
- Do you want guidance that feels more practical, energetic, spiritual, or balanced?

### 4. Preferred session length
Ask:
- What is your ideal default practice length?
- 2 min
- 5 min
- 10 min
- 20+ min

### 5. Safety / sensitivity profile
Ask carefully and clearly:
- Are there any conditions or sensitivities the app should account for?

Examples:
- anxiety / panic sensitivity
- dizziness / fainting history
- respiratory issues
- high blood pressure
- pregnancy
- sensitivity to breath retention or intense practices

## Daily Check-In Flow
The daily flow should stay short and easy.

### Step 1. Desired outcome
Prompt:
- What are you needing most right now?

Options:
- Energy
- Calm
- Focus
- Balance

### Step 2. Current state
Prompt:
- How do you feel right now?

Options:
- Tired
- Anxious
- Scattered
- Heavy / sluggish
- Fine, just want support

### Step 3. Time available
Prompt:
- How much time do you have?

Options:
- 2 min
- 5 min
- 10 min
- 20+ min

## Recommendation Output
Once the user answers, the bot should return:
- one recommended practice
- a short reason why it fits
- short instructions
- optional longer version or explanation

### Recommendation structure
- Practice name
- Why this fits right now
- What it supports
- How long to do it
- Simple guided steps
- Optional caution or modification if relevant

## Future Expansion Ideas
Later, the bot could also support:
- time-of-day aware recommendations
- pre-sleep recommendations
- before work / midday / after work check-ins
- streak tracking
- reflection prompts after practice
- favorites / saved practices
- adaptive recommendations based on prior responses

## Design Notes
- The daily interaction should feel lighter than filling out a form
- The bot should build trust by being clear and non-pushy
- Recommendations should feel personalized, not random
- Simplicity matters more than feature volume at the start

## Notes
- Current best version of the product starts with onboarding + a daily three-question check-in.
- This flow should later connect to a structured practice data model and recommendation logic.

## Linked
- [[01 - Projects/Breathwork App]]
- [[03 - Resources/Reference/Pranayama Effects Directory]]
- [[02 - Areas/Breathwork]]
