# Start User Story Creation

Begin creating user stories for: $ARGUMENTS

## Enhanced Flow:

### Phase 1: Initial Setup & Context Check
1. Create timestamp folder: user-stories/YYYY-MM-DD-HHMM-[slug]
2. Extract feature/problem from $ARGUMENTS
3. Check .context.json for existing audience/competitors
4. If context exists, ask: "Building for [audience] with [competitors] as reference. Correct? (yes/no/update)"
5. If no context or update needed, ask for:
   - Target audience
   - Known competitors
6. Save context and initial input to 00-initial-input.md

### Phase 2: Codebase Analysis (Autonomous)
7. Use mcp__repomap__analyze_codebase (if available) to understand overall structure
8. Search for existing features related to $ARGUMENTS:
   - Use mcp__RepoPrompt__search (if available) to find relevant files
   - Identify what already exists
   - Note similar features and patterns
   - Check for partial implementations
9. Document findings in 01-codebase-analysis.md:
   - Existing related features
   - Similar patterns in codebase
   - Potential integration points
   - What's NOT built yet

### Phase 3: Targeted Research Phase (Autonomous)
10. Based on what's NOT in codebase, search for user needs:
    - Reddit: "[missing feature] frustration"
    - Focus on gaps identified in codebase analysis
    - Search competitor discussions for features we lack
    - Find pain points we haven't addressed
11. Document findings in 02-research-findings.md and present to user your findings in summary form including:
    - Pain points for missing features
    - User language about gaps
    - Competitor advantages we lack
    - Unmet needs in our space

### Phase 4: Progressive Discovery Questions
12. Ask the MOST important yes/no question based on research. always provide a idk default "smart" option
13. Based on the answer, determine the next most relevant question
14. Continue for up to 5 questions total, each informed by previous answers
15. After ALL questions complete, save to:
    - 03-discovery-questions.md (all questions with defaults)
    - 04-discovery-answers.md (all answers)

### Phase 5: Direction Proposals
16. Based on codebase gaps, research, and answers, propose 5 directions:
    - Each addresses different unmet needs
    - Focus on what we DON'T have yet
    - Different problem angles
    - MVP vs comprehensive solutions
    - Quick wins vs transformative changes
17. Write directions to 05-directions.md and present the full details to the user
18. Ask user to pick which one that resonates the most [1-5]

### Phase 6: User Story Generation
19. For chosen direction, generate 3-5 user stories:
    - Epic name and description
    - Individual stories with format:
      - As a [persona]
      - I want [capability]
      - So that [value]
      - Acceptance Criteria
    - Priority order with rationale
20. Save to 06-user-stories.md
21. Update .context.json with commonPainPoints and gaps found

## Initial Prompt:
```
Tell me about the feature, problem, or improvement you're considering.

Optional details:
- Target audience (e.g., "young professionals")
- Competitors (e.g., "like Notion but simpler")
- Previous context (e.g., "continue from story #3")
```

## Important Rules:
- ALWAYS analyze codebase before external research
- Focus on what DOESN'T exist yet
- Questions must be progressive - each builds on previous answer
- Don't write all questions at once - adapt based on responses
- Use actual user language from research
- Present directions that address gaps, not existing features
- Save questions/answers ONLY after all are complete

## Metadata Structure:
```json
{
  "id": "feature-slug",
  "started": "ISO-8601-timestamp",
  "lastUpdated": "ISO-8601-timestamp",
  "status": "active",
  "phase": "context|codebase|research|discovery|directions|complete",
  "targetAudience": "from context",
  "competitors": ["from context"],
  "existingFeatures": ["found in codebase"],
  "gaps": ["what's missing"],
  "progress": {
    "discovery": { "answered": 0, "total": 5 },
    "currentDirection": null
  },
  "painPointsDiscovered": ["from research"],
  "chosenDirection": 0
}
```

## Phase Transitions:
- After each phase, announce: "Phase complete. Starting [next phase]..."
- Save all work before moving to next phase
- User can check progress anytime with /user-story-status