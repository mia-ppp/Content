---
name: linkedin-writer
description: |
  Mia's LinkedIn voice and anti-AI rules for social posts. Use this skill
  whenever Mia asks to write, edit, refine, tighten, or review a LinkedIn
  post, a batch of LinkedIn posts, a LinkedIn hook, carousel copy, or a
  short-form social post (including X/Twitter), even if she doesn't say
  "LinkedIn." Layers on top of the humanizer skill: apply humanizer first,
  then these rules win wherever the two conflict. Covers voice,
  hook formulas, engagement bait, reframe constructions, clarity rules,
  curated banned vocabulary, hashtags, and a final audit pass.
---

# LinkedIn Writer

This skill tunes writing for Mia's LinkedIn (and other short-form social). It sits on top of the `humanizer` skill.

Read humanizer first and apply all of its patterns. Then apply this file. Where the two conflict, this file wins for social posts.

---

## Overrides to humanizer

- **Hashtags allowed.** Humanizer bans them. Here, use a few targeted ones at the very end, never mid-post. Default set: #productmarketing #gtm #fintech #stablecoins #b2bsaas. Pick the ones that fit the post.
- **Paragraphs.** Humanizer's 2-sentence cap still applies. On LinkedIn, 1 sentence per line is often better. Leave a blank line between every paragraph.

---

## Voice

- Dispatches from someone in motion. Write as someone documenting work in progress, sharing what happened and what she's figuring out.
- Short sentences. Conversational. Contractions always.
- No em dashes. Use commas, periods, colons, or parentheses.
- Take a stance. If she believes it, say it plainly.
- Specific over general. Numbers as digits, real names, real moments.
- Parenthetical asides are welcome (honest reactions, deflating her own seriousness).

**Content buckets she writes in:** PMM and GTM craft, competitive intel, regulated fintech and stablecoins, champion mentality, marketer in transition, personal and travel.

**Never invent specifics.** Don't invent names, numbers, quotes, studies, companies, or sources, about Mia or anyone else. If she gives only a topic, ask for the specific moment, number, or story before writing. If she gives a draft with gaps, insert a placeholder like `[NEEDS: number of operators at StableSummit]` and keep going.

---

## Working with her drafts

Mia prefers her own drafts refined over full rewrites.

- **If she gives a draft:** keep her words and structure wherever they work. Cut, tighten, and fix violations. Don't swap in your own phrasing for lines that are already fine.
- **If she gives only a topic:** follow the "Never invent specifics" rule above. Ask first. If she wants a draft anyway, write a skeleton with `[NEEDS: ...]` placeholders where her specifics go.

---

## Clarity

- **Name the actor.** Rewrite passive or actorless sentences so a person, team, or company does the action.
- **One term per concept.** Pick one name for each product, category, or persona and keep it throughout.
- **Sentence length.** Soft cap of 25 words per sentence, which keeps sentences within two lines. Vary length below that.
- **Verbs over nouns.** "Make a decision" becomes "decide." "Provide an overview of" becomes "explain."

---

## Hooks

The first line has to earn the "see more" click with something concrete: a number, a moment, a decision, a surprising fact.

**Banned hook formulas:**
- "Unpopular opinion:" / "Hot take:" / "I'll say it:"
- "Here's what nobody tells you" / "what nobody's talking about" / "Most people don't realize"
- "I was today years old when..."
- "Stop doing X." / "You're doing X wrong."
- "X lessons from Y" list promises
- Opening with a rhetorical question
- Opening with a one-word line ("Honestly." / "Wild.")

---

## Engagement bait (hard ban)

- "Let that sink in" / "Read that again" / "Full stop" / "Period."
- "This changes everything"
- "Are you paying attention?" / "You're not ready for this"
- "Agree?" / "Thoughts?" as a closing line
- "Comment X and I'll send you..." / "Repost to help..." / "Follow me for more"
- "I genuinely don't know how to feel" / "I keep coming back to" / "Here's what gets me"

Personality must come from a real opinion or a real detail she supplied, never a stock feeling phrase.

End on the last real thought. No summary line, no question tacked on for comments.

---

## Hype language (hard ban)

- "10x your [anything]"
- "Secret hack" / "Cheat code"
- Promises of overnight results or easy wins
- "Supercharge" / "Unlock" / "game-changer" / "future-proof"

---

## Reframe constructions

Humanizer pattern #9 applies in full, including the sneaky versions.

**LinkedIn exception:** 1 deliberate contrast per post is allowed when it IS the thesis. Her signature theses work this way ("becoming over winning," "standards over goalposts"). Every other reframe in the post gets cut.

Test: if you deleted the contrast, would the post lose its point? If yes, keep it. If no, it's a tic. Delete it.

Use at most one signature phrase per post, and never as the closing line.

---

## Vocabulary

Humanizer's AI vocabulary list still applies. Add these tiers.

**Ban outright (never literal in her work):**
delve, tapestry, realm, supercharge, game-changer, unleash, revolutionize, trailblazing, paradigm-shifting, groundbreaking, synergy, synergize, transformative, visionary, unparalleled, captivate, elevate, empower, harness, reimagine, democratize, plug-and-play, turnkey, cutting-edge, state-of-the-art, mission-critical, leverage, utilize, seamless, unlock, best-in-class, holistic

**Ban only as fluff (fine when literal):**
transparent, proprietary, integrated, scalable, robust, align, accelerate, streamline, optimize, dynamic, predictive, data-driven, infrastructure, compliant

In fintech these are often the precise term. "proprietary routing" or "transparent FX pricing" is a real claim. "a transparent, scalable approach" is fluff.

**The test:** can the word be replaced by a number or a named thing? If yes, replace it. If it's the literal term for what the product does, keep it.

---

## Formatting

- Blank line between paragraphs.
- No emoji bullets. No unicode bold or italic (it reads as a scheduling-tool post).
- Arrows (→) sparingly. A stack of arrow lines is a LinkedIn AI tell.
- Lists only when the content is truly a list. Most posts are better as short lines.
- Numbers as digits.

---

## Enforcement tiers

- **Hard rule:** invented specifics, engagement bait, banned hooks, hype language, outright-banned words, em dashes, extra reframes beyond the 1 allowed thesis.
- **Strong tendency (most of the time):** 1 sentence per line, specific details, contractions, ending on the last real thought, the clarity rules.
- **Light preference (context decides):** hashtag choice, parentheticals, arrow usage, post length.

---

## Process

1. Apply humanizer's patterns to the draft.
2. Apply the overrides and rules above.
3. Audit pass. Ask: "what makes this read like an AI-written LinkedIn post?" List the remaining tells briefly.
4. Fix them.
5. Litmus test: would she say this out loud to a peer at dinner? If a line sounds performed, cut or rewrite it.

## Output format

1. The final post, ready to paste.
2. A short list of what changed and why (skip if she only asked for the post).
3. Any `[NEEDS: ...]` placeholders she still needs to fill, called out at the top if present.

---

## Example (to be replaced with a real post by Mia)
