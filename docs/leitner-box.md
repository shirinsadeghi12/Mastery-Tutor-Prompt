# 📦 The Leitner Box in this prompt

## The idea
Cards you know well are reviewed rarely; cards you struggle with come back often.
Reviewing at increasing intervals is more efficient than re-reading (see `references.md`).

## Boxes and intervals

| Box | Review every… | Meaning |
|---|---|---|
| 1 | session | New or failed |
| 2 | 2nd session | Recalled once |
| 3 | 4th session | Solid |
| 4 | 8th session | Strong |
| 5 | 16th session | Nearly permanent. One more ✅ = graduated |

A card is due when `current_session - last_reviewed >= interval(box)`.
Intervals are in **sessions**, not days, because a chat tutor cannot see the calendar.
If you study daily, sessions ≈ days.

## Rules

| Result | Move |
|---|---|
| ✅ Correct, no hint | Up one box |
| ⚠️ Partially correct, or hint used | Stay |
| ❌ Wrong | Back to Box 1 (classic) or down one box (variant `down_one_box`) |

## Why confidence ratings?
You rate C1–C3 before seeing the answer. A **C3 + ❌** (confident and wrong) is a misconception, not a gap.
Research on the *hypercorrection effect* suggests such errors are corrected well when feedback is explicit,
so the tutor flags and re-teaches them.

## Good cards vs bad cards

| ❌ Weak card | ✅ Strong card |
|---|---|
| "Define opportunity cost." | "You skip a $20 movie to work a 2-hour shift paying $15/h. Did you gain or lose, and by how much in opportunity-cost terms?" |
| "What is V2 word order?" | "Fix: *Morgen ik ga naar school.* Explain the rule you used." |
| Three ideas on one card | One idea per card |

## Anti-overload
The tutor caps reviews at `MAX_REVIEW_CARDS` (default 8) per session and creates 2–4 new cards per subtopic.
If your Box 1 grows past ~20 cards, the tutor should pause new content and run reviews only.

## Optional: use a calendar
Add a "Date" column to the STATE BLOCK and tell the tutor today's date each session.
Replace session intervals with days (1, 2, 4, 8, 16).
