# Putting it together

*What should a builder do first, and what is genuinely new here?*

Nine chapters, one message: **a written rule guides an agent, but only enforcement controls it.** A soul file that "grants no power", a skill that "grants no permission", a result that is "data, never orders": each is a good rule, and each needs a matching lock in configuration, code or process. Research is consistent on this point across identity [^owasp-llm06][^claude-memory], skills [^claude-skills], tools and limits [^owasp-llm06], and the space between agents [^nasr-attacker][^beurer-patterns]. When in doubt, ask of every rule: what actually stops the agent if it ignores this?

The second message is restraint. Both Anthropic and OpenAI advise starting with the simplest system that works and adding agents only when the work needs them [^anthropic-effective][^openai-guide]. Teams cost more and fail in new ways [^anthropic-multiagent][^mast]. Build the hive one layer at a time, and prove each layer before adding the next.

## A build order

| Stage | Add | Done when |
|---|---|---|
| 1. One agent | A role file, a soul file, one shared rules file | The agent does one job well, in a voice you recognise |
| 2. Skills | Three skills, each with a with and without test | Each skill actually improves the work |
| 3. Tools | Tools at permission none, then opened one by one | Nothing reaches outside without a gate |
| 4. Method | One workflow with a review gate and an output template | The same job comes out the same way twice |
| 5. Limits | An action ceiling and a fresh yes for final actions | Nothing costly or public happens unasked |
| 6. Loop | An independent verifier and 20 or more test briefs | Quality is measured, not assumed |
| 7. Team | A front door, a coordinator, one handoff contract | More agents add capacity, not confusion |
| 8. Nerves | A live board, typed results, an escalation ladder, a trace | The team can see, protect and audit itself |

**What is genuinely new in this model.** Several ideas here go further than common published practice, and they are fair to present as original design choices rather than research findings:

- Splitting provenance into RAW, FETCH, SEARCH and INFER, and treating search as discovery, never as evidence.
- Binding every review and approval to the exact version of the work, so any change voids it.
- Letting only a human turn a mistake into a rule, which also blocks an agent from writing its own instructions.
- Stating that a skill grants no permission, which is stricter than at least one popular runtime.
- Keeping readiness, dispatch and permission as three separate gates.
- Refusing to blur outcomes: partial is never reported as done.

**Two fixes for the examples.** The research found two places where the model's own example files contradict its principles. The example soul file repeats behaviour rules that already live in the role, which breaks "link, don't copy". The example SEO audit skill is marked active while its evaluation flag is still false, which breaks "tested before trusted". Fixing those two files makes the teaching material match what it teaches.

**What comes next.** The nervous system is the frontier. Live state and tracing are already standard in current frameworks; trust between agents is the most important and least solved problem in the field [^nasr-attacker][^prompt-infection]. A hive that can see its own work, refuse orders hidden in data, call for help, and replay what happened is a hive you can trust with real work.

---
Previous: [The nervous system](09-the-nervous-system.md)  ·  Home: [The Hive Mind](README.md)  ·  Sources: [References](references.md)

[^owasp-llm06]: OWASP GenAI Security Project, "LLM06:2025 Excessive Agency", Top 10 for LLM Applications 2025. https://genai.owasp.org/llmrisk/llm062025-excessive-agency/ ([all references](references.md#owasp-llm06))
[^claude-memory]: Anthropic, "How Claude remembers your project", Claude Code documentation, read 27 October 2026. https://code.claude.com/docs/en/memory ([all references](references.md#claude-memory))
[^claude-skills]: Anthropic, "Extend Claude with skills", Claude Code documentation, read 27 October 2026. https://code.claude.com/docs/en/skills ([all references](references.md#claude-skills))
[^nasr-attacker]: Milad Nasr, Nicholas Carlini et al., "The Attacker Moves Second: Stronger Adaptive Attacks Bypass Defenses Against LLM Jailbreaks and Prompt Injections", arXiv 2510.09023, 10 October 2025. https://arxiv.org/abs/2510.09023 ([all references](references.md#nasr-attacker))
[^beurer-patterns]: Luca Beurer-Kellner et al., "Design Patterns for Securing LLM Agents against Prompt Injections", arXiv 2506.08837, June 2025. https://arxiv.org/abs/2506.08837 ([all references](references.md#beurer-patterns))
[^anthropic-effective]: Erik Schluntz and Barry Zhang, "Building effective agents", Anthropic Engineering, 19 December 2024. https://www.anthropic.com/engineering/building-effective-agents ([all references](references.md#anthropic-effective))
[^openai-guide]: OpenAI, "A practical guide to building agents", PDF, April 2025 (date from file metadata). https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf ([all references](references.md#openai-guide))
[^anthropic-multiagent]: Jeremy Hadfield, Barry Zhang, Kenneth Lien, Florian Scholz, Jeremy Fox and Daniel Ford, "How we built our multi-agent research system", Anthropic Engineering, 13 June 2025. https://www.anthropic.com/engineering/multi-agent-research-system ([all references](references.md#anthropic-multiagent))
[^mast]: Mert Cemri, Melissa Z. Pan, Shuyi Yang et al., "Why Do Multi-Agent LLM Systems Fail?", arXiv 2503.13657, v3 26 October 2025. https://arxiv.org/abs/2503.13657 ([all references](references.md#mast))
[^prompt-infection]: Donghyun Lee and Mo Tiwari, "Prompt Infection: LLM-to-LLM Prompt Injection within Multi-Agent Systems", arXiv 2410.07283, 9 October 2024. https://arxiv.org/abs/2410.07283 ([all references](references.md#prompt-infection))
