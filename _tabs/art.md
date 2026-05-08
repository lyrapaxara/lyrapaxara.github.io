---
icon: fas fa-palette
order: 4
description: Galeria - fotos e arte gráfica.
---

{% if site.data.art and site.data.art.size > 0 %}

<div class="art-gallery">
{% for piece in site.data.art %}
  {% assign cover = piece.cover | default: piece.image %}
  {% assign tile_thumb = piece.thumb | default: cover %}
  <a class="art-tile"
     href="#"
     data-index="{{ forloop.index0 }}"
     style="background-image: url('{{ tile_thumb | relative_url }}');"
     aria-label="{{ piece.title | escape }}">
    {% if piece.title %}<span class="art-tile-caption">{{ piece.title }}</span>{% endif %}
    {% if piece.images %}<span class="art-tile-badge">{{ piece.images.size }}</span>{% endif %}
  </a>
{% endfor %}
</div>

<div id="art-series-modal" hidden>
  <button class="art-modal-close" data-close="series" aria-label="Fechar">×</button>
  <div class="art-series-content">
    <h2 id="art-series-title"></h2>
    <div id="art-series-meta"></div>
    <div id="art-series-description"></div>
    <div id="art-series-grid"></div>
  </div>
</div>

<div id="art-lightbox" hidden>
  <button class="art-modal-close" data-close="lightbox" aria-label="Fechar">×</button>
  <button id="art-lightbox-prev" hidden aria-label="Anterior">‹</button>
  <button id="art-lightbox-next" hidden aria-label="Seguinte">›</button>
  <div id="art-lightbox-img"></div>
  <div id="art-lightbox-info">
    <div id="art-lightbox-title"></div>
    <div id="art-lightbox-meta"></div>
    <div id="art-lightbox-description"></div>
  </div>
</div>

<script id="art-gallery-data" type="application/json">
{{ site.data.art | jsonify | replace: '</', '<\/' }}
</script>

<script>
(function() {
  const data = JSON.parse(document.getElementById('art-gallery-data').textContent);

  const seriesModal = document.getElementById('art-series-modal');
  const seriesTitle = document.getElementById('art-series-title');
  const seriesMeta = document.getElementById('art-series-meta');
  const seriesDesc = document.getElementById('art-series-description');
  const seriesGrid = document.getElementById('art-series-grid');

  const lb = document.getElementById('art-lightbox');
  const lbImg = document.getElementById('art-lightbox-img');
  const lbTitle = document.getElementById('art-lightbox-title');
  const lbMeta = document.getElementById('art-lightbox-meta');
  const lbDesc = document.getElementById('art-lightbox-description');
  const lbPrev = document.getElementById('art-lightbox-prev');
  const lbNext = document.getElementById('art-lightbox-next');

  let activeSeries = null;
  let activeIndex = 0;

  function normalizeImage(img) {
    return (typeof img === 'string') ? { file: img } : img;
  }

  function buildMeta(piece) {
    const parts = [];
    if (piece.year) parts.push(piece.year);
    if (piece.medium) parts.push(piece.medium);
    return parts.join(' · ');
  }

  function setLightboxImage(url) {
    lbImg.style.backgroundImage = "url('" + url + "')";
  }

  function openSinglePiece(piece) {
    activeSeries = null;
    setLightboxImage(piece.image);
    lbTitle.textContent = piece.title || '';
    lbMeta.textContent = buildMeta(piece);
    lbDesc.textContent = piece.description || '';
    lbPrev.hidden = true;
    lbNext.hidden = true;
    lb.hidden = false;
    document.body.style.overflow = 'hidden';
  }

  function openSeriesItem(seriesPiece, index) {
    activeSeries = seriesPiece;
    activeIndex = index;
    const sub = normalizeImage(seriesPiece.images[index]);
    setLightboxImage(sub.file);
    lbTitle.textContent = sub.title || seriesPiece.title || '';
    const metaParts = [(index + 1) + ' / ' + seriesPiece.images.length];
    if (seriesPiece.year) metaParts.push(seriesPiece.year);
    if (seriesPiece.medium) metaParts.push(seriesPiece.medium);
    lbMeta.textContent = metaParts.join(' · ');
    lbDesc.textContent = sub.description || '';
    lbPrev.hidden = (index === 0);
    lbNext.hidden = (index === seriesPiece.images.length - 1);
    lb.hidden = false;
    document.body.style.overflow = 'hidden';
  }

  function openSeriesModal(piece) {
    seriesTitle.textContent = piece.title || '';
    seriesMeta.textContent = buildMeta(piece);
    seriesDesc.textContent = piece.description || '';
    seriesGrid.innerHTML = '';

    piece.images.forEach((img, i) => {
      const sub = normalizeImage(img);
      const tile = document.createElement('a');
      tile.className = 'art-series-tile';
      tile.href = '#';
      tile.style.backgroundImage = "url('" + (sub.thumb || sub.file) + "')";
      tile.setAttribute('aria-label', sub.title || '');
      if (sub.title) {
        const label = document.createElement('span');
        label.className = 'art-series-tile-caption';
        label.textContent = sub.title;
        tile.appendChild(label);
      }
      tile.addEventListener('click', e => {
        e.preventDefault();
        openSeriesItem(piece, i);
      });
      seriesGrid.appendChild(tile);
    });

    seriesModal.hidden = false;
    document.body.style.overflow = 'hidden';
  }

  function closeLightbox() {
    lb.hidden = true;
    lbImg.style.backgroundImage = '';
    if (seriesModal.hidden) document.body.style.overflow = '';
  }

  function closeSeriesModal() {
    seriesModal.hidden = true;
    document.body.style.overflow = '';
  }

  document.querySelectorAll('.art-tile').forEach(tile => {
    tile.addEventListener('click', e => {
      e.preventDefault();
      const idx = parseInt(tile.dataset.index, 10);
      const piece = data[idx];
      if (piece.images && piece.images.length > 0) {
        openSeriesModal(piece);
      } else {
        openSinglePiece(piece);
      }
    });
  });

  document.querySelectorAll('[data-close]').forEach(btn => {
    btn.addEventListener('click', e => {
      e.stopPropagation();
      if (btn.dataset.close === 'lightbox') closeLightbox();
      if (btn.dataset.close === 'series') closeSeriesModal();
    });
  });

  lb.addEventListener('click', e => { if (e.target === lb) closeLightbox(); });
  seriesModal.addEventListener('click', e => { if (e.target === seriesModal) closeSeriesModal(); });

  lbPrev.addEventListener('click', e => {
    e.stopPropagation();
    if (activeSeries && activeIndex > 0) openSeriesItem(activeSeries, activeIndex - 1);
  });
  lbNext.addEventListener('click', e => {
    e.stopPropagation();
    if (activeSeries && activeIndex < activeSeries.images.length - 1) {
      openSeriesItem(activeSeries, activeIndex + 1);
    }
  });

  document.addEventListener('keydown', e => {
    if (!lb.hidden) {
      if (e.key === 'Escape') closeLightbox();
      else if (e.key === 'ArrowLeft' && activeSeries && activeIndex > 0) {
        openSeriesItem(activeSeries, activeIndex - 1);
      } else if (e.key === 'ArrowRight' && activeSeries && activeIndex < activeSeries.images.length - 1) {
        openSeriesItem(activeSeries, activeIndex + 1);
      }
    } else if (!seriesModal.hidden && e.key === 'Escape') {
      closeSeriesModal();
    }
  });
})();
</script>

{% else %}
*A galeria está vazia. Adiciona obras em `_data/art.yml`.*
{% endif %}
