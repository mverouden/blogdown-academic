---
# An instance of the Contact widget.
widget: contact

# Activate this widget? true/false
active: true

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 130

title: Contact
subtitle:

content:
  # Automatically link email and phone or display as text?
  autolink: true

  # Email form provider
  form:
    provider: formspree
    formspree:
      id: maikel.verouden@gmail.com
    netlify:
      # Enable CAPTCHA challenge to reduce spam?
      captcha: false

  # Contact details (edit or remove options as required)
  email: # maikel.verouden@gmail.com
  phone: # +31 317 4 81861
  address:
    street: 'Wageningen University & Research (Biometris), Droevendaalsesteeg 1 (Building 107 a.k.a. Radix) '
    city: 'Wageningen'
    region: 'Gelderland'
    postcode: '6708 PB'
    country: The Netherlands
    country_code: NL
  coordinates:
    latitude: '51.986513'
    longitude: '5.663702'
  directions: 'Room: W4.Ad.011 (Radix West 4th Floor)'
  office_hours: # 'Monday--Friday 08:30h to 17:30h'
    - 'Monday--Tuesday--Thursday--Friday from 08:30h to 17:30h'
    - 'Wednesday from 07:00h to 13:30h'
  # appointment_url: 'https://calendly.com'
  contact_links:
    # - icon: paper-plane
    #   icon-pack: fas
    #   name: 'E-mail Me'
    #   link: 'mailto:maikel.verouden@wur.nl'
    - icon: skype
      icon_pack: fab
      name: 'Contact Me on Skype'
      link: 'skype:aquarius0174?call'
    - icon: microsoft
      icon_pack: fab
      name: Call Me directly on Microsoft Teams
      link: "callto:maikel.verouden@wur.nl"
    # - icon: skype
    #   icon_pack: fab
    #   name: 'Contact Me on Skype for Business'
    #   link: 'sip:maikel.verouden@wur.nl'
    - icon: twitter
      icon_pack: fab
      name: 'Direct Message @mverouden'
      link: 'https://twitter.com/messages/compose?recipient_id=91304466'
    # - icon: keybase
    #   icon_pack: fab
    #   name: Chat on Keybase
    #   link: 'https://keybase.io/'
    # - icon: comments
    #   icon_pack: fas
    #   name: Discuss on Forum
    #   link: 'https://discourse.gohugo.io'
    # - icon: video
    #   icon_pack: fas
    #   name: Zoom Me
    #   link: 'https://zoom.com'

design:
  background:
    # Background color.
    # color: navy
    # Background gradient.
    # gradient_start: DeepSkyBlue
    # gradient_end: SkyBlue
    # Background image.
    # image: headers/bubbles-wide.jpg  # Name of image in `static/media/`.
    # image_darken: 0.6  # Darken the image? Range 0-1 where 0 is transparent and 1 is opaque.
    # Text color (true=light or false=dark).
    # text_color_light: true
  columns: '2'

advanced:
  # Custom CSS.
  # css_style: ""
  # CSS Class.
  # css_clas: ""
---
