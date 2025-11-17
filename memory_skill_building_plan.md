# Memory Skill Building Plan
## Complete Topic-based Dynamic Memory System

**Status**: Planning (2025-11-18)
**Branch**: feature/complete-topic-memory (to be created)
**Implementation**: Tomorrow

---

## Vision

Build a **completely automated, topic-based dynamic memory system** for Cursor + Claude Code that:
- 🔄 **Auto-detects** relevant topics from user input
- 🧠 **Semantically searches** all project files in context
- 💾 **Auto-updates** memory with new insights after each session
- 🔗 **Auto-discovers** connections between topics
- ✅ **Requires user approval** only for final memory updates

---

## Core Architecture

### **3-Layer Automation**

#### Layer 1: Dynamic Topic Loading
```
User message → Auto-detect topics → Load relevant context only
Examples:
- "Ohouse AI portfolio" → loads ohouse_ai.json + related files
- "Brand 2.0 case" → loads brand_2.0.json
- Multiple topics → loads all + checks connections
```

#### Layer 2: Semantic Search & Context Retrieval
```
During conversation:
- Auto-detect keywords/concepts
- Search all .md files for related content
- Pull up relevant sections automatically
- Propose: "You mentioned this before in [file]. Relevant?"
```

#### Layer 3: Auto Memory Update
```
Session end:
- Analyze conversation for new insights
- Extract: topic, insight, source files
- Propose update with user review
- User approves → auto-update JSON + git commit
```

---

## File Structure

```
.cursor/skills/project-memory/
├── SKILL.md                           # Claude Skill definition
├── topics/                            # Dynamic topic contexts
│   ├── brand_2.0.json
│   ├── ohouse_ai.json
│   ├── visual_search.json
│   ├── ai_workshop.json
│   ├── ux_writing.json
│   ├── ai_native_team_building.json
│   └── pd_in_ai.json
├── topic_index.json                   # All topics registry
├── connections.json                   # Topic relationships
├── memory_update_log.json              # History of updates
└── README.md                          # Usage guide
```

---

## Topic JSON Structure

Each topic file contains:

```json
{
  "topic": "Topic Name",
  "category": "Portfolio|Work",
  "status": "active|archived",
  "last_updated": "2025-11-18T10:30:00",

  "versions": [
    {
      "version": "v7",
      "date": "2025-11-18",
      "key_insight": "Core breakthrough or pivot",
      "files": ["file paths"]
    }
  ],

  "core_concepts": ["concept1", "concept2"],
  "source_files": ["path1.md", "path2.md"],
  "related_topics": ["topic1", "topic2"],
  "triggers": ["keyword1", "keyword2"],

  "insights": [
    {
      "insight": "What was learned",
      "date": "2025-11-18",
      "source_file": "file path",
      "related_concepts": ["concept"]
    }
  ]
}
```

---

## Implementation Plan

### Phase 1: Setup & Initial Topics (tomorrow morning)

1. **Create branch**: `git checkout -b feature/complete-topic-memory`

2. **Generate initial topics from MEMORY.md**:
   - Extract each project/topic from MEMORY.md
   - Convert to individual JSON files in `topics/`
   - Maintain version history for each topic

3. **Create topic_index.json**:
   - Auto-generated registry of all topics
   - Metadata: status, category, last_updated

4. **Create connections.json**:
   - Extract from MEMORY.md "Connecting Insights Across Projects" section
   - Map relationships between topics
   - Identify shared concepts

### Phase 2: SKILL.md Implementation (tomorrow afternoon)

5. **Auto-detection logic**:
   - Keyword matching for topic detection
   - LLM-based intent analysis (if keyword matching unsure)
   - Multi-topic handling

6. **Semantic search function**:
   - Search all source_files for relevance
   - Return ranked results with snippets
   - Auto-propose context loading

7. **Memory update protocol**:
   - Conversation analysis for new insights
   - Insight extraction (what changed?)
   - User approval flow
   - Auto JSON update + git commit

### Phase 3: Testing & Refinement (if time)

8. **Test scenarios**:
   ```
   ✓ Single topic load: "Ohouse AI v7 near-term?"
   ✓ Multi-topic: "How do Brand 2.0 and Ohouse AI connect?"
   ✓ Semantic search: "design phase vs execution phase"
   ✓ New insight: Auto-detect + propose update
   ✓ Version tracking: "Show AI_native_team_building evolution"
   ```

9. **Edge cases**:
   - New topics (auto-detection + ask before adding)
   - File path changes (auto-update references)
   - Deleted topics (archive instead of delete)

---

## Key Automation Features

### 1. Auto Topic Detection
```
Logic:
- Match user message against topic triggers
- If multiple topics: load all + show connections
- If unsure: ask user or use LLM classification
```

### 2. Semantic Search (Within Session)
```
During conversation:
- Key terms → search all .md files
- Return top 3 matches with relevance score
- Propose: "Found relevant discussion in [file]. Load?"
```

### 3. Auto Memory Update (Session End)
```
Conversation transcript → LLM analysis
↓
Extract:
- New insights (what changed?)
- Affected topics
- Source files mentioned
↓
Propose update:
"New insight for ohouse_ai:
- Design phase ≠ Execution phase separation
- Related to: contractor management strategy
- Source: Daily_note/11182025.md

Add to ohouse_ai.json? [Yes] [Edit] [No]"

If Yes:
- Update JSON
- git add + commit
```

### 4. Auto Connection Discovery
```
When updating a topic:
- Check: Do other topics share concepts?
- Example: "Design Leadership" appears in both
           brand_2.0 and ai_native_team_building
- Propose: Add to connections.json
```

### 5. New Topic Detection
```
When new files created:
- Scan for topic keywords
- If new topic detected:
  "New topic 'Design_System_v2' detected.
   Create topics/design_system_v2.json?
   [Yes - Create & configure] [No]"
- User configures trigger keywords, concepts, etc.
```

---

## Comparison: Before vs After

| Aspect | Current MEMORY.md | New Dynamic System |
|--------|------------------|-------------------|
| **Memory Load** | Manual (full file) | Auto-detect → relevant only |
| **Context Finding** | Manual search | Semantic search (auto) |
| **Insight Saving** | Manual edit | Auto-extract → approve → save |
| **Topic Updates** | Manual version management | Auto-version + timestamp |
| **Cross-topic Links** | Manual maintenance | Auto-discovery + proposal |
| **New Topics** | Manual documentation | Auto-detect + ask |
| **Session Memory** | No session tracking | Conversation → insights logged |

---

## Expected Workflow (After Implementation)

### Typical Session

```
[Session Start]
Me: "Working on Ohouse AI portfolio"
→ Auto-detects: ohouse_ai topic
→ Loads: ohouse_ai.json + Daily_note/11182025.md + related files
→ Shows: "Context loaded: Ohouse AI v7 near-term implementation"

[During Work]
Me: "How to separate design from execution phase?"
→ Auto-searches: "design phase", "execution", "contractor"
→ Finds: Daily_note section 4
→ Proposes: "Found relevant discussion from 11/18. Load?"

[Work Session]
Me: [Writing portfolio case study]
System: [Tracking conversation]

[Session End]
System analyzes conversation:
- Detected new insight: "Design phase needs clear success metrics"
- Affected topic: ohouse_ai
- Related files: Daily_note/11182025.md, Onboarding.md

System proposes:
"New insight for ohouse_ai:
'Design phase success = user confidence & conversion'
Related: business metrics & UX validation"

Me: [Approve/Edit]
→ Auto-update: ohouse_ai.json
→ Auto-commit: git commit -m "Update ohouse_ai: design phase metrics insight"
```

---

## Implementation Notes

### What's NOT Phase 2
- ❌ Vector database (not needed - LLM does semantic analysis)
- ❌ Background daemon (runs per-session)
- ❌ Complex caching (simple JSON files)

### What's Built In
- ✅ All automation via LLM (Claude)
- ✅ Simple file I/O (Python standard)
- ✅ Git integration (Bash)
- ✅ User approval (interactive prompts)

### Cursor/Claude Code Integration
- Uses: MCP server pattern or SKILL.md execution
- Persists: .cursor/skills/project-memory/ (always available)
- Updates: Auto-commit via git after each session

---

## Success Criteria

When complete:
1. ✅ Auto-loads only relevant topics (not entire MEMORY.md)
2. ✅ Semantic search finds related content in real-time
3. ✅ New insights auto-extracted and proposed
4. ✅ User can approve/edit before saving
5. ✅ Auto-git commits after memory updates
6. ✅ Handles new topics gracefully
7. ✅ Tracks topic connections automatically
8. ✅ Version history preserved & accessible

---

## Timeline

**Tomorrow**:
- Morning (2-3 hours): Setup + Initial topics + topic_index + connections
- Afternoon (2-3 hours): SKILL.md implementation
- Optional evening: Testing & refinement

**Total**: ~4-6 hours for complete implementation

---

## Questions Answered

**Why complete automation?**
- ✅ No "Phase 1/2" delays - all features at once
- ✅ Cursor + Claude Code fully capable
- ✅ User approval provides control, not bottleneck

**Why topic-based over persona-based?**
- ✅ Topics are dynamic (keep adding projects)
- ✅ Personas are fixed (designer, dad, etc.)
- ✅ Current need is project context switching

**Why not Vector DB?**
- ✅ LLM can analyze semantics directly
- ✅ Simpler, fewer dependencies
- ✅ Faster for small-to-medium document sets

---

## Related Files

- **MEMORY.md** - High-level summaries (unchanged, kept as reference)
- **Daily_note/11182025.md** - Recent discovery (becomes ohouse_ai insights)
- **Portfolio/** - All source files (scanned by semantic search)
- **Work_Build_ai_native/** - All source files (scanned by semantic search)

---

**Created**: 2025-11-18
**Author**: Ilwon + Claude Code
**Status**: Ready for implementation tomorrow
