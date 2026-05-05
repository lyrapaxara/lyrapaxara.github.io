

---

icon: fas fa-palette
order: 2
description: Galeria de arte gráfica.

---

{% if site.data.art and site.data.art.size > 0 %}

<div class="art-gallery">
{% for piece in site.data.art %}
  <a class="art-tile" href="{{ piece.image | relative_url }}" data-title="{{ piece.title | escape }}">
    <img src="{{ piece.thumb | default: piece.image | relative_url }}"
         alt="{{ piece.title | escape }}" loading="lazy">
    {% if piece.title %}<span class="art-tile-caption">{{ piece.title }}</span>{% endif %}
  </a>
{% endfor %}
</div>

<div id="art-lightbox" hidden>
  <button id="art-lightbox-close" aria-label="Fechar">×</button>
  <img id="art-lightbox-img" src="" alt="">
  <div id="art-lightbox-caption"></div>
</div>

<script>
(function() {
  const tiles = document.querySelectorAll('.art-tile');
  const lb = document.getElementById('art-lightbox');
  const lbImg = document.getElementById('art-lightbox-img');
  const lbCap = document.getElementById('art-lightbox-caption');
  const lbClose = document.getElementById('art-lightbox-close');
  if (!lb) return;

  tiles.forEach(tile => {
    tile.addEventListener('click', e => {
      e.preventDefault();
      lbImg.src = tile.getAttribute('href');
      lbCap.textContent = tile.dataset.title || '';
      lb.hidden = false;
      document.body.style.overflow = 'hidden';
    });
  });

  function close() {
    lb.hidden = true;
    lbImg.src = '';
    document.body.style.overflow = '';
  }
  lbClose.addEventListener('click', close);
  lb.addEventListener('click', e => { if (e.target === lb) close(); });
  document.addEventListener('keydown', e => { if (e.key === 'Escape' && !lb.hidden) close(); });
})();
</script>

{% else %}
*A galeria está vazia. Adiciona obras em `_data/art.yml`.*
{% endif %}
