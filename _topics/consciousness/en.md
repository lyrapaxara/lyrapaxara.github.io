---
title: Consciousness
lang: en
permalink: /topics/consciousness/
is_landing: true
order: 1
icon: fas fa-brain
description: Notes, readings, and references on the nature of consciousness — the hard problem, altered states, and survival research.
cover: /assets/img/topics/consciousness-cover.svg
---

{% include lang-switcher-collection.html %}

What is consciousness? After centuries of philosophy and decades of neuroscience, the question remains stubbornly open. We can describe its neural correlates with growing precision; we still cannot say *why* there is anything it is like to be a conscious creature at all.

This page collects what I find most worth thinking about: the philosophical formulation of the puzzle, the empirical study of what happens to consciousness in altered states, and the controversial but persistent body of evidence suggesting that consciousness may not be exhausted by the brain's activity.

## My approach

I'm not committed to materialism, idealism, or any other -ism. I find the materialist consensus strong on what it explains, conspicuously silent on what it doesn't, and I try to read across traditions — analytic philosophy, contemplative writing, parapsychology, near-death studies — without pre-judging which corner the answers will come from.

## Recommended starting points

If you're new to the question, three books that frame it well from very different angles:

- **David Chalmers, *The Conscious Mind* (1996)** — the canonical statement of the "hard problem." Dense but rewarding.
- **Christof Koch, *The Feeling of Life Itself* (2019)** — a working neuroscientist's defense of Integrated Information Theory.
- **Pim van Lommel, *Consciousness Beyond Life* (2010)** — a cardiologist's study of near-death experiences and what they imply.

## Branches

Three subtopics where I gather more specific notes:

{% assign subs = site.topics | where_exp: "t", "t.parent == 'consciousness'" | where: "lang", "en" | sort: "order" %}

{% include card-grid.html items=subs %}

## Working list of references

This section will grow into something more structured. For now, a few articles and talks worth bookmarking:

- *(placeholder for an annotated list — books, papers, lectures, podcasts)*

---

*Last updated: {{ site.time | date: "%B %Y" }}.*
