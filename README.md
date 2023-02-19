# Jekyll Curate Docs

# Table of Contents

   * [Install](#Install)
   * [Theme Colors and Fonts](#theme-colors-and-fonts)
   * [Logo](#logo)
   * [Header](#header)
   * [Dark Mode](#dark-mode)
   
# Install

### Install Ruby

Make sure you have Ruby & RubyGems installed - For a step-by-step guide, read Jekyll docs [installation](https://jekyllrb.com/docs/installation/)

### Install Theme

Once you have purchased the theme simply extract the .zip file on your local machine.

    bundle install
    bundle exec jekyll build
    

### Develop Locally

Run `jekyll serve` or `bundle exec jekyll serve` to start the Jekyll server.

    bundle exec jekyll serve
    

You can visit `http://localhost:4000` in the browser to see the local development site.
   
**[⬆ back to top](#table-of-contents)**

# Theme Colors and Fonts

Jekyll Advance uses variables for typical global theme settings, such as colors and fonts. It’s easy to change the theme to your brand color and typography.

You can edit these variables in the `_config.yml`

Editing theme colors
--------------------

You can edit the main theme colors in the `_config.yml`

    # _config.yml
```yml
    colors:
      primary: '#0d042b'
      primary_text: '#fdfcf9'
      background: '#fdfcf9'
      background_2: '#f7f6ed'
      background_3: '#faebd7'
      text: '#0d042b'
      text_2: '#3b364c'
````

Editing theme fonts
-------------------

This theme uses Google Fonts. If you want to use different fonts, visit the Google fonts website, select your fonts, then copy and paste the `<link>` code snippet into the `google_fonts` field in the `_config.yml`. Below this field update the `heading`, `base` and `monospace` fields with the name of the new font.

    # _config.yml
```yml 
    fonts:
      google_fonts: 'https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;700&family=Fira+Mono&display=swap'
      heading: 'DM Sans'
      base: 'DM Sans'
      monospace: 'Fira Mono'
      logo: 'DM Sans'
```

# Logo

The logo can be either text or an image or both together. You can control the visibility for both desktop and mobile.

Image Logo
----------

To update the logo, copy your logo files to the `assets/images/logo` folder. You can simply overwrite the existing files.

There are 4 logo variations for mobile and inverted (white) states.

* `assets/images/logo/logo.png` _Desktop logo_
* `assets/images/logo/logo-mobile.png` _Mobile logo, typically the smaller icon version of your logo “the mark”_
* `assets/images/logo/logo-invert.png` _Desktop logo in white, for use when the header is transparent_
* `assets/images/logo/logo-invert-mobile.png` _Mobile logo in white_

If you want to use different filenames for your logo you can update the path to the logos in the `_config.yml`. You can use .svg or other file extensions.

Text Logo
---------

If you prefer to use a text logo update the `logo_text` property and ensure that `show_logo_text_on_mobile` or `show_logo_text_on_desktop` is true

Logo Config
-----------

    # _config.yml
```yml
    logo:
      logo_text: 'Jekyll Curate'
      logo_image: assets/images/logo/logo.png
      logo_image_mobile: assets/images/logo/logo-mobile.png
      logo_image_invert: assets/images/logo/logo-invert.png
      logo_image_invert_mobile: assets/images/logo/logo-invert-mobile.png
      logo_image_desktop_height: '28px'
      logo_image_desktop_width: '28px'
      logo_image_mobile_height: '28px'
      logo_image_mobile_width: '28px'
      show_logo_image_on_mobile: true
      show_logo_image_on_desktop: true
      show_logo_text_on_mobile: false
      show_logo_text_on_desktop: false
```

#

This theme has a versatile header that can be static or fixed.

### Fixed header

    # _config.yml
    ...
    
    header: 
      fixed: true
    

### Animate on scroll

Setting the header to fixed will enable animate on scroll.

# Dark Mode

Dark mode is enabled by default. Dark mode can be disabled in `_config.yml`

    # _config.yml
    
    darkmode:
      enable_dark_mode: true
      show_dark_mode_toggle_in_header: true 
      show_dark_mode_toggle_in_bottom: false # displays the dark mode toggle switch in the footer and allows the user to manually change the mode
      show_dark_mode_toggle_in_mobile_menu: false # displays the dark mode toggle switch in the footer and allows the user to manually change the mode
    

### Automatic Dark Mode

Darkmode detects the users OS dark mode preferences automatically. We use `prefers-color-scheme` ([Mozilla Docs - prefers color scheme](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)) to achieve this.

Try changing your dark mode preference in OSX.

![Mac OSX Dark mode settings](darkmode-mac.png#border)

### Dark Mode logic

If a user specifically toggles to dark or light mode this preference will be remembered and **will override the system preference**. This setting is stored in the users sessionStorage ([Mozilla Docs - sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)) which means the preference is remembered across pages and page reloads, until the user closes their browser or clears their cache.
