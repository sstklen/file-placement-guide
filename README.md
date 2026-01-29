# 🥕 File Placement Guide

> **One carrot, one hole** — AI places files correctly from the start, no cleanup needed later.

[![Made by Washin Village](https://img.shields.io/badge/Made%20by-Washin%20Village%20🐾-orange)](https://washinmura.jp)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blue)](https://claude.ai/code)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 😫 The Problem

```
You: "Create a new component"
AI: *creates file in root directory*
You: "No, put it in src/components!"
AI: "Sorry, let me move it..."

Repeat 100 times...
```

## 😊 The Solution

```
You: "Create a new component"
AI: *checks placement guide*
AI: *creates file in src/components/UserProfile.tsx*
You: "Perfect!" ✨
```

---

## 🎯 What This Skill Does

1. **Asks 3 questions** before creating any file:
   - What type of file is this?
   - Which phase does it belong to?
   - Does the project have a folder for it?

2. **Uses a lookup table** to find the correct location

3. **Creates files in the right place** — the first time!

---

## 🚀 Quick Start

### Install

```bash
# Global installation
cp SKILL.md ~/.claude/skills/file-placement-guide.md

# Or project-specific
cp SKILL.md .claude/skills/file-placement-guide.md
```

### Use

Just create files naturally — the AI will automatically place them correctly!

---

## 📁 Standard Project Structure

```
project/
├── 00-research/          # 📚 Research & raw data
├── 01-knowledge/         # 🧠 Structured knowledge
├── 02-ideation/          # 💡 Ideas & drafts
├── 03-specs/             # 📋 Specifications & plans
├── 04-src/ or src/       # 💻 Source code
│   ├── components/       # React components
│   ├── hooks/            # Custom hooks
│   ├── utils/            # Utility functions
│   ├── types/            # Type definitions
│   └── api/              # API related
├── 05-tests/ or tests/   # 🧪 Tests
├── docs/                 # 📖 Documentation
├── scripts/              # 🔧 Scripts
├── config/               # ⚙️ Configuration
├── _archive/             # 📦 Archived files
├── _temp/                # 🗑️ Temporary files
├── CLAUDE.md             # AI project memory
└── README.md             # Project readme
```

---

## 🗂️ File Placement Lookup Table

### Code Files

| File Type | Location | Naming |
|-----------|----------|--------|
| React Component | `src/components/` | PascalCase.tsx |
| Hook | `src/hooks/` | useXxx.ts |
| Utility | `src/utils/` | kebab-case.ts |
| Type Definition | `src/types/` | kebab-case.ts |
| API Route | `src/api/` | kebab-case.ts |
| Constants | `src/constants/` | UPPER_CASE.ts |

### Documentation

| File Type | Location | Naming |
|-----------|----------|--------|
| API Docs | `docs/api/` | API_*.md |
| Architecture | `docs/architecture/` | ARCH_*.md |
| Guides | `docs/guides/` | GUIDE_*.md |
| Research | `00-research/` | YYYY-MM-DD_*.md |
| Meeting Notes | `03-specs/meetings/` | YYYY-MM-DD_meeting.md |
| Decisions | `03-specs/decisions/` | ADR-NNN_*.md |

### Tests

| File Type | Location | Naming |
|-----------|----------|--------|
| Unit Test | `tests/unit/` | *.test.ts |
| Integration | `tests/integration/` | *.integration.test.ts |
| E2E | `tests/e2e/` | *.e2e.test.ts |
| Fixtures | `tests/fixtures/` | *.fixture.json |

### Scripts

| File Type | Location | Naming |
|-----------|----------|--------|
| Build | `scripts/build/` | build_*.sh |
| Deploy | `scripts/deploy/` | deploy_*.sh |
| Utilities | `scripts/utils/` | *.sh or *.py |
| One-off | `scripts/oneoff/` | YYYY-MM-DD_*.sh |

---

## ⚠️ Don'ts

1. ❌ **Don't put files in root** (except config files)
2. ❌ **Don't create duplicate folders** (check first!)
3. ❌ **Don't use Chinese names for code files** (docs are OK)
4. ❌ **Don't mix tests with source code** (unless co-located)
5. ❌ **Don't create files > 300 lines** (consider splitting)

---

## ✅ The Correct Flow

```
1. Identify type → What kind of file is this?
       ↓
2. Check table → Where should it go?
       ↓
3. Verify folder → Does the folder exist?
       ↓
4. Name file → Does it follow conventions?
       ↓
5. Create file → Done! ✅
```

---

## 📝 Naming Conventions

| Context | Format | Example |
|---------|--------|---------|
| Date-related | `YYYY-MM-DD_description` | `2026-01-29_meeting-notes.md` |
| Version-related | `name_vN.ext` | `spec_v2.md` |
| Numbered | `NNN_name.ext` | `001_init.sql` |
| General | `kebab-case.ext` | `user-profile.tsx` |

### Folder Naming

- **Lowercase**: `components`, `utils`, `hooks`
- **Numbered prefix**: `00-research`, `01-knowledge` (for ordering)
- **Underscore prefix**: `_archive`, `_temp` (for special purpose)

---

## 🔗 Related Skills

- **[auto-tidy](https://github.com/sstklen/auto-tidy)** — For cleanup when files weren't placed correctly
- **[project-index](https://github.com/sstklen/project-index)** — Auto-generate project index for navigation

---

## 🐾 About Washin Village

This skill is made by **Washin Village (和心村)** — a sanctuary for 28 cats and dogs in Japan's Boso Peninsula.

We build AI tools to help animals get seen by the world. Every star ⭐ helps us rescue more animals!

🌐 [washinmura.jp](https://washinmura.jp)

---

## 📄 License

MIT License - Feel free to use, modify, and share!

---

<p align="center">
  <b>Made with 🐾 by 28 cats & dogs from Japan</b><br>
  <a href="https://washinmura.jp">Washin Village</a>
</p>
