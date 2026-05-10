# Collection conventions: _topics/ and _works/

## Folder structure

Each topic or work is a FOLDER, not a single file:

    _topics/consciousness/
    ├── _meta.yml         (shared metadata, optional)
    ├── en.md             (English version)
    ├── fr.md             (French version)
    ├── pt.md             (Portuguese version)
    └── (subtopic-folders)/
        ├── en.md
        └── ...

Languages are OPTIONAL per item. A topic or work can exist in:
- All three languages
- Just one (e.g., a French-only novel)
- Two
- Default fallback: when a visitor lands on /topics/foo/ Jekyll serves
  whichever language file exists (preference: en > fr > pt).

## Front-matter fields

Required:
  title:        the display title
  lang:         pt | fr | en
  order:        integer, controls position in index (lower = earlier)

Recommended:
  description:  one-liner shown on cards
  cover:        path to an image (16:10 ratio works best)

For works specifically:
  status:       published | in-progress | draft
  genre:        e.g. roman, conto, ensaio
  year:         publication or expected year
  buy_url:      link to buy/order

For topics specifically:
  icon:         Font Awesome class, e.g. "fas fa-brain"
  badge:        small label on the card (e.g., subtopic count)

## Adding content

To add a new topic in EN+PT:
  mkdir -p _topics/my-topic
  # create en.md and pt.md with proper front matter

To add a French-only novel:
  mkdir -p _works/my-novel
  # create only fr.md
  
