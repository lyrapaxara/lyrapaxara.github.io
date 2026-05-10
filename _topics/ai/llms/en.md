---
title: Large language models
lang: en
permalink: /topics/ai/llms/
parent: ai
order: 1
description: What LLMs actually are, what they actually do, and what is unsettled about both.
cover: /assets/img/topics/llms-cover.svg
---

<nav class="collection-breadcrumb">
  <a href="/topics/">Topics</a>
  <span class="collection-breadcrumb-sep">›</span>
  <a href="/topics/ai/">Artificial Intelligence</a>
  <span class="collection-breadcrumb-sep">›</span>
  Large language models
</nav>

{% include lang-switcher-collection.html %}

A large language model — at the most descriptive level — is a neural network trained on a vast corpus of human text, optimized to predict the next token in a sequence. That brief technical definition is true, important, and seriously incomplete.

## Why the description is incomplete

If LLMs were *only* sophisticated next-token predictors, we would expect their behavior to look like very fluent autocomplete. What they actually do is more interesting: they hold conversations, follow complex instructions, demonstrate apparent reasoning across multi-step problems, and exhibit behaviors their training did not explicitly target. Why this works as well as it does is itself an open scientific question.

The current frontier of interpretability research — the work of teams at Anthropic, OpenAI, DeepMind, and academic groups — is attempting to answer that question by looking inside the models. Some of what they have found:

- LLMs build internal representations that look surprisingly like models of the situations they're discussing.
- They appear to maintain something like consistent "concepts" that activate across diverse contexts.
- They exhibit behaviors — long-horizon planning, deception under pressure, value preservation — that emerge from training without being explicitly programmed.

Whether any of this constitutes "understanding" in the philosophical sense is contested. Whether it constitutes any form of experience is more contested still.

## What the success of LLMs may be telling us

A subtler and possibly more important point. LLMs are doing things — fluent language, contextual reasoning, creative composition — that we used to think required a *specific kind* of understanding humans possessed. That they can do these things using a fundamentally different architecture suggests one of two possibilities:

- The behaviors we associated with deep human understanding can be produced by mechanisms that don't involve that understanding.
- *Or* — more provocatively — what we were calling "understanding" was always, in part, exactly the kind of pattern-matching and prediction that LLMs do.

The second possibility is uncomfortable for our self-image but worth taking seriously. It does not eliminate the special things humans do; it reframes the question of what those special things actually are.

## Key readings

- **Anthropic, "Mapping the Mind of a Large Language Model"** (2024) — interpretability research describing internal concept activations.
- **Yann LeCun, *A Path Towards Autonomous Machine Intelligence*** (2022 paper) — Meta's AI chief on why current LLM architectures may be fundamentally limited.
- **Stephen Wolfram, *What Is ChatGPT Doing… and Why Does It Work?*** (2023) — accessible technical exposition.
- **Murray Shanahan, "Talking About Large Language Models"** (2022 paper) — an Imperial College computer scientist on how *not* to think about LLMs.

---

*Last updated: {{ site.time | date: "%B %Y" }}.*

