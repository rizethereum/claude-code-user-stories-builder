# End User Story Session

Finalize the current user story creation session.

## Instructions:

1. Read user-stories/.current-story
2. If no active session:
   - Show "No active user story session to end"
   - Exit

3. Show current status and ask user intent:
   ```
   ⚠️ Ending user story session: [name]
   Current phase: [phase] ([X/Y] complete)
   
   What would you like to do?
   1. Generate stories with current information
   2. Mark as incomplete for later
   3. Cancel and delete
   ```

4. Based on choice:

### Option 1: Generate Stories
- If direction chosen, generate stories for that direction
- If no direction chosen, use most popular from research
- Create 05-user-stories.md
- Update metadata status to "complete"
- Update .context.json with new pain points discovered

### Option 2: Mark Incomplete  
- Update metadata status to "incomplete"
- Add "lastUpdated" timestamp
- Create summary of progress
- Note what's still needed

### Option 3: Cancel
- Confirm deletion
- Remove story folder
- Clear .current-story

## Final Story Format:
```markdown
# User Stories: [Feature Name]

Generated: [timestamp]
Target Audience: [audience]
Chosen Direction: [direction name]

## Epic: [Epic Name]
[Epic description based on chosen direction]

### Story 1: [Story Title]
**As a** [persona discovered from research]
**I want** [specific capability]
**So that** [emotional/business value]

**Acceptance Criteria:**
- [ ] [Specific testable criterion]
- [ ] [Another criterion]
- [ ] [Edge case handling]

**Priority:** High
**Effort:** Medium
**Rationale:** [Why this story first]

### Story 2: [Story Title]
[Similar format...]

## Implementation Order:
1. Story 1 - Core functionality
2. Story 3 - Enhanced experience
3. Story 2 - Power user feature

## Next Steps:
- Pick a story and run: /requirements-start [story description]
- Review with team for feedback
- Add stories to backlog
```

5. Clear .current-story
6. Update user-stories/index.md