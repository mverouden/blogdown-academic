---
# Slider widget.
widget: slider

# Activate this widget? true/false
active: false

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 1

# Slide interval.
# Use `false` to disable animation or enter a time in ms, e.g. `5000` (5s).
interval: false

# Slide height (optional).
# E.g. `500px` for 500 pixels or `calc(100vh - 70px)` for full screen.
height: 300px

# Slides.
# Duplicate an `[[item]]` block to add more slides.
item:
  - title: Hello
    content: 'I am center aligned :smile:'
    align: center  # Choose `center`, `left`, or `right`.
    # Overlay a color or image (optional).
    #   Deactivate an option by commenting out the line, prefixing it with `#`.
    overlay_color: '#666'  # An HTML color value.
    overlay_img: bubbles-wide.jpg  # Image path relative to your `assets/media/` folder.
    overlay_filter: 0.5  # Darken the image. Value in range 0-1.
    # Call to action button (optional).
    #   Activate the button by specifying a URL and button label below.
    #   Deactivate by commenting out parameters, prefixing lines with `#`.
    cta_label: Download my app
    cta_url: 'https://example.org'
    cta_icon_pack: fas
    cta_icon: graduation-cap
  - title: Left
    content: 'I am left aligned :smile:'
    align: left
    overlay_color: '#555'  # An HTML color value.
    overlay_img: '' # Image path relative to your 'assets/media/` folder.
    overlay_filter: 0.5 # Darken the image. Value in range 0-1.
  - title: Right
    content: 'I am right aligned :smile:'
    align: right
    overlay_color: '#333' # An HTML color value.
    overlay_img: ''  # Image path relative to your `assets/media/` folder.
    overlay_filter: 0.5 # Darken the image. Value in range 0-1.

design:
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
