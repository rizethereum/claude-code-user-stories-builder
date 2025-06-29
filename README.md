# Claude User Story Builder (Prototype)

An intelligent user story creation system that researches real user pain points, asks smart questions, and generates actionable user stories.

## 🚀 Quick Test

```bash
# Start creating user stories
/user-story-start add financial goal tracking

# Check progress
/user-story-status

# View current session
/user-story-current
```

## 🎯 How It Works

### 1. Context Gathering
- Asks for target audience and competitors
- Remembers context for future sessions

### 2. Codebase Analysis (NEW!)
- Analyzes what features already exist
- Identifies gaps and missing functionality
- Prevents suggesting already-built features

### 3. Targeted Research
- Searches Reddit for pain points about MISSING features
- Focuses only on gaps found in codebase
- Finds unmet user needs we haven't addressed

### 4. Progressive Questions
- Asks ONE question at a time
- Next question adapts based on previous answer
- Maximum 5 questions, each building on the last
- Saves all Q&A only after completion

### 5. Direction Proposals
- Offers 5 different NEW feature directions
- Each addresses different gaps found
- User picks the best fit [1-5]

### 6. Story Generation
- Creates 3-5 detailed user stories
- Only for capabilities that DON'T exist yet
- Includes personas, goals, and acceptance criteria
- Prioritized and ready for requirements

## 📁 Structure

```
user-stories/
├── .context.json              # Remembered audience/competitors
├── .current-story            # Active session tracking
└── YYYY-MM-DD-HHMM-feature/  # Story sessions
    ├── 00-initial-input.md   # What user asked for
    ├── 01-codebase-analysis.md # What already exists
    ├── 02-research-findings.md # Pain points for gaps
    ├── 03-discovery-questions.md # Progressive questions
    ├── 04-discovery-answers.md   # User responses
    ├── 05-directions.md      # 5 new feature options
    └── 06-user-stories.md    # Final stories
```

## 🔗 Integration

After generating stories:
```
/requirements-start [chosen user story]
```

This creates a complete workflow from idea → stories → requirements → implementation.

## 🧪 Prototype Status

- ✅ Core command structure
- ✅ Context management
- ✅ Codebase analysis phase
- ✅ Research phase design
- ✅ Progressive questioning system
- ✅ Gap-focused directions
- 🚧 Web search integration
- 🚧 Story generation templates
- 🚧 Direction selection logic

## 💡 Key Innovations

Unlike traditional story writing, this tool:
1. **Knows your codebase** - Won't suggest features you already have
2. **Researches gaps only** - Focuses on what's missing
3. **Adaptive questioning** - Each question builds on the last
4. **Progressive discovery** - Not all questions predetermined
5. **Offers new directions** - Only proposes unbuilt features
6. **Maintains context** - Gets smarter over time