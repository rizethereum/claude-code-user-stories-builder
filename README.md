# Claude User Story Builder

An intelligent user story creation system for Claude Code that analyzes your codebase, researches real user pain points for missing features, asks adaptive questions, and generates actionable user stories that feed directly into requirements gathering.

## 🎯 Overview

This system transforms the user story creation process by:
- **Codebase-Aware Discovery**: Analyzes what you've already built to avoid redundancy
- **Gap-Focused Research**: Searches for pain points only about missing features
- **Progressive Questioning**: Each question adapts based on previous answers
- **Multi-Direction Exploration**: Offers 5 different approaches to solve identified gaps
- **Context Memory**: Learns your audience and competitors over time
- **Requirements-Ready Output**: Stories formatted to feed directly into technical requirements

## 🚀 Quick Start

```bash
# Start creating user stories for a new feature
/user-story-start add financial goal tracking

# Check progress and continue where you left off
/user-story-status

# View detailed current session information
/user-story-current

# List all user story sessions
/user-story-list

# End current session
/user-story-end

# Quick reminder if AI strays off course
/user-story-remind
```

## 🔄 How It Works

### Phase 1: Context Gathering
```
User: /user-story-start add financial goal tracking

AI: Tell me about the feature, problem, or improvement you're considering.
User: I want to help users track their financial goals better

AI: Building for young professionals with Mint, YNAB as reference?
User: yes
```

### Phase 2: Codebase Analysis (Autonomous)
AI analyzes your codebase to understand:
- What goal-related features already exist
- Current UI patterns and components
- Database schema and data models
- Integration points and APIs

### Phase 3: Targeted Research (Autonomous)
Based on gaps found, AI searches:
- Reddit: "financial goals frustration" (focusing on what you DON'T have)
- Twitter/X: "wish my finance app could..."
- Competitor forums: Features you're missing
- Stack Overflow: Implementation challenges

### Phase 4: Progressive Discovery Questions
```
Q1: Should users be able to track multiple financial goals simultaneously?
(Default: YES - most users have various goals like retirement, vacation, house)
User: yes

Q2: Based on multi-goal tracking, should goals have interdependencies?
(Default: YES - saving for vacation might impact house down payment timeline)
User: idk
AI: ✓ Using default: YES

[Continues adapting questions based on answers...]
```

### Phase 5: Direction Proposals
```
Based on my analysis, here are 5 directions for NEW features:

[1] Goal Timeline Visualization
    Focus: When will I achieve each goal?
    Missing: Time-based projections
    Effort: Medium | Impact: High

[2] Goal Conflict Resolution
    Focus: How do goals compete for resources?
    Missing: Trade-off analysis
    Effort: High | Impact: Very High

[3] Scenario Planning Sandbox
    Focus: What-if analysis without commitment
    Missing: Safe experimentation space
    Effort: Medium | Impact: High

[4] Intelligent Goal Recommendations
    Focus: AI-suggested goal adjustments
    Missing: Proactive guidance
    Effort: Very High | Impact: Medium

[5] Social Goal Accountability
    Focus: Share progress with trusted friends
    Missing: Social features
    Effort: Low | Impact: Medium

Which direction resonates most? [1-5]
User: 2
```

### Phase 6: User Story Generation
```
Generated 4 stories for Goal Conflict Resolution:

Story 1: Goal Priority Management
As a multi-goal saver
I want to set priority levels for my goals
So that the system knows which to protect when resources are limited

Story 2: Trade-off Visualization
As a financial planner
I want to see how delaying one goal affects others
So that I can make informed decisions about my priorities

[Continues with full stories including acceptance criteria...]
```

## 📁 Repository Structure

```
claude-user-stories/
├── commands/                     # Claude command definitions
│   ├── user-story-start.md      # Begin new story session
│   ├── user-story-status.md     # Check progress & continue
│   ├── user-story-current.md    # View active session details
│   ├── user-story-end.md        # Finalize story session
│   ├── user-story-list.md       # List all story sessions
│   └── user-story-remind.md     # Remind AI of rules
│
├── user-stories/                 # Story documentation storage
│   ├── .current-story           # Tracks active session
│   ├── .context.json            # Persistent audience/competitors
│   ├── index.md                 # Summary of all stories
│   └── YYYY-MM-DD-HHMM-name/   # Individual story sessions
│       ├── metadata.json        # Status and progress tracking
│       ├── 00-initial-input.md      # User's request
│       ├── 01-codebase-analysis.md  # What already exists
│       ├── 02-research-findings.md  # External research results
│       ├── 03-discovery-questions.md # Adaptive questions asked
│       ├── 04-discovery-answers.md   # User's responses
│       ├── 05-directions.md         # 5 proposed directions
│       └── 06-user-stories.md       # Generated stories
│
└── examples/                     # Example story session
    └── 2025-01-27-goal-tracking/

```

## 📋 Command Reference

### `/user-story-start [description]`
Begins creating user stories for a new feature or improvement.

**Example:**
```
/user-story-start implement recommendation engine
```

**Process:**
1. Collects/confirms target audience and competitors
2. Analyzes codebase for existing features
3. Researches user pain points for gaps
4. Asks 5 adaptive yes/no questions
5. Proposes 5 directions based on findings
6. Generates 3-5 stories for chosen direction

### `/user-story-status`
Shows current story session progress and continues from last point.

**Output:**
```
📝 Active User Story: recommendation-engine
Phase: Discovery Questions
Progress: 3/5 questions answered

Last: Q3: Should recommendations update in real-time? YES

Next Question:
Q4: Should users be able to dismiss recommendations?
(Default: YES - gives users control over their experience)
```

### `/user-story-current`
Displays comprehensive information about the active session.

**Shows:**
- Session details and duration
- Target audience and competitors
- Codebase findings
- Research discoveries
- All questions and answers
- Proposed directions (if reached)
- Generated stories (if complete)

### `/user-story-end`
Finalizes current story session with options.

**Options:**
1. Generate stories with current information
2. Mark as incomplete for later
3. Cancel and delete session

### `/user-story-list`
Shows all story sessions with their status.

**Output:**
```
✅ COMPLETE: recommendation-engine (5 stories, Direction: Collaborative filtering)
🔴 ACTIVE: social-features (Discovery 3/5)
⚠️ INCOMPLETE: ai-insights (Paused at directions)
```

### `/user-story-remind` (aliases: `/story-remind`, `/sr`)
Reminds AI to follow story creation rules.

**Use when AI:**
- Skips codebase analysis
- Writes all questions upfront (instead of progressive)
- Suggests existing features
- Starts writing requirements instead of stories

## 🎯 Features

### Smart Context Management
- Remembers target audience and competitors
- Reuses context across sessions
- Builds knowledge of your product over time

### Codebase-Aware Discovery
- Analyzes existing features before suggesting new ones
- Identifies gaps and opportunities
- Prevents redundant feature suggestions

### Progressive Questioning
- Each question builds on previous answers
- Adapts line of inquiry based on responses
- Maximum 5 questions to respect user time

### Multi-Direction Exploration
- Always offers 5 different approaches
- Each addresses different user needs
- Includes effort/impact analysis

### Integration with Requirements
Stories feed directly into requirements:
```
/requirements-start "Story 1: Goal Priority Management"
```

## 💡 Best Practices

### For Users
1. **Be Specific**: Clear descriptions help AI find relevant gaps
2. **Trust Defaults**: "idk" uses well-researched defaults
3. **Pick Resonant Directions**: Choose what excites you most
4. **Complete Sessions**: Finished stories are most valuable

### For Story Quality
1. **One Feature Area**: Keep sessions focused
2. **Real Problems**: Best stories address actual user pain
3. **Think Implementation**: Consider technical feasibility
4. **Link Everything**: Connect stories to requirements/PRs

## 🔧 Installation

1. Clone this repository:
```bash
git clone https://github.com/rizethereum/claude-user-stories.git
```

2. Copy commands to Claude:
```bash
cp -r commands/* ~/.claude/commands/
```

3. Create story directory:
```bash
mkdir -p user-stories
touch user-stories/.current-story
echo '{"targetAudience":"","competitors":[]}' > user-stories/.context.json
```

4. Add to `.gitignore` if needed:
```
user-stories/
!user-stories/index.md
!user-stories/.context.json
```

## 📚 Examples

### SaaS Feature
```
/user-story-start add team collaboration
# AI analyzes existing user system
# Researches collaboration pain points
# Asks about real-time needs, permissions, etc.
# Offers 5 directions (live editing, comments, permissions...)
# Generates stories for chosen direction
```

### Mobile App Enhancement
```
/user-story-start improve offline experience
# AI checks current offline capabilities
# Researches user frustrations when offline
# Asks about data criticality, sync preferences
# Proposes smart caching, conflict resolution, etc.
# Creates implementation-ready stories
```

### Developer Tool
```
/user-story-start add debugging features
# AI examines existing debug capabilities
# Finds what developers complain about
# Asks about log verbosity, breakpoints, etc.
# Suggests missing debug tools
# Outputs detailed technical stories
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Improve commands or add new ones
4. Submit a pull request

### Ideas for Contribution
- Enhance research phase with more sources
- Add story templates for common patterns
- Create story validation commands
- Build story-to-task breakdown tools
- Add estimation helpers

## 📄 License

MIT License - Feel free to use and modify for your projects.

## 🙏 Acknowledgments

Built as a companion to [claude-requirements](https://github.com/rizethereum/claude-code-requirements-builder), which handles the technical requirements phase after story creation.

---

**Remember**: Great products start with understanding what users actually need, not what we think they need!
