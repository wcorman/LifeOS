---
type: project-note
status: active
created: 2026-04-17
updated: 2026-04-17
tags:
  - project
  - breathwork
  - recommendation-logic
  - bot
---

# Breathwork App - Recommendation Logic

## Purpose
Define how the bot should choose an appropriate breath practice based on user input, stored profile information, and safety considerations.

## Core Principle
The recommendation engine should feel:
- helpful
- simple
- safe
- understandable
- not overly mysterious

It should recommend one strong fit, not overwhelm the user with too many options.

## Inputs The Bot Uses

### Daily inputs
- desired outcome
- current state
- time available

### Onboarding/profile inputs
- wake-up time
- experience level
- practice preference
- preferred session length
- safety / sensitivity profile

## Daily Input Examples
### Desired outcome
- energy
- calm
- focus
- balance

### Current state
- tired
- anxious
- scattered
- heavy / sluggish
- fine, just want support

### Time available
- 2 min
- 5 min
- 10 min
- 20+ min

## Core Recommendation Process

### Step 1. Safety filter
Before anything else, remove practices that conflict with the user's contraindications or sensitivities.

Examples:
- avoid intense energizing practices for some anxiety / panic profiles
- avoid retention-heavy or forceful practices for certain users
- avoid practices that exceed the user's experience level if the instructions are more advanced

### Step 2. Match desired outcome
Filter toward practices whose `supports` field matches the user's desired outcome.

Examples:
- energy -> energizing practices
- calm -> calming practices
- focus -> balancing or clarifying practices
- balance -> balancing practices

### Step 3. Adjust for current state
Current state should shape which recommendation is safest and smartest.

Examples:
- user wants energy + currently tired -> energizing may fit well
- user wants energy + currently anxious -> avoid highly stimulating choices, recommend balancing or gently energizing
- user wants calm + currently heavy / sluggish -> choose calming without making them more shut down
- user wants focus + currently scattered -> balancing or mildly calming may fit better than strong stimulation

### Step 4. Match time available
Prefer practices whose default or available durations match the user's available time.

Examples:
- 2 min -> choose only very accessible, low-friction practices
- 5 min -> core daily-use practices
- 10 min -> fuller guided options
- 20+ min -> deeper versions or more immersive practices

### Step 5. Match experience level
When multiple practices fit, favor the one that better matches the user's experience level.

Examples:
- beginners -> simpler, safer, easier to explain
- experienced users -> can receive more nuanced or demanding practices

### Step 6. Apply preference flavoring
If the user prefers practical, energetic, spiritual, or balanced framing, shape the recommendation language accordingly.

This affects presentation more than the underlying practice selection.

## Simple Recommendation Heuristics

### If user wants calm
Prefer:
- significantly calming
- moderately calming
- balancing

Avoid:
- highly stimulating practices unless specifically appropriate

### If user wants energy
Prefer:
- mildly energizing
- moderately energizing
- significantly energizing

But if current state is anxious:
- first prefer balancing or gently energizing

### If user wants focus
Prefer:
- balancing
- mildly energizing
- practices with sattvic / centering qualities

### If user wants balance
Prefer:
- balancing
- practices associated with steadiness and regulation

## Example Recommendation Logic Pattern

### Example 1
Input:
- desired outcome: energy
- current state: tired
- time: 5 min
- user: intermediate

Possible fit:
- mildly or moderately energizing breath

### Example 2
Input:
- desired outcome: energy
- current state: anxious
- time: 5 min
- panic sensitivity: yes

Better fit:
- balancing or gently energizing practice
- avoid the strongest stimulating options

### Example 3
Input:
- desired outcome: calm
- current state: scattered
- time: 2 min

Better fit:
- short, balancing or mildly calming practice
- simple instructions, low barrier

## Recommendation Output Format
A useful output should include:
- practice name
- one-sentence reason
- expected effect
- duration
- short instructions
- optional note or caution

### Example output shape
- Recommended practice: Alternate Nostril Breathing
- Why: You asked for balance and focus, and this practice supports steadiness without overstimulating.
- Duration: 5 minutes
- Instructions: ...
- Note: Keep the breath gentle and unforced.

## Future Recommendation Improvements
Later, the logic could also include:
- time-of-day effects
- practice rotation so users do not always get the same recommendation
- previous user feedback
- practices the user liked or skipped
- streak-aware suggestions
- stronger energetic / spiritual logic layers

## Notes
- Recommendation quality depends on the quality of the practice metadata.
- The system should favor safe usefulness over false precision.
- Simplicity matters more than perfect complexity at the start.

## Linked
- [[01 - Projects/Breathwork App]]
- [[01 - Projects/Breathwork App - Bot Flow]]
- [[01 - Projects/Breathwork App - Practice Data Model]]
- [[03 - Resources/Reference/Pranayama Effects Directory]]
