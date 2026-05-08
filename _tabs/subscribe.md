---
icon: fas fa-envelope-open-text
order: 10
description: Inscreve-te na newsletter Lyrapaxara · Inscris-toi à la newsletter · Subscribe to the newsletter.
---

<div class="lang-tabs" id="subscribe-lang-tabs">
  <button class="lang-tab active" data-lang="pt">Português</button>
  <button class="lang-tab" data-lang="fr">Français</button>
  <button class="lang-tab" data-lang="en">English</button>
</div>

<div class="lang-section" data-lang="pt" markdown="1">

# Newsletter

De vez em quando, envio por email uma seleção dos textos novos publicados aqui — sem rodeios, sem spam, sem partilha de dados com terceiros.

Para te inscreveres, basta indicar o teu email no formulário abaixo. Receberás um email de confirmação para validares a inscrição (passo obrigatório por motivos legais e para evitar inscrições falsas).

{% include newsletter.html %}

## Como cancelar

Cada email enviado contém um link **"unsubscribe"** no rodapé. Um clique cancela a inscrição imediatamente, sem necessidade de explicação.

## Privacidade

O endereço de email é guardado pelo serviço [Buttondown](https://buttondown.com) e usado exclusivamente para envio da newsletter. Não é partilhado com terceiros.

</div>

<div class="lang-section" data-lang="fr" hidden markdown="1">

# Newsletter

De temps à autre, j'envoie par email une sélection des textes nouvellement publiés ici — sans détours, sans spam, sans partage de données avec des tiers.

Pour t'inscrire, il suffit d'indiquer ton adresse email dans le formulaire ci-dessous. Tu recevras ensuite un email de confirmation pour valider l'inscription (étape obligatoire pour des raisons légales et pour éviter les inscriptions fictives).

{% include newsletter.html %}

## Comment se désinscrire

Chaque email envoyé contient un lien **« unsubscribe »** en pied de page. Un seul clic suffit pour annuler l'abonnement, sans avoir à se justifier.

## Confidentialité

L'adresse email est conservée par le service [Buttondown](https://buttondown.com) et utilisée exclusivement pour l'envoi de la newsletter. Elle n'est partagée avec aucun tiers.

</div>

<div class="lang-section" data-lang="en" hidden markdown="1">

# Newsletter

From time to time, I send out by email a selection of the new texts published here — no fluff, no spam, no sharing of data with third parties.

To subscribe, simply enter your email address in the form below. You will then receive a confirmation email to validate the subscription (a mandatory step for legal reasons and to prevent fake sign-ups).

{% include newsletter.html %}

## How to unsubscribe

Every email sent contains an **"unsubscribe"** link in the footer. A single click cancels the subscription immediately, with no explanation required.

## Privacy

Your email address is stored by the [Buttondown](https://buttondown.com) service and used exclusively to send the newsletter. It is not shared with any third party.

</div>

<script>
(function() {
  const buttons = document.querySelectorAll('#subscribe-lang-tabs .lang-tab');
  const sections = document.querySelectorAll('#subscribe-lang-tabs ~ .lang-section');
  buttons.forEach(btn => {
    btn.addEventListener('click', () => {
      const target = btn.dataset.lang;
      buttons.forEach(b => b.classList.toggle('active', b.dataset.lang === target));
      sections.forEach(s => s.hidden = (s.dataset.lang !== target));
    });
  });
})();
</script>
