# 🎓 Mastery Tutor Prompt

A copy-paste prompt that turns any LLM into a **mastery-based tutor** for any book, PDF, or syllabus.
It combines short lectures, application-level practice, honest feedback, and a **Leitner box**
(spaced repetition) that works even when the model has no memory.

## ✨ What you get

| Feature | What it does |
|---|---|
| 📚 Curriculum builder | Extracts the table of contents, rates difficulty, builds a roadmap |
| 🧠 2-paragraph lectures | Short, example-driven, scaffolded (simple → layered → edge case) |
| 🎯 3 graded questions | Apply → Analyze → Transfer. Never "repeat the text" |
| 📦 Leitner box | Cards move up on success, reset on failure; due cards are reviewed first |
| 🪞 Confidence ratings | You rate confidence before grading; confident-but-wrong answers are flagged |
| 💾 Portable state | A `STATE BLOCK` you paste back each session. No memory feature required |
| 🧭 Adaptive pacing | Depth and speed adjust to your recent scores |
| ⚖️ Honest feedback | No empty praise; claims cite the source or are labeled as external |

## 🚀 Quick start (2 minutes)

1. Open `prompts/mastery-tutor.md` and copy everything.
2. Paste it into a new chat. Fill in the `CONFIG` block (or leave it and the tutor will ask).
3. Attach or paste your material (book, PDF, notes, topic list).
4. Confirm the curriculum. Study. At the end of each session, **copy the STATE BLOCK** the tutor prints.
5. Next session: paste the prompt again + your STATE BLOCK.

## 🕹️ Commands

| Command | Effect |
|---|---|
| `/status` | Progress table + box counts |
| `/review` | Force a review round now |
| `/hint` | Next hint level (answering with a hint caps the card at ⚠️) |
| `/skip` | Skip current question (counts as ❌) |
| `/export` | Print the STATE BLOCK |
| `/boxes` | Show all cards by box |

## ⚠️ Limitations (read this)

- The individual techniques (retrieval practice, spacing, interleaving) have good research support
  (see `docs/references.md`). **This specific prompt has not been tested in a controlled study.**
- LLMs can misgrade or misremember. Challenge any grade you disagree with.
- LLMs can hallucinate citations. The prompt tells the tutor to say "location not verified" when unsure, but check important claims yourself.
- Strict formatting ("exactly two paragraphs") is followed less reliably by smaller models.
- Scheduling is by *session number*, not calendar date. The tutor can't know how many days passed.

## 🗺️ Roadmap

- [ ] Lite version (half length) for smaller models
- [ ] Persian / Spanish / German translations
- [ ] Test suite: sample inputs and expected behaviors
- [ ] Optional script that parses the STATE BLOCK and computes due cards

## 📄 License

MIT. See `LICENSE`.
