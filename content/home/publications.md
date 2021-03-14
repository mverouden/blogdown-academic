---
# An instance of the Pages widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: pages

# Activate this widget? true/false
active: true

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 90

title: Recent Publications
subtitle: ''

content:
  # Page type to display. E.g. post, talk, publication...
  page_type: publication
  # Choose how much pages you would like to display (0 = all pages)
  count: 5
  # Choose how many pages you would like to offset by
  offset: 0
  # Page order: descending (desc) or ascending (asc) date.
  order: desc
  # Filter on criteria
  filters:
    tag: ''
    category: ''
    publication_type: ''
    author: ''
    exclude_featured: false
design:
  # Choose a view for the listings:
  #   1 = List
  #   2 = Compact
  #   3 = Card
  #   4 = Citation (publication only)
  view: 2
  background:
    # Background color.
    #color: navy
    # Background gradient.
    #gradient_start: DeepSkyBlue
    #gradient_end: SkyBlue
    # Background image.
    #  Name of image in `assets/media/`.
    #image: bubbles-wide.jpg
    # Darken the image? Range 0-1 where 0 is transparent and 1 is opaque.
    #image_darken: 0.6 
    # Text color (true=light or false=dark).
    #text_color_light: true
  spacing:
    # Customize the section spacing. Order is top, right, bottom, left.
    #padding: ["20px", "0", "20px", "0"]
advanced:
  # Custom CSS.
  #css_style: ''
  # CSS Class.
  #css_clas: ''
---

{{% callout note %}}
Quickly discover relevant content by [filtering publications](./publication/).
{{% /callout %}}
