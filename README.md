# asher-grad-essays

A Claude Code / Amp skill that encodes the frameworks, techniques, and principles from Donald Asher's *Graduate Admissions Essays* (4th Edition). Use it to get expert guidance on writing grad school application essays, choosing programs, managing deadlines, securing funding, and coaching letters of recommendation.

---

## Attribution

This skill is a transformative study aid derived from:

> **Graduate Admissions Essays: Write Your Way into the Graduate School of Your Choice (4th Edition)**
> Donald Asher
> Ten Speed Press, 2012
> ISBN: 978-1-60774-322-4

This repository summarizes Asher's named frameworks, principles, and techniques for personal and educational use. It does not reproduce the book's sample essays or substantial verbatim passages. **Buy the book** — it contains 50+ annotated real application essays that no summary can replace: [Ten Speed Press](https://www.penguinrandomhouse.com/books/210671/graduate-admissions-essays-fourth-edition-by-donald-asher/) or your preferred bookseller.

---

## What This Skill Does

Once installed, you can ask your agent:

```
/asher-grad-essays
```

and it will load Asher's core frameworks — the Application Sequence, RTGDQ, the Academizer, the Essay Hall of Shame, funding counterintuitions, the Law of Descending Prestige, and more — ready to apply to your specific situation.

Ask follow-up questions like:

- "How should I open my essay?"
- "What's wrong with my motivation for going to grad school?"
- "How do I choose between these three programs?"
- "What should I give my letter writers?"
- "Review this paragraph — does it belong in the Hall of Shame?"
- "What does Asher say about negotiating financial aid?"

The skill loads chapter files on demand (they are not all loaded at once), so token usage is proportional to what you actually ask about.

---

## Installation

### Claude Code

Copy the skill directory into your global Claude Code skills folder:

```bash
git clone https://github.com/avatar-lavventura/asher-grad-essays.git
cp -r asher-grad-essays ~/.claude/skills/asher-grad-essays
```

Then invoke with `/asher-grad-essays` in any Claude Code session.

### Amp (global)

```bash
git clone https://github.com/avatar-lavventura/asher-grad-essays.git
cp -r asher-grad-essays ~/.config/agents/skills/asher-grad-essays
```

### Amp (project-local)

```bash
git clone https://github.com/avatar-lavventura/asher-grad-essays.git
cp -r asher-grad-essays .agents/skills/asher-grad-essays
```

### Update

```bash
cd ~/.claude/skills/asher-grad-essays
git pull
```

Or re-run the cp command after pulling the repo.

---

## Usage Examples

### Get core frameworks

```
/asher-grad-essays
```

Loads RTGDQ, the Academizer, the Essay Hall of Shame, the Application Sequence, and the funding counterintuitions.

### Get advice on a specific topic

```
/asher-grad-essays funding
/asher-grad-essays letters of recommendation
/asher-grad-essays opening paragraph
/asher-grad-essays school selection
```

### Dive into a specific chapter

```
/asher-grad-essays ch05
/asher-grad-essays ch07
/asher-grad-essays ch09
```

### Review your actual essay file

Pass your essay as an argument and get a full structured critique:

```
/asher-grad-essays check-my-essay my-statement.pdf
/asher-grad-essays check-my-essay statement-of-purpose.docx
/asher-grad-essays check-my-essay draft.txt
```

The skill extracts the text, asks you for the prompt if it is not in the file, then produces a 9-section report:

1. RTGDQ — does it answer the question?
2. Opening type classification (epiphany, self-definition, generic, etc.)
3. Essay Hall of Shame audit — 12 items, PASS or FLAG with a suggested fix
4. Academizer assessment — 2-3 casual phrases rewritten to graduate register
5. Personal + academic balance
6. School-specific research demonstration (Strong / Partial / Missing)
7. Vague adjective audit
8. Three highest-priority fixes with concrete rewrites
9. One thing working well

Supported formats: pdf, docx, doc, txt, md, rtf.

### Review your essay draft (inline)

Paste your draft and ask:

> "Review this against Asher's Essay Hall of Shame criteria. What should I fix?"

### Plan your application

> "I'm applying to PhD programs in cognitive science. Walk me through Asher's Application Sequence and help me build an activity log."

---

## Skill Structure

```
asher-grad-essays/
├── SKILL.md                  # Core frameworks + chapter index (always loaded)
├── README.md                 # This file
├── glossary.md               # ~30 defined terms (loaded on request)
├── patterns.md               # 14 named techniques with when/how/trade-offs
├── cheatsheet.md             # Quick-reference tables for major decisions
└── chapters/
    ├── ch00-introduction.md  # Read-First Protocol, Procrastination Recovery
    ├── ch01-should-you-go.md # Good/Bad Reasons, Funding Counterintuitions
    ├── ch02-choosing-school.md  # 20-School Rule, 5-Dimension Evaluation
    ├── ch03-planning-process.md # Activity Log, 30-Day-Early Rule
    ├── ch04-what-happens.md  # Application structure inside admissions
    ├── ch05-getting-ready.md # Pool-Building Protocol, Unusual Self-Assessment
    ├── ch06-first-draft.md   # RTGDQ, Epiphany Opening, Write-First Phase
    ├── ch07-subsequent-drafts.md # Academizer, Reader's Brain, Hall of Shame
    ├── ch08-samples.md       # Pattern analysis across 50+ annotated essays
    └── ch09-letters-of-rec.md # Three-Criteria Selection, Rights Waiver
```

`SKILL.md` is the only file loaded automatically. Chapter files are read on demand when you ask about a topic they cover, keeping token usage low.

---

## Key Frameworks (Preview)

| Framework | What It Does |
|-----------|-------------|
| **RTGDQ** | Read The Gosh Darn Question — answer exactly what was asked, in the order asked |
| **The Academizer** | Editing pass that converts casual first-draft language to graduate-level register |
| **Essay Hall of Shame** | Checklist of what admissions readers hate most (generic openers, wrong school name, etc.) |
| **Epiphany Opening** | Most effective essay structure: specific place + sensory detail + the moment of decision |
| **Pool-Building Protocol** | Complete all Ch 5 exercises before writing a word — generates the raw material |
| **Funding Counterintuitions** | Expensive schools are often cheaper; PhD is often cheaper than master's; always apply for aid |
| **Law of Descending Prestige** | You typically teach at a less prestigious institution than where you got your degree |
| **Three-Criteria Letter Selection** | Writer must: know your work well, say great things, be reliable |
| **Rights Waiver Rule** | Always waive Buckley Amendment rights — programs discount non-waived letters |
| **30-Day-Early Rule** | Apply at minimum 30 days early; 2+ months for highly competitive programs |

---

## How It Was Made

This skill was generated using [book-to-skill](https://github.com/virgiliojr94/book-to-skill), a Claude Code skill that converts books into reusable agent skills.

---

## License

The skill structure, synthesis, and formatting in this repository are released under [MIT License](LICENSE). The underlying intellectual content belongs to Donald Asher and Ten Speed Press. This repository makes no claim over the book's content and is intended solely as a study aid for people who own the book.
