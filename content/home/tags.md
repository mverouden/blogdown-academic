---
# An instance of the Tag Cloud widget.
# Docs: https://wowchemy.com/docs/page-builder/
widget: tag_cloud

# Activate this widget? true/false
active: true

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 120

title: Popular Topics
subtitle: ''

content:
  # Choose the taxonomy from `config.toml` to display (e.g. tags, categories)
  taxonomy: tags
  
  # Choose how many tags you would like to display (0 = all tags)
  count: 20

design:
  # Minimum and maximum font sizes (1.0 = 100%).
  font_size_min: 0.7
  font_size_max: 2.0
  # Apply a background color, gradient, or image.
  #   Uncomment (by removing `#`) an option to apply it.
  #   Choose a light or dark text color by setting `text_color_light`.
  #   Any HTML color name or Hex value is valid.
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
