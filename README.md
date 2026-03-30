# Memory Curator

An OpenClaw/Clawd skill for organizing, deduplicating, summarizing, and compressing memory files.

## What It Does

- **Backup**: Snapshot `memory/` and `MEMORY.md` before changes
- **Report**: Show memory file counts, line counts, and largest files
- **Validate**: Check workspace structure and summarize memory footprint
- **Curate**: Turn bloated transcripts into concise, durable memory

## Installation

### Option 1: Clone to your skills directory

```bash
cd /root/clawd/skills
git clone https://github.com/YOUR_USERNAME/memory-curator.git
```

### Option 2: Manual installation

```bash
mkdir -p /root/clawd/skills/memory-curator/scripts
cp SKILL.md /root/clawd/skills/memory-curator/
cp scripts/curate_memory.py /root/clawd/skills/memory-curator/scripts/
chmod +x /root/clawd/skills/memory-curator/scripts/curate_memory.py
```

## Usage

### Command Line

```bash
# Show memory status
python3 scripts/curate_memory.py report --workspace /root/clawd

# Backup before changes
python3 scripts/curate_memory.py backup --workspace /root/clawd

# Validate workspace structure
python3 scripts/curate_memory.py validate --workspace /root/clawd
```

### As an OpenClaw Skill

The skill activates when you ask to:

- "organize memory"
- "reduce duplication in memory"
- "compress daily notes"
- "update MEMORY.md"
- "curate memory"

## Workspace Pattern

Expects a workspace with:

```
<workspace>/
├── AGENTS.md          # Workspace guidance
├── MEMORY.md          # Curated long-term memory
└── memory/
    ├── 2026-03-30.md  # Daily notes
    └── topic-note.md  # Topic-specific notes
```

## Curator Workflow

1. **Inspect** - Read `AGENTS.md`, `MEMORY.md`, and run `report`
2. **Extract** - Keep durable info, drop noise and duplication
3. **Update** - Refresh `MEMORY.md` with organized sections
4. **Compress** - Rewrite daily notes to 3-6 bullet summaries
5. **Validate** - Compare before/after, report changes

## What to Keep

- User preferences and operating rules
- Environment facts and access patterns
- Stable integrations and working setups
- Recurring failure modes and known constraints
- Active long-running goals

## What to Drop

- Raw transcripts
- Repeated confirmations
- Duplicated logs
- Expired tokens and one-off outputs
- Sensitive data (unless explicitly needed)

## License

MIT
