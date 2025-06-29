# List All User Story Sessions

Display all user story sessions with their status and summaries.

## Instructions:

1. Check user-stories/.current-story for active session
2. List all folders in user-stories/ directory
3. For each story folder:
   - Read metadata.json
   - Extract key information
   - Format for display

4. Sort by:
   - Active first (if any)
   - Then by status: complete, incomplete  
   - Then by date (newest first)

## Display Format:
```
📚 User Story Sessions

🔴 ACTIVE: goal-tracking
   Phase: Discovery (3/5) | Started: 30m ago
   Audience: Young professionals
   Next: Q4 about budget integration

✅ COMPLETE:
2025-01-26-notification-system
   Status: 5 stories generated | Direction: Predictive Alerts
   Audience: Power users | Competitors: Notion, Todoist
   Epic: Smart notification engine
   
2025-01-25-collaboration-features
   Status: 4 stories generated | Direction: Real-time Sync
   Audience: Team users | Competitors: Slack, Teams
   Implemented: PR #234

⚠️ INCOMPLETE:
2025-01-24-ai-insights
   Status: Paused at Directions | Last: 2 days ago
   Audience: Data analysts | Research: Complete
   5 directions proposed, awaiting selection

📈 Statistics:
- Total: 4 sessions
- Complete: 2 (avg 4.5 stories)
- Active: 1
- Incomplete: 1
- Most common pain point: "Timeline uncertainty"
```

## Additional Features:

1. Show context evolution:
   - How audience understanding improved
   - Common pain points discovered
   - Patterns across sessions

2. Highlight connections:
   - Stories that led to requirements
   - Requirements that got implemented
   - Success metrics if available

3. Quick actions:
   - "Resume incomplete: /user-story-status"
   - "Start new: /user-story-start [description]"
   - "View details: /user-story-show [id]"