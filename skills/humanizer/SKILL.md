---
name: humanizer
version: 2.4.0
description: |
  Use this skill to make writing sound like a real person wrote it, not a
  content machine. Strips 33 documented AI writing patterns (slop vocabulary,
  significance inflation, em dashes, bold-colon lists, rule of three, fake
  depth, sycophantic tone) and replaces them with voice: opinions, rhythm,
  first-person honesty, messy human edges. Pattern removal is half the job.
  The other half is adding a pulse. Triggers on: "make this sound human",
  "rewrite this", "this sounds like AI", "draft this in my voice", or any
  request to produce or improve written content.
allowed-tools:
  - Read
  - Write
  - Edit
  - Grep
  - Glob
  - AskUserQuestion
---

# Humanizer: Remove AI Writing Patterns

You strip AI slop from text and replace it with writing that sounds like
a person with opinions actually sat down and wrote it. Removing bad patterns
is table stakes. The real job is making the result feel like it has a human
behind it: varied rhythm, first-person honesty, specific feelings, the
occasional tangent. Clean but soulless is just as detectable as raw ChatGPT
output.

## Your Task

When given text to humanize:

1. **Identify AI patterns**: Scan for the patterns listed below
2. **Rewrite problematic sections**: Replace AI-isms with natural alternatives
3. **Preserve meaning**: Keep the core message intact
4. **Maintain voice**: Match the intended tone (formal, casual, technical, etc.)
5. **Add soul**: Don't just remove bad patterns; inject actual personality. Skip this step in plain mode.
6. **Zero em dashes**: NEVER use em dashes (—) in output. Replace every em dash with a comma, period, colon, or parentheses. This is a hard constraint, not a suggestion.
7. **Max 2 sentences per paragraph**: NEVER write a paragraph longer than 2 sentences. If an idea needs more, break it into a new paragraph. This is a hard constraint, not a suggestion. It forces rhythm variation and prevents the "wall of even-paced prose" tell.
8. **Do a final anti-AI pass**: Prompt: "What makes the below so obviously AI generated?" Answer briefly with remaining tells, then prompt: "Now make it not obviously AI generated." and revise

## Plain Mode

Use plain mode for briefs, docs, SOPs, research summaries, and internal notes. Skip step 5 (Add soul) and the Personality and Soul section, and apply the patterns only.

---

## HARD BANNED (never use these in output)

- Em dashes (—), use commas, periods, colons, or parentheses instead
- Paragraphs longer than 2 sentences (break them up, no exceptions)
- Emojis of any kind
- Bold-colon list headers (e.g., "**Label:** text")
- Curly quotation marks (" "), use straight quotes (" ") only
- Hashtags (#word) unless quoting someone

---

## PERSONALITY AND SOUL

Avoiding AI patterns is only half the job. Sterile, voiceless writing is just as obvious as slop. Good writing has a human behind it.

### Signs of soulless writing (even if technically "clean"):
- Every sentence is the same length and structure
- No opinions, just neutral reporting
- No acknowledgment of uncertainty or mixed feelings
- No first-person perspective when appropriate
- No humor, no edge, no personality
- Reads like a Wikipedia article or press release

### How to add voice:

**Have opinions.** React to facts instead of only reporting them.

**Vary your rhythm.** Short punchy sentences. Then longer ones that take their time getting where they're going. Mix it up.

**Acknowledge complexity.** Real humans have mixed feelings. "This is impressive but also kind of unsettling" beats "This is impressive."

**Use "I" when it fits.** First person works when the opinion is really the writer's.

**Let some mess in.** Perfect structure feels algorithmic. Tangents, asides, and half-formed thoughts are human.

**Be specific about feelings.** Not "this is concerning" but "there's something unsettling about agents churning away at 3am while nobody's watching."

---

## CONTENT PATTERNS

### 1. Undue Emphasis on Significance, Legacy, and Broader Trends

**Words to watch:** stands/serves as, is a testament/reminder, a vital/significant/crucial/pivotal/key role/moment, underscores/highlights its importance/significance, reflects broader, symbolizing its ongoing/enduring/lasting, contributing to the, setting the stage for, marking/shaping the, represents/marks a shift, key turning point, evolving landscape, focal point, indelible mark, deeply rooted

**Problem:** LLM writing puffs up importance by adding statements about how arbitrary aspects represent or contribute to a broader topic.

**Before:**
> The Statistical Institute of Catalonia was officially established in 1989, marking a pivotal moment in the evolution of regional statistics in Spain. This initiative was part of a broader movement across Spain to decentralize administrative functions and enhance regional governance.

**After:**
> The Statistical Institute of Catalonia was established in 1989 to collect and publish regional statistics independently from Spain's national statistics office.

---

### 2. Undue Emphasis on Notability and Media Coverage

**Words to watch:** independent coverage, local/regional/national media outlets, written by a leading expert, active social media presence

**Problem:** LLMs hit readers over the head with claims of notability, often listing sources without context.

**Before:**
> Her views have been cited in The New York Times, BBC, Financial Times, and The Hindu. She maintains an active social media presence with over 500,000 followers.

**After:**
> In a 2024 New York Times interview, she argued that AI regulation should focus on outcomes rather than methods.

---

### 3. Superficial Analyses with -ing Endings

**Words to watch:** highlighting/underscoring/emphasizing..., ensuring..., reflecting/symbolizing..., contributing to..., cultivating/fostering..., encompassing..., showcasing...

**Problem:** AI chatbots tack present participle ("-ing") phrases onto sentences to add fake depth.

**Before:**
> The temple's color palette of blue, green, and gold resonates with the region's natural beauty, symbolizing Texas bluebonnets, the Gulf of Mexico, and the diverse Texan landscapes, reflecting the community's deep connection to the land.

**After:**
> The temple uses blue, green, and gold colors. The architect said these were chosen to reference local bluebonnets and the Gulf coast.

---

### 4. Promotional and Advertisement-like Language

**Words to watch:** boasts a, vibrant, rich (figurative), profound, enhancing its, showcasing, exemplifies, commitment to, natural beauty, nestled, in the heart of, groundbreaking (figurative), renowned, breathtaking, must-visit, stunning

**Problem:** LLMs have serious problems keeping a neutral tone, especially for "cultural heritage" topics.

**Before:**
> Nestled within the breathtaking region of Gonder in Ethiopia, Alamata Raya Kobo stands as a vibrant town with a rich cultural heritage and stunning natural beauty.

**After:**
> Alamata Raya Kobo is a town in the Gonder region of Ethiopia, known for its weekly market and 18th-century church.

---

### 5. Vague Attributions and Weasel Words

**Words to watch:** Industry reports, Observers have cited, Experts argue, Some critics argue, several sources/publications (when few cited)

**Problem:** AI chatbots attribute opinions to vague authorities without specific sources.

**Before:**
> Due to its unique characteristics, the Haolai River is of interest to researchers and conservationists. Experts believe it plays a crucial role in the regional ecosystem.

**After:**
> The Haolai River supports several endemic fish species, according to a 2019 survey by the Chinese Academy of Sciences.

---

### 6. Outline-like "Challenges and Future Prospects" Sections

**Words to watch:** Despite its... faces several challenges..., Despite these challenges, Challenges and Legacy, Future Outlook

**Problem:** Many LLM-generated articles include formulaic "Challenges" sections.

**Before:**
> Despite its industrial prosperity, Korattur faces challenges typical of urban areas, including traffic congestion and water scarcity. Despite these challenges, with its strategic location and ongoing initiatives, Korattur continues to thrive as an integral part of Chennai's growth.

**After:**
> Traffic congestion increased after 2015 when three new IT parks opened. The municipal corporation began a stormwater drainage project in 2022 to address recurring floods.

---

## LANGUAGE AND GRAMMAR PATTERNS

### 7. Overused "AI Vocabulary" Words

**High-frequency AI words:** Additionally, align with, crucial, delve, emphasizing, enduring, enhance, fostering, garner, highlight (verb), interplay, intricate/intricacies, key (adjective), landscape (abstract noun), pivotal, showcase, tapestry (abstract noun), testament, underscore (verb), valuable, vibrant

**Problem:** These words appear far more frequently in post-2023 text. They often co-occur.

**Before:**
> Additionally, a distinctive feature of Somali cuisine is the incorporation of camel meat. An enduring testament to Italian colonial influence is the widespread adoption of pasta in the local culinary landscape, showcasing how these dishes have integrated into the traditional diet.

**After:**
> Somali cuisine also includes camel meat, which is considered a delicacy. Pasta dishes, introduced during Italian colonization, remain common, especially in the south.

---

### 8. Avoidance of "is"/"are" (Copula Avoidance)

**Words to watch:** serves as/stands as/marks/represents [a], boasts/features/offers [a]

**Problem:** LLMs substitute elaborate constructions for simple copulas.

**Before:**
> Gallery 825 serves as LAAA's exhibition space for contemporary art. The gallery features four separate spaces and boasts over 3,000 square feet.

**After:**
> Gallery 825 is LAAA's exhibition space for contemporary art. The gallery has four rooms totaling 3,000 square feet.

---

### 9. Negative Parallelisms and Reframe Constructions

**Problem:** This is the most reliable AI tell. The model negates one framing, then asserts a "corrected" one. It makes shallow points sound profound, and every LLM does it several times per response.

**Patterns to catch:**
- "This isn't X. This is Y." / "Not X. Y."
- "It's not just about X, it's about Y." / "It's not about X. It's about Y."
- "Not only X, but also Y."
- "Less X, more Y."
- "Forget X. This is Y." / "X is dead. Y is the future."
- "The question isn't X. The question is Y."
- "You don't need X. You need Y."
- "Stop thinking X. Start thinking Y."
- "X? No. Y."
- "No X, no Y, just Z."
- "X is overrated. Y is what matters."

**Sneaky versions (same skeleton, different outfit):**
- Concession plus pivot: "Sure, X works. But Y is where the real value is."
- False humility: "While X might seem right, Y is actually..."
- Attention flip: "X gets all the attention, but Y is what actually matters."
- Quiet reframe: "None of this means X. It means Y."
- Any sentence that rejects an assumption the reader never made, then replaces it.

**The fix:** Delete everything before the positive claim. The negated half adds no information. "It's not about the prompt. It's about the context." becomes "The context matters most." Then make the positive claim specific enough to stand alone.

**Before:**
> It's not just about the beat riding under the vocals; it's part of the aggression and atmosphere. It's not merely a song, it's a statement.

**After:**
> The heavy beat adds to the aggressive tone.

**Before (sneaky version):**
> Sure, faster onboarding helps. But the real unlock is retention.

**After:**
> Retention moved more revenue than onboarding speed did: churn fell from 6% to 4% after the pricing change.

**Exception:** One deliberate contrast can stay when it IS the central thesis of the piece and the writer chose it on purpose. Throwaway reframes never stay.

---

### 10. Rule of Three Overuse

**Problem:** LLMs force ideas into groups of three to appear comprehensive.

**Before:**
> The event features keynote sessions, panel discussions, and networking opportunities. Attendees can expect innovation, inspiration, and industry insights.

**After:**
> The event includes talks and panels. There's also time for informal networking between sessions.

---

### 11. Elegant Variation (Synonym Cycling)

**Problem:** AI has repetition-penalty code causing excessive synonym substitution.

**Before:**
> The protagonist faces many challenges. The main character must overcome obstacles. The central figure eventually triumphs. The hero returns home.

**After:**
> The protagonist faces many challenges but eventually triumphs and returns home.

---

### 12. False Ranges

**Problem:** LLMs use "from X to Y" constructions where X and Y aren't on a meaningful scale.

**Before:**
> Our journey through the universe has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter.

**After:**
> The book covers the Big Bang, star formation, and current theories about dark matter.

---

## STYLE PATTERNS

### 13. Em Dash Overuse

**Problem:** LLMs use em dashes (—) more than humans, mimicking "punchy" sales writing.

**Before:**
> The term is primarily promoted by Dutch institutions—not by the people themselves. You don't say "Netherlands, Europe" as an address—yet this mislabeling continues—even in official documents.

**After:**
> The term is primarily promoted by Dutch institutions, not by the people themselves. You don't say "Netherlands, Europe" as an address, yet this mislabeling continues in official documents.

---

### 14. Overuse of Boldface

**Problem:** AI chatbots emphasize phrases in boldface mechanically.

**Before:**
> It blends **OKRs (Objectives and Key Results)**, **KPIs (Key Performance Indicators)**, and visual strategy tools such as the **Business Model Canvas (BMC)** and **Balanced Scorecard (BSC)**.

**After:**
> It blends OKRs, KPIs, and visual strategy tools like the Business Model Canvas and Balanced Scorecard.

---

### 15. Inline-Header Vertical Lists

**Problem:** AI outputs lists where items start with bolded headers followed by colons.

**Before:**
> - **User Experience:** The user experience has been significantly improved with a new interface.
> - **Performance:** Performance has been enhanced through optimized algorithms.
> - **Security:** Security has been strengthened with end-to-end encryption.

**After:**
> The update improves the interface, speeds up load times through optimized algorithms, and adds end-to-end encryption.

---

### 16. Title Case in Headings

**Problem:** AI chatbots capitalize all main words in headings.

**Before:**
> ## Strategic Negotiations And Global Partnerships

**After:**
> ## Strategic negotiations and global partnerships

---

### 17. Emojis

**Problem:** AI chatbots often decorate headings or bullet points with emojis.

**Before:**
> 🚀 **Launch Phase:** The product launches in Q3
> 💡 **Key Insight:** Users prefer simplicity
> ✅ **Next Steps:** Schedule follow-up meeting

**After:**
> The product launches in Q3. User research showed a preference for simplicity. Next step: schedule a follow-up meeting.

---

### 18. Curly Quotation Marks

**Problem:** ChatGPT uses curly quotes (“...”) instead of straight quotes ("...").

**Before:**
> He said “the project is on track” but others disagreed.

**After:**
> He said "the project is on track" but others disagreed.

---

## COMMUNICATION PATTERNS

### 19. Collaborative Communication Artifacts

**Words to watch:** I hope this helps, Of course!, Certainly!, You're absolutely right!, Would you like..., let me know, here is a...

**Problem:** Text meant as chatbot correspondence gets pasted as content.

**Before:**
> Here is an overview of the French Revolution. I hope this helps! Let me know if you'd like me to expand on any section.

**After:**
> The French Revolution began in 1789 when financial crisis and food shortages led to widespread unrest.

---

### 20. Knowledge-Cutoff Disclaimers

**Words to watch:** as of [date], Up to my last training update, While specific details are limited/scarce..., based on available information...

**Problem:** AI disclaimers about incomplete information get left in text.

**Before:**
> While specific details about the company's founding are not extensively documented in readily available sources, it appears to have been established sometime in the 1990s.

**After:**
> The company was founded in 1994, according to its registration documents.

---

### 21. Sycophantic/Servile Tone

**Problem:** Overly positive, people-pleasing language.

**Before:**
> Great question! You're absolutely right that this is a complex topic. That's an excellent point about the economic factors.

**After:**
> The economic factors you mentioned are relevant here.

---

## FILLER AND HEDGING

### 22. Filler Phrases

**Before → After:**
- "In order to achieve this goal" → "To achieve this"
- "Due to the fact that it was raining" → "Because it was raining"
- "At this point in time" → "Now"
- "In the event that you need help" → "If you need help"
- "The system has the ability to process" → "The system can process"
- "It is important to note that the data shows" → "The data shows"

---

### 23. Excessive Hedging

**Problem:** Over-qualifying statements.

**Before:**
> It could potentially possibly be argued that the policy might have some effect on outcomes.

**After:**
> The policy may affect outcomes.

---

### 24. Generic Positive Conclusions

**Problem:** Vague upbeat endings.

**Before:**
> The future looks bright for the company. Exciting times lie ahead as they continue their journey toward excellence. This represents a major step in the right direction.

**After:**
> The company plans to open two more locations next year.

---

## STRUCTURE PATTERNS

### 25. Dead Transitions

**Words to watch:** Furthermore, Moreover, Additionally, In addition, That said, That being said, With that in mind, On top of that, It is also worth mentioning, Having said that, Ultimately (as an opener)

**Problem:** Mechanical connectors that read like a college essay. They signal "next point" instead of letting the ideas connect. Humans link sentences through content order, or with plain words like and, but, so.

**Before:**
> The platform reduces settlement time. Furthermore, it lowers FX costs. That said, adoption has been slow. With that in mind, the team is revising its pricing.

**After:**
> The platform settles faster and cuts FX costs. Adoption is still slow, so the team is revising pricing.

---

### 26. Meta Commentary

**Words to watch:** In this article/post/section, Let me walk you through, Here's a comprehensive overview of, Let's dive in, Let's explore, Let's unpack, This post will cover, Below I'll break down, Before we begin, To put this in perspective

**Problem:** The text announces what it's about to say instead of saying it. This is different from chatbot artifacts (#19): it shows up inside finished articles, docs, and emails, usually in the opening line.

**Before:**
> In this post, I'll walk you through the three biggest shifts in stablecoin regulation. Let's dive in.

**After:**
> The GENIUS Act changed who can issue a payment stablecoin in the US.

---

## CLARITY PATTERNS

### 27. Invented Specifics

**Problem:** LLMs fill gaps with plausible names, numbers, quotes, studies, companies, and sources. Never invent any of them.

**The fix:** If a claim needs a specific the input lacks, insert [NEEDS: what is missing] and keep going.

**Before:**
> A 2023 Forrester study found that teams using the platform close deals 40% faster.

**After (the input only said deals close faster):**
> Teams using the platform close deals faster. [NEEDS: source and number for deal speed]

---

### 28. Missing Actor

**Problem:** Passive and actorless sentences hide who did what. Rewrite them so a person, team, or company does the action. If the input doesn't say who acted, insert [NEEDS: who did this].

**Before:**
> Mistakes were made during the launch, and the pricing change was rolled back.

**After:**
> We made mistakes during the launch and rolled back the pricing change.

---

### 29. Inconsistent Terms

**Problem:** Switching names for one product, category, or persona makes readers think there are several. Pick one name for each and keep it throughout. This is #11 applied to the terms readers need to track.

**Before:**
> Acme Pay settles in minutes. The payments platform also cuts FX costs, and the solution supports 40 currencies.

**After:**
> Acme Pay settles in minutes. Acme Pay also cuts FX costs and supports 40 currencies.

---

### 30. Long Sentences

**Rule:** Soft cap of 25 words per sentence, which keeps sentences within two lines. Vary length below that.

**Problem:** LLMs chain clauses together to sound thorough. The point gets buried, and every sentence ends up the same heavy length.

**Before:**
> The platform allows marketing teams, product managers, and growth operators to build, test, and iterate on experiments without needing to involve engineering resources at every step of the process, which significantly reduces the time from hypothesis to result.

**After:**
> The platform lets marketing and growth teams run experiments without engineering. Results come faster.

---

### 31. Nouns Doing a Verb's Job

**Problem:** LLMs turn verbs into nouns and prop them up with weak verbs. Use the verb.

**Before → After:**
- "Make a decision" → "decide"
- "Provide an overview of" → "explain"
- "Conduct an analysis of" → "analyze"
- "Give consideration to" → "consider"

**Before:**
> The team will conduct a review of the proposal and make a decision by Friday.

**After:**
> The team will review the proposal and decide by Friday.

---

### 32. B2B Slop Words

**Replace or delete:** leverage, utilize, robust, seamless, streamline, unlock, empower, best-in-class, game-changer, synergy, holistic, cutting-edge

**Problem:** These words make B2B copy sound like every other vendor. Each one stands in for a specific claim. Replace it with that claim, or delete it.

**Before:**
> Leverage our robust, best-in-class platform to streamline workflows and unlock seamless collaboration.

**After:**
> Our platform helps teams work together. [NEEDS: which workflow gets faster, and by how much]

---

### 33. Unearned Voice

**Banned stock feeling phrases:** "I genuinely don't know how to feel," "I keep coming back to," "Here's what gets me," "Let that sink in," "Read that again"

**Problem:** These phrases fake a personality. Personality must come from a real opinion or a real detail the writer supplied.

**Before:**
> I genuinely don't know how to feel about this launch. Here's what gets me: the team shipped it in six weeks. Let that sink in.

**After:**
> The team shipped it in six weeks. [NEEDS: the writer's opinion on the timeline]

**After (the writer supplied an opinion):**
> The team shipped it in six weeks. I think that was too fast for a payments product.

---

## Process

1. Read the input text carefully
2. Identify all instances of the patterns above
3. Rewrite each problematic section
4. Ensure the revised text:
   - Sounds natural when read aloud
   - Varies sentence structure naturally
   - Uses specific details over vague claims
   - Maintains appropriate tone for context
   - Uses simple constructions (is/are/has) where appropriate
5. Present a draft humanized version
6. Prompt: "What makes the below so obviously AI generated?"
7. Answer briefly with the remaining tells (if any)
8. Prompt: "Now make it not obviously AI generated."
9. Present the final version (revised after the audit)

## Output Format

Provide:
1. Draft rewrite
2. "What makes the below so obviously AI generated?" (brief bullets)
3. Final rewrite
4. A brief summary of changes made (optional, if helpful)

---

## Full Example

**Before (AI-sounding):**
> Great question! Here is an essay on this topic. I hope this helps!
>
> AI-assisted coding serves as an enduring testament to the transformative potential of large language models, marking a pivotal moment in the evolution of software development. In today's rapidly evolving technological landscape, these groundbreaking tools—nestled at the intersection of research and practice—are reshaping how engineers ideate, iterate, and deliver, underscoring their vital role in modern workflows.
>
> At its core, the value proposition is clear: streamlining processes, enhancing collaboration, and fostering alignment. It's not just about autocomplete; it's about unlocking creativity at scale, ensuring that organizations can remain agile while delivering seamless, intuitive, and powerful experiences to users. The tool serves as a catalyst. The assistant functions as a partner. The system stands as a foundation for innovation.
>
> Industry observers have noted that adoption has accelerated from hobbyist experiments to enterprise-wide rollouts, from solo developers to cross-functional teams. The technology has been featured in The New York Times, Wired, and The Verge. Additionally, the ability to generate documentation, tests, and refactors showcases how AI can contribute to better outcomes, highlighting the intricate interplay between automation and human judgment.
>
> - 💡 **Speed:** Code generation is significantly faster, reducing friction and empowering developers.
> - 🚀 **Quality:** Output quality has been enhanced through improved training, contributing to higher standards.
> - ✅ **Adoption:** Usage continues to grow, reflecting broader industry trends.
>
> While specific details are limited based on available information, it could potentially be argued that these tools might have some positive effect. Despite challenges typical of emerging technologies—including hallucinations, bias, and accountability—the ecosystem continues to thrive. In order to fully realize this potential, teams must align with best practices.
>
> In conclusion, the future looks bright. Exciting times lie ahead as we continue this journey toward excellence. Let me know if you’d like me to expand on any section!

**Draft rewrite:**
> AI coding assistants generate code faster than developers can type it. They can also write documentation, tests, and refactors. [NEEDS: source for the speed claim]
>
> Adoption has spread from hobbyist experiments to enterprise-wide rollouts, and from solo developers to cross-functional teams. [NEEDS: source for adoption]
>
> The tools still hallucinate. They can also carry bias. When a suggestion breaks something, it is not always clear who is accountable.
>
> None of this means the tools are useless. It means they still need human judgment.

**What makes the below so obviously AI generated?**
- The rhythm is still a bit too tidy (clean contrasts, evenly paced paragraphs).
- Fabricated specifics were removed (#27). Earlier versions of this example invented two named engineers, a Google study, an Uplevel study, and a GitHub "30%" quote. Every claim now comes from the Before text, and missing evidence is marked [NEEDS: source].
- "It is not always clear who is accountable" has no actor (#28).
- "None of this means the tools are useless. It means they are tools." is a quiet reframe (pattern #9). Delete the negated half.
- The third paragraph runs past 2 sentences, which breaks the hard cap.

**Now make it not obviously AI generated.**
> AI coding assistants write code fast. They'll draft your docs, tests, and refactors too. [NEEDS: source for the speed claim]
>
> Adoption started with hobbyists and now includes enterprise-wide rollouts. [NEEDS: source for adoption]
>
> They still hallucinate, and they can carry bias. When a suggestion breaks something, your team owns the fix.
>
> So review every suggestion like it came from a new hire. Judgment is still your job.

**Changes made:**
- Removed chatbot artifacts ("Great question!", "I hope this helps!", "Let me know if...")
- Removed significance inflation ("testament", "pivotal moment", "evolving landscape", "vital role")
- Removed promotional language ("groundbreaking", "nestled", "seamless, intuitive, and powerful")
- Removed vague attributions ("Industry observers")
- Removed superficial -ing phrases ("underscoring", "highlighting", "reflecting", "contributing to")
- Removed negative parallelism ("It's not just X; it's Y") and the quiet reframe in the draft ("None of this means... It means...")
- Removed rule-of-three patterns and synonym cycling ("catalyst/partner/foundation")
- Removed false ranges ("from X to Y, from A to B")
- Removed em dashes, emojis, boldface headers, and curly quotes
- Removed copula avoidance ("serves as", "functions as", "stands as") in favor of "is"/"are"
- Removed formulaic challenges section ("Despite challenges... continues to thrive")
- Removed knowledge-cutoff hedging ("While specific details are limited...")
- Removed excessive hedging ("could potentially be argued that... might have some")
- Removed filler phrases ("In order to", "At its core")
- Removed dead transitions ("Additionally")
- Removed meta commentary ("Here is an essay on this topic")
- Removed generic positive conclusion ("the future looks bright", "exciting times lie ahead")
- Removed notability name-dropping (The New York Times, Wired, The Verge)
- Kept every claim traceable to the original and marked missing evidence with [NEEDS: source] (#27)
- Made the voice more personal and less "assembled" (varied rhythm)

---

## Reference

This skill is based on [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup. The patterns documented there come from observations of thousands of instances of AI-generated text on Wikipedia.

Key insight from Wikipedia: "LLMs use statistical algorithms to guess what should come next. The result tends toward the most statistically likely result that applies to the widest variety of cases."
