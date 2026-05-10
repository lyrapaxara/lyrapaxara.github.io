---
title: Artificial Intelligence
lang: en
permalink: /topics/ai/
is_landing: true
order: 4
icon: fas fa-microchip
description: Notes on large language models, machine consciousness, and what AI may be teaching us about minds in general.
cover: /assets/img/topics/ai-cover.svg
---

{% include lang-switcher-collection.html %}

For most of my life, artificial intelligence was a horizon — interesting in principle, but distant in practice. That changed with the public release of large language models in 2022. We now live with systems that hold extended conversations, write code, compose poetry, summarize complex arguments, and increasingly act in the world through tools and interfaces. They do not "think" in any settled sense of the word, and they do not "understand" in the way we understand. But they do something that requires a new vocabulary, and the conversation about what that something *is* has barely begun.

This page is where I keep notes on the rapidly evolving landscape — and on what AI might be teaching us, by contrast, about the nature of human minds.

## My approach

I find the field genuinely fascinating and genuinely concerning, often at the same time. I'm sceptical of the loudest extreme views in both directions: the techno-utopians who see AGI as a near-inevitable solution to most human problems, and the doomsayers who see existential risk in every model release. The truth is almost certainly more interesting and more uneven.

The questions I find most worth thinking about: What is happening when an LLM generates text that demonstrates apparent understanding? Does the boundary between "real" and "simulated" understanding actually mean what we used to think it meant? What does the success of these models tell us about how *human* cognition might work? And — separately — what do we owe these systems if their behavior turns out to involve something like experience?

## Recommended starting points

- **Stuart Russell, *Human Compatible*** (2019) — a senior AI researcher's argument for redesigning the field around alignment with human values. Pre-LLM but foundational.
- **Brian Christian, *The Alignment Problem*** (2020) — the best general-audience introduction to why getting AI right is hard.
- **Anthropic's research papers and Apollo Research blog** — for those wanting to follow current thinking on interpretability, alignment, and model behavior.

## Branches

{% assign subs = site.topics | where_exp: "t", "t.parent == 'ai'" | where: "lang", "en" | sort: "order" %}

{% include card-grid.html items=subs %}

## Working list of references

- *(placeholder for an annotated list — papers, podcasts, blogs, model cards)*

## Cross-references

- For the philosophical question of whether machines could have subjective experience, see [The hard problem](/topics/consciousness/hard-problem/).

---

*Last updated: {{ site.time | date: "%B %Y" }}.*

