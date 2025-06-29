# View Current User Story Session

Display detailed information about the active user story creation.

## Instructions:

1. Read user-stories/.current-story
2. If no active story session:
   - Show "No active user story session"
   - Display last 3 completed story sessions
   - Exit

3. For active story session:
   - Load all files from story folder
   - Display comprehensive status
   - Show research findings if available
   - Show all questions and answers
   - Display proposed directions
   - Show generated stories if complete

## Display Format:
```
📝 Current User Story Session: [name]
⏱️ Duration: [time since start]
📊 Phase: [Context/Research/Discovery/Directions/Complete]
🎯 Progress: [current step] of [total steps]

🎯 Target Audience: [audience]
🏆 Competitors: [list]

📄 Initial Input:
[Show 00-initial-input.md content]

🔍 Research Findings:
- Pain Point: "Can't see when I'll reach my goal" (r/personalfinance)
- Request: "Need scenario planning" (Twitter)
- Complaint: "Progress bars are meaningless" (Reddit)

✅ Discovery Questions (3/5 answered):
Q1: Is timeline uncertainty the main frustration? YES
Q2: Do users need what-if scenarios? YES  
Q3: Are visual progress indicators sufficient? NO
Q4: Should this integrate with existing budgets? [PENDING]

🎯 Proposed Directions:
[1] Timeline-focused visualization
[2] Scenario planning toolkit
[3] Goal conflict resolution
[4] Predictive alerts system
[5] Comprehensive goal dashboard

Chosen: [2] Scenario planning toolkit

📚 Generated User Stories:
1. As a saver, I want to test different monthly amounts...
2. As a planner, I want to see impact of one-time deposits...

📝 Next Action:
- Continue with /user-story-status
- End session with /user-story-end
```