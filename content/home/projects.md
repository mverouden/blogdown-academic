---
# An instance of the Portfolio widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: portfolio

# Activate this widget? true/false
active: true

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 65

title: Projects
subtitle:

content:
  # Page type to display. E.g. project.
  page_type: project

  # Default filter index (e.g. 0 corresponds to the first `filter_button` instance below).
  filter_default: 0

  # Filter toolbar (optional).
  # Add or remove as many filters (`filter_button` instances) as you like.
  # To show all items, set `tag` to "*".
  # To filter by a specific tag, set `tag` to an existing tag name.
  # To remove the toolbar, delete the entire `filter_button` block.
  filter_button:
  - name: All
    tag: '*'
  - name: Deep Learning
    tag: Deep Learning
  - name: Other
    tag: Demo

design:
  # Choose how many columns the section has. Valid values: '1' or '2'.
  columns: '2'

  # Toggle between the various page layout types.
  #   1 = List
  #   2 = Compact
  #   3 = Card
  #   5 = Showcase
  view: 2

  # For Showcase view, flip alternate rows?
  flip_alt_rows: false
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
  #css_style: ""
  # CSS Class.
  #css_clas: ""
---
