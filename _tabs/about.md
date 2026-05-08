---
# the default layout is 'page'
title: About
icon: fas fa-user
order: 9
---

<div class="lang-tabs" id="about-lang-tabs">
  <button class="lang-tab active" data-lang="pt">Português</button>
  <button class="lang-tab" data-lang="fr">Français</button>
  <button class="lang-tab" data-lang="en">English</button>
</div>

<div class="lang-section" data-lang="pt" markdown="1">

# João Gabriel Correia

Nasceu em 1952, em Santana, Ilha da Madeira.

Foi aluno do Seminário do Funchal. Saiu da Madeira em 1970 e em 1971 radicou-se na Bélgica.

Frequentou a Universidade Católica Portuguesa em 1970-1971 (estudo de Filosofia e Teologia) e doutorou-se em Psicologia na Universidade Católica de Lovaina onde foi docente durante oito anos.

Ao lado da psicologia e ciências afins, os seus interesses vão da literatura, à filosofia, à antropologia, ao estudo comparado das culturas e religiões, e desde há pouco, à inteligência artificial! Em busca contínua de novos horizontes do conhecimento, o autor define-se sobretudo como um contador de histórias para jovens de todas as idades…

---

📩 Contacto: [contact@lyrapaxara.eu](mailto:contact@lyrapaxara.eu)

</div>

<div class="lang-section" data-lang="fr" hidden markdown="1">

# João Gabriel Correia

Né en 1952 à Santana, île de Madère, Portugal.

Ancien élève du Séminaire de Funchal, il quitte Madère en 1970 et s'installe en Belgique en 1971.

Il fréquente l'Université Catholique Portugaise en 1970-1971 (études de Philosophie et Théologie) puis obtient un doctorat en Psychologie à l'Université Catholique de Louvain, où il a enseigné pendant huit ans.

Au-delà de la psychologie et des sciences connexes, ses intérêts vont de la littérature à la philosophie, en passant par l'anthropologie, l'étude comparée des cultures et des religions, et depuis peu, l'intelligence artificielle ! En quête permanente de nouveaux horizons de connaissance, l'auteur se définit avant tout comme un conteur d'histoires pour jeunes de tous âges…

---

📩 Contact : [contact@lyrapaxara.eu](mailto:contact@lyrapaxara.eu)

</div>

<div class="lang-section" data-lang="en" hidden markdown="1">

# João Gabriel Correia

Born in 1952 in Santana, Madeira Island, Portugal.

A former student of the Funchal Seminary, he left Madeira in 1970 and settled in Belgium in 1971.

He attended the Portuguese Catholic University in 1970–1971 (studies in Philosophy and Theology) and received his doctorate in Psychology from the Catholic University of Louvain, where he taught for eight years.

Alongside psychology and related sciences, his interests range across literature, philosophy, anthropology, the comparative study of cultures and religions, and — more recently — artificial intelligence! In a continuous search for new horizons of knowledge, the author thinks of himself, above all, as a storyteller for young people of all ages…

---

📩 To get in touch: [contact@lyrapaxara.eu](mailto:contact@lyrapaxara.eu)

</div>

<script>
(function() {
  const buttons = document.querySelectorAll('#about-lang-tabs .lang-tab');
  const sections = document.querySelectorAll('.lang-section');
  buttons.forEach(btn => {
    btn.addEventListener('click', () => {
      const target = btn.dataset.lang;
      buttons.forEach(b => b.classList.toggle('active', b.dataset.lang === target));
      sections.forEach(s => s.hidden = (s.dataset.lang !== target));
    });
  });
})();
</script>
