# Writing Skills for AI Agents

A collection of AI agent skills for writing that sounds like a real person wrote it. Built for marketers, founders, and content teams who want AI agents to produce clean, human copy — without the slop.

Works with Claude Code, Cursor, Windsurf, and any agent that supports the Agent Skills spec.

---

## Available Skills

| Skill | Description |
|---|---|
| `humanizer` | Strips AI writing patterns from any draft. Detects and removes 33 patterns including significance inflation, promotional language, vague attributions, em dash overuse, rule of three, invented specifics, and more. Rewrites for natural human voice with actual personality, or runs in plain mode for docs and briefs. |
| `linkedin-writer` | LinkedIn and short-form social rules that layer on top of humanizer. Covers voice, hooks, engagement bait, reframe constructions, clarity rules, banned vocabulary, hashtags, and a final audit pass. |

---

## Skill Detail

### `humanizer` — AI Writing Pattern Remover

Identifies and removes signs of AI-generated text based on Wikipedia's "Signs of AI writing" guide. Goes beyond pattern removal to inject actual voice and personality.

**Patterns detected and fixed (33 total):**

| Category | Patterns |
|---|---|
| Content | Significance inflation, notability emphasis, superficial -ing phrases, promotional language, vague attributions, formulaic "Challenges" sections |
| Language | AI vocabulary words, copula avoidance ("serves as"), negative parallelisms, rule of three, synonym cycling, false ranges |
| Style | Em dash overuse, excessive boldface, inline-header lists, title case headings, emojis, curly quotes |
| Communication | Chatbot artifacts, knowledge-cutoff disclaimers, sycophantic tone |
| Filler | Filler phrases, excessive hedging, generic positive conclusions |
| Structure | Dead transitions, meta commentary |
| Clarity | Invented specifics (marked [NEEDS: ...] instead), missing actors, inconsistent terms, sentences over 25 words, nouns doing a verb's job, B2B slop words, unearned voice |

**Process:**
1. Draft rewrite — all AI patterns removed, voice added
2. AI tells audit — "What makes this so obviously AI generated?"
3. Final rewrite — revised after the audit
4. Changes summary — list of everything fixed

**Plain mode:** for briefs, docs, SOPs, research summaries, and internal notes, the skill applies the patterns only and skips adding voice.

**Triggers:** "humanize this", "make this sound less AI", "remove AI patterns", "edit this copy", "clean up this draft"

### `linkedin-writer`: LinkedIn Voice and Anti-AI Rules

Tunes posts for LinkedIn and other short-form social. Apply humanizer first. Where the two conflict, linkedin-writer wins for social posts.

Covers hooks, engagement bait, hype language, reframe constructions, clarity rules, tiered banned vocabulary, formatting, hashtags, and a final audit pass. It never invents specifics: it asks for them on topic-only requests and inserts [NEEDS: ...] placeholders in drafts with gaps.

**Triggers:** "write a LinkedIn post", "edit this post", "tighten this hook", carousel copy, X/Twitter posts

---

## Installation

### Option 1: Clone and Copy

```bash
git clone https://github.com/[your-username]/[your-repo].git
cp -r writing-skills/skills/* .agents/skills/
```

### Option 2: Download a Single Folder

Use [DownGit](https://downgit.github.io) — paste the folder URL and download as ZIP.

### Option 3: Git Submodule

```bash
git submodule add https://github.com/[your-username]/[your-repo].git .agents/writing-skills
```

---

## Folder Structure

```
skills/
├── humanizer/
│   └── SKILL.md
└── linkedin-writer/
    └── SKILL.md
```

---

## Usage

Once installed, ask your agent to help with writing tasks:

```
"Humanize this draft"
→ Uses humanizer skill

"Make this sound less like AI wrote it"
→ Uses humanizer skill

"Clean up this copy"
→ Uses humanizer skill

"Write a LinkedIn post about our launch"
→ Uses linkedin-writer skill (on top of humanizer)
```

You can also invoke directly:

```
/humanizer
```

---

## Inputs Required

- Text to humanize (any format — paste directly or provide a file path)
- Intended tone, optional (formal, casual, technical — defaults to matching the input)

---

## Contributing

Found a way to improve a skill or have a new one to add? PRs and issues welcome.

See CONTRIBUTING.md for guidelines on adding or improving skills.

---

## License

MIT — Use these however you want.
