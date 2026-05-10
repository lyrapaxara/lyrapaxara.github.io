---
title: Consciência
lang: pt
permalink: /topics/consciousness/pt/
is_landing: true
order: 1
icon: fas fa-brain
description: Notas, leituras e referências sobre a natureza da consciência — o problema difícil, os estados alterados, e a investigação sobre a sobrevivência.
cover: /assets/img/topics/consciousness-cover.svg
---

{% include lang-switcher-collection.html %}

O que é a consciência? Depois de séculos de filosofia e décadas de neurociência, a questão permanece obstinadamente aberta. Sabemos descrever os seus correlatos neuronais com precisão crescente; continuamos sem saber dizer *porque* há sequer algo como aquilo que se sente ser um ser consciente.

Esta página reúne o que me parece mais digno de pensamento: a formulação filosófica do enigma, o estudo empírico do que acontece à consciência em estados alterados, e o corpo de investigação — controverso mas persistente — que sugere que a consciência poderá não esgotar-se na actividade do cérebro.

## A minha abordagem

Não me comprometo nem com o materialismo, nem com o idealismo, nem com qualquer outro -ismo. Acho o consenso materialista sólido naquilo que explica, e curiosamente silencioso naquilo que não explica. Tento ler através de tradições — filosofia analítica, escrita contemplativa, parapsicologia, estudos sobre experiências de quase-morte — sem prejulgar de que canto virão as respostas.

## Pontos de partida

Para abordar a questão, três livros que a enquadram bem a partir de ângulos muito diferentes:

- **David Chalmers, *The Conscious Mind* (1996)** — o enunciado canónico do «problema difícil». Denso mas recompensador.
- **Christof Koch, *The Feeling of Life Itself* (2019)** — a defesa, por um neurocientista em exercício, da teoria da informação integrada.
- **Pim van Lommel, *Consciência para além da Vida* (2010)** — o estudo de um cardiologista sobre experiências de quase-morte e o que implicam.

## Ramos

Três subdomínios onde junto notas mais específicas:

{% assign subs = site.topics | where_exp: "t", "t.parent == 'consciousness'" | where: "lang", "pt" | sort: "order" %}

{% include card-grid.html items=subs %}

## Lista de referências (em construção)

Esta secção crescerá para algo mais estruturado. Por agora, alguns artigos e conferências dignos de marcador:

- *(espaço para uma lista anotada — livros, artigos, conferências, podcasts)*

---

*Última actualização: {{ site.time | date: "%B %Y" }}.*

