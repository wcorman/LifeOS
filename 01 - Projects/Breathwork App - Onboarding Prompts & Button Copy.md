---
type: project-note
status: active
created: 2026-04-17
updated: 2026-04-17
tags:
  - project
  - breathwork
  - bot
  - onboarding
  - prompts
---

# Breathwork App - Onboarding Prompts & Button Copy

## Purpose
Define the exact onboarding prompts and core button labels for the Telegram bot so the product starts to feel concrete and buildable.

## Tone Direction
The bot should feel:
- supportive
- calm
- clear
- non-pushy
- simple

Avoid:
- overly clinical tone
- overly mystical wording by default
- too much explanation at once

## Welcome Message
**Message:**
Welcome. I’m here to help you build a more consistent breathwork practice.

Each day, I can check in with you, learn what you need most, and recommend a practice that fits your current state.

Let’s start with a few quick setup questions.

**Buttons:**
- Let’s Begin

## Prompt 1 - Wake-Up Time
**Message:**
What time would you like your daily breathwork check-in?

You can type a time like `7:00 AM`.

## Prompt 2 - Experience Level
**Message:**
How familiar are you with breath practices?

**Buttons:**
- Beginner
- Intermediate
- Experienced

## Prompt 3 - Practice Preference
**Message:**
What kind of guidance do you want most?

**Buttons:**
- Practical
- Energetic
- Spiritual
- Balanced

## Prompt 4 - Preferred Session Length
**Message:**
What practice length feels most realistic for you by default?

**Buttons:**
- 2 min
- 5 min
- 10 min
- 20+ min

## Prompt 5 - Safety / Sensitivity Intro
**Message:**
A few safety questions will help me avoid recommending practices that may not be a good fit.

If none apply, you can skip.

**Buttons:**
- Continue
- Skip

## Prompt 6 - Safety / Sensitivity Options
**Message:**
Do any of these apply to you?

**Buttons:**
- Anxiety / panic sensitivity
- Dizziness / fainting history
- Respiratory issues
- High blood pressure
- Pregnancy
- Sensitive to intense breathwork
- None of these

## Onboarding Complete Message
**Message:**
You’re all set.

I’ll check in with you each day and recommend a breath practice based on what you need, how you feel, and how much time you have.

When you’re ready, we can begin with your first check-in.

**Buttons:**
- Start Today’s Check-In

# Daily Check-In Flow

## Daily Intro
**Message:**
Good morning. What are you needing most right now?

**Buttons:**
- Energy
- Calm
- Focus
- Balance

## Current State Prompt
**Message:**
How do you feel right now?

**Buttons:**
- Tired
- Anxious
- Scattered
- Heavy / sluggish
- Fine, just want support

## Time Available Prompt
**Message:**
How much time do you have right now?

**Buttons:**
- 2 min
- 5 min
- 10 min
- 20+ min

# Recommendation Output Copy

## Recommendation Intro
**Message template:**
Here’s a practice that fits what you shared.

## Recommendation Body Template
**Message template:**
**Recommended practice:** {practice_name}

**Why this fits:** {reason}

**Suggested duration:** {duration}

**How to do it:**
{short_instructions}

{optional_note}

**Buttons:**
- I’ll Do This
- Show Me Another Option
- Tell Me More

## Completion Follow-Up
**Message:**
Did you do the practice?

**Buttons:**
- Yes
- Not Yet
- Skip

## If Yes
**Message:**
Beautiful. Nice work showing up.

Would you like to check in on how you feel now?

**Buttons:**
- Yes
- Not Now

## If Not Yet
**Message:**
No problem. You can come back to it when you’re ready.

**Buttons:**
- Remind Me Later
- Done

## If Skip
**Message:**
That’s okay. We’ll keep it simple and try again next time.

# Optional Reflection Prompt
**Message:**
How do you feel now?

**Buttons:**
- More calm
- More clear
- More energized
- About the same
- Hard to tell

## Notes
- The prompts should stay lightweight and easy to answer.
- Buttons are preferable to free-text whenever possible.
- The onboarding should feel short enough that users actually finish it.
- Language can later be tuned more toward practical, energetic, or spiritual styles depending on user preference.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Bot Flow]]
- [[01 - Projects/Breathwork App - Telegram Bot Architecture]]
