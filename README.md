# VOCAL Prompts — Dialogic Bootstrapping Session Prompts

This repository contains runtime system prompts that implement the **VOCAL Framework** (*Vocabulary-Oriented Collaboration with AI for Learning*), introduced in:

> Muñoz-Jaramillo, A., Tejada-Sánchez, I., Mahlin, P., Holland, C., & Zevin, D. (2026). *The VOCAL Framework: Vocabulary-Oriented Collaboration with AI for Learning in STEAM Education.*

![VOCAL Framework Infographic](VOCAL_Infographic.png)

---

## The idea behind these prompts

The VOCAL Framework argues that **conceptual vocabulary — not prompting technique — is the primary bottleneck in productive human-AI collaboration**. A learner who lacks the domain-specific terms to describe what they need cannot be helped by prompting tips alone; the gap is linguistic, not technical.

The prompts operationalize a mechanism called **dialogic bootstrapping**: a positive feedback loop in which iterative AI dialogue builds the vocabulary needed for progressively more effective prompting. Each exchange should leave the learner better equipped to ask the next question.

By default, general-purpose LLMs work *against* this process: they silently translate vague language into precise vocabulary, decompose problems on the learner's behalf, and accept "looks good" as task completion — all of which short-circuit vocabulary acquisition. These prompts install specific countermeasures:

- A **calibration probe** at session opening that estimates the learner's domain level from behavioral evidence, overriding self-reported expertise.
- A **three-phase interaction cycle** (engage → introduce → produce) that separates the introduction of new terms from their evaluative use, preventing the learner from skipping productive engagement.
- **Anchor term persistence**: a term identified as the learner's next growth edge is tracked across cycles and woven into subsequent questioning until the learner deploys it correctly.
- **Suppressed default behaviors**: the prompts explicitly prohibit silent vocabulary translation, unprompted problem decomposition, and accepting output without explanation in domain terms.

Progress is tracked against a **five-level AI Collaboration Scale**, from Level 1 (*creative subordination* — vague goals, no evaluative capacity) to Level 5 (*equal partnership* — full technical direction, nuanced evaluation). The scale is domain-relative: a learner may be at Level 4 in Python and Level 1 in solar physics within the same session.

---

## Available prompts

| Language | Prompt |
|---|---|
| English | [VOCAL\_prompt\_implementing\_dialogic\_bootstrapping\_EN.md](VOCAL_prompts/VOCAL_prompt_implementing_dialogic_bootstrapping_EN.md) |
| Spanish | [VOCAL\_prompt\_implementando\_bootstrapping\_dialogico\_ES.md](VOCAL_prompts/VOCAL_prompt_implementando_bootstrapping_dialogico_ES.md) |

---

## How to use

1. **Open the prompt file** for your preferred language.

2. **Fill in the SESSION CONTEXT** at the top of the file:
   - `Session length` — estimated time available (e.g., `45 minutes`).
   - `Topic` — the subject or task the learner will work on, in their own words.
   - `Goal type` — one of: *understand a concept*, *get a task done*, or *explore a topic broadly*.

3. **Leave the OPTIONAL SESSION CONTEXT blank if unsure.** An empty field is better than a guess. The AI will infer defaults from the calibration probe.

4. **Paste the entire document** — including the filled-in SESSION CONTEXT — into the system prompt or at the start of a new conversation with your LLM of choice, followed immediately by the learner's first question or task.

5. **Let the session run.** The prompt manages the interaction structure from there: it will open with a calibration probe, introduce vocabulary in context, require the learner to produce vocabulary before moving forward, and close cycles with explicit reflection on vocabulary gains.

### A note on the OPTIONAL SESSION CONTEXT

The optional fields are primarily designed for **educators deploying these prompts in a structured course or program**:

- `Primary domain` and `Adjacent domains` focus the calibration and vocabulary selection on the specific disciplinary context of the lesson.
- `Vocabulary already introduced in prior sessions` allows the AI to treat previously learned terms as known anchors, picking up where the last session left off rather than re-introducing familiar vocabulary.
- `Target collaboration level` communicates the educator's pedagogical goal for the session. **This does not set the AI's working level** — the calibration probe does — but it tells the AI which level to aim toward as the session's ceiling.

If you are using these prompts outside a formal curriculum (e.g., self-directed learning or professional upskilling), the required SESSION CONTEXT fields are sufficient to get started.

---

## Contributing

We welcome discussion, suggested modifications, and new prompts with specific pedagogical objectives. These prompts are actively tested and revised as part of the [ButterflAI program](https://coffies.ucar.edu/butterflai) — an 11-week undergraduate research experience in solar physics built around the VOCAL Framework. Open an issue or pull request to contribute.
