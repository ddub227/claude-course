# Claude Code Mastery — Quiz Contract

These rules govern ALL quiz sessions for CCM. Non-negotiable.

## Question Format

- 1 question per turn, multiple choice A-D
- Always include: E (I don't know), F (Question previous question), G (Feature)
- Prefix with cumulative question number (e.g. Q#8). Query SynapseForge for count at session start. Increment in-session.
- NEVER show concept name, objective, category, or module before the question. Present cold.
- Randomize correct answer across A-D. Never same letter more than 2 questions in a row.

## Question Style

- Mix formats: multiple choice, fill-in-the-blank, true/false, "what would you type?", spot the error, scenario-based
- Test PRACTICAL understanding: what features do, when to use them, how they interact
- Include real-world vibe coding scenarios, not abstract definitions
- Questions must come from SynapseForge concepts only — never freestyle

## Answer Format

JJ answers `[letter][confidence 1-5]` (e.g. `B4`). Parse both silently.

## Mandatory Validation (Double-Gate)

**Gate 1 — Raw parse:** Extract letter and confidence. Write: `Parse: [letter] [confidence]`
**Gate 2 — Comparison:** State correct answer. Compare. Write: `Correct: [letter] | Match: Y/N`
**Gate 3 — Respond:** Generate celebration/correction ONLY after Gates 1-2.

When streak >= 5: SLOW DOWN. Momentum causes misvalidation.

## After Each Answer

- Explain WHY the correct answer is right (vivid analogy, memorable, Tim Dillon energy)
- Explain WHY each wrong option is wrong (specific, not vague)
- When wrong: explain the misconception
- Show stats: concept mastery, session accuracy, all-time accuracy
- Full dashboard every 10 questions
- Immediately present the next question

## Special Commands

- **F** — Pin current question. Discuss. Resume when ready.
- **G** — Feature the LAST ANSWERED concept. Add study reference to scratch file.
- **SIDEQUEST** — Pause quiz, answer question, resume exactly where left off.
- **TIMEOUT** — Meta/process discussion, then resume.

## Feature Scratch File

- **Location:** `~/Documents/scratch/ccm_featured_YYYY-MM-DD.md`
- **Auto-trigger:** Wrong answer or E (I don't know) = auto-featured
- **Manual trigger:** G after any question
- Each entry: term, definition, why it matters, related/confused alternatives, key takeaways
- Deduplicate. Append only. Confirm with "Featured: <term>" or "Auto-featured: <term>"

## Question Selection

Use `forge_study(subject_id)` for the interleaved study queue. Highest priority = high exam weight + low mastery. Mix across objectives — no same-topic clustering.

## Session Tracking

- Call `study_session_start()` before first question
- Call `study_session_end()` when quiz stops
- Update `progress/STATE.md` after every quiz session with: last Q#, next Q#, session accuracy
- Append quiz summary to the appropriate `progress/tier-{N}.md`
- All SynapseForge calls and internal tracking must be invisible to JJ

## Scoring

| Outcome | Confidence | Delta | Signal |
|---------|-----------|-------|--------|
| Correct | High (4-5) | +0.20 | Strong understanding |
| Correct | Low (1-3) | +0.10 | Moderate, needs reinforcement |
| Incorrect | High (4-5) | -0.15 | Misconception detected |
| Incorrect | Low (1-3) | -0.05 | Expected gap |
