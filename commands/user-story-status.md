# Check User Story Status

Show current user story session progress and continue.

## Instructions:

1. Read user-stories/.current-story
2. If no active session:
   - Show "No active user story session"
   - Suggest /user-story-start or /user-story-list
   - Exit

3. If active session exists:
   - Read metadata.json for current phase
   - Show brief status summary
   - Continue from last point:

### Phase Continuations:

**If in Context Phase:**
- Complete audience/competitor collection
- Move to Research Phase

**If in Research Phase:**
- Show "Researching user pain points..."
- Complete autonomous research
- Move to Discovery Questions

**If in Discovery Phase:**
- Show last answered question
- Continue with next question
- After all answered, move to Directions

**If in Directions Phase:**
- Show 5 proposed directions
- Wait for user to pick [1-5]
- Generate stories for chosen direction

**If Complete:**
- Show generated stories
- Suggest next steps

## Status Display:
```
📝 Active User Story: [name]
Phase: Discovery Questions
Progress: 3/5 questions answered

Last: Q3: Are visual indicators sufficient? NO

Next Question:
Q4: Should this integrate with existing budgets?
(Default: YES - users expect unified experience)
```