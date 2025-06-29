# User Story Creation Reminder

Quick correction when deviating from user story creation rules.

## Aliases:
- /user-story-remind
- /story-remind
- /sr

## Instructions:

1. Check user-stories/.current-story
2. If no active session:
   - Show "No active user story session"
   - Exit

3. Display reminder based on current context:

```
🔔 User Story Creation Reminder

You are creating user stories for: [active-session]
Current phase: [Context/Codebase/Research/Discovery/Directions/Stories]
Progress: [X/Y] steps

📋 PHASE-SPECIFIC RULES:

Phase 1 - Context:
- ✅ Collect target audience and competitors
- ✅ Check existing context first
- ✅ Save for future sessions

Phase 2 - Codebase Analysis (Autonomous):
- ✅ Analyze what already exists
- ✅ Identify gaps and missing features
- ✅ Note similar patterns
- ❌ No user interaction during analysis

Phase 3 - Research (Autonomous):
- ✅ Search for pain points about MISSING features
- ✅ Focus on gaps found in codebase
- ✅ Find unmet user needs
- ❌ Don't research existing features

Phase 4 - Progressive Discovery:
- ✅ Ask ONE question at a time
- ✅ Adapt next question based on answer
- ✅ Maximum 5 questions total
- ❌ Don't write all questions upfront
- ✅ Save questions/answers AFTER all complete

Phase 5 - Direction Proposals:
- ✅ Focus on what DOESN'T exist yet
- ✅ Propose exactly 5 directions
- ✅ Each addresses different gaps
- ✅ Wait for user to pick [1-5]

Phase 6 - Story Generation:
- ✅ Generate 3-5 stories for chosen direction
- ✅ Stories for NEW capabilities only
- ✅ Include acceptance criteria
- ✅ Order by priority

🚫 GENERAL RULES:
1. ❌ Don't skip research phase
2. ❌ Don't write requirements (use stories)
3. ❌ Don't assume pain points (research them)
4. ❌ Don't offer more than 5 directions

📍 CURRENT STATE:
- Last action: [describe last action]
- Next action: [describe next step]

Please continue with the current phase.
```

## Common Corrections:

### Skipping codebase analysis:
"Let me first analyze what features already exist..."

### Writing all questions upfront:
"Let me ask one question at a time and adapt based on your answer..."

### Researching existing features:
"Let me focus on gaps and missing features instead..."

### Proposing existing functionality:
"This already exists. Let me propose directions for what's missing..."

### Skipping research:
"Let me search for real user discussions about missing features..."

### Writing requirements instead of stories:
"Let me rephrase as user stories..."

### Too many directions:
"Let me consolidate to exactly 5 directions..."

### Missing acceptance criteria:
"Let me add testable acceptance criteria..."