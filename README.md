# Jekyll Curate Pro Docs

Develop by [Cyberassemble](https://github.com/cyberassemble).

Join our telegram channel [CYBERASSEMBLE](https://t.me/cyberassemble)

### Support us by donate BTC

BTC Address
```
3JMLc8iTVnQKgYyNNpqXRZbqkDw4Xp5fLW
```

# Table of Contents

   * [Install](#Install)
   * [Theme Colors and Fonts](#theme-colors-and-fonts)
   * [Logo](#logo)
   * [Header](#header)
   * [Dark Mode](#dark-mode)
   * [Comments](#comments)
   * [Newsletter](#newsletter)
   * [Footer](#footer)
   * [Main Menu](#main-menu)
   
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
```yml
    header: 
      fixed: true
```

### Animate on scroll

Setting the header to fixed will enable animate on scroll.

# Dark Mode

Dark mode is enabled by default. Dark mode can be disabled in `_config.yml`

    # _config.yml
```yml 
    darkmode:
      enable_dark_mode: true
      show_dark_mode_toggle_in_header: true 
show_dark_mode_toggle_in_bottom: false # displays the dark mode toggle switch in the footer and allows the user to manually change the mode
      show_dark_mode_toggle_in_mobile_menu: false # displays the dark mode toggle switch in the footer and allows the user to manually change the mode
```

### Automatic Dark Mode

Darkmode detects the users OS dark mode preferences automatically. We use `prefers-color-scheme` ([Mozilla Docs - prefers color scheme](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)) to achieve this.

Try changing your dark mode preference in OSX.

![Mac OSX Dark mode settings](darkmode-mac.png#border)

### Dark Mode logic

If a user specifically toggles to dark or light mode this preference will be remembered and **will override the system preference**. This setting is stored in the users sessionStorage ([Mozilla Docs - sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)) which means the preference is remembered across pages and page reloads, until the user closes their browser or clears their cache.


#

2 different contact forms are available on the contact page.

Netlify Form
------------

By default the theme uses [Netlify forms](https://www.netlify.com/products/forms/). If you are hosting your site on Netlify and have `use_netlify_form` enabled the form will work automatically with Netlify forms.

    # _config.yml
```yml 
    contact_form: 
      use_netlify_form: true
      use_formspree_form: false
      formspree_endpoint: ""
```

Formspree
---------

You can optionally turn on Formspree forms. disable Netlify forms and add your formspree endpoint for the form your created in formspree.

    # _config.yml
```yml   
    contact_form: 
      use_netlify_form: false
      use_formspree_form: true
      formspree_endpoint: https://formspree.io/f/moqyklqv
```

**[⬆ back to top](#table-of-contents)**

# Comment

Comments are powered by [Disqus](https://disqus.com/)

Comments can be enabled on blog posts by adding your disqus shortname to the `_config.yml`

    # _config.yml
```yml
    disqus:
      shortname: "zerostatic" # Your disqus shortcode. leave this blank to disable comments globally
``
    

Comments Per Post
-----------------

Comments can be disabled on a per post basis. In the blog posts frontmatter set `comments: false`

    # collections/_posts/2021-07-20-targeting-keywords-for-traffic.md
    ---
    ...
    comments: false
    ---
    
# Newsletter

Newsletter subscription is powered by [Mailchimp](https://mailchimp.com/)

The subscrine box can be enabled on the homepage and blog posts by adding your mailchimp form url to the `_config.yml`

Note that you must explicity enable the subcribe box on each page.

    # _config.yml
```yml
    mailchimp:
      form_action_url: https://zerostatic.us13.list-manage.com/subscribe/post?u=675276692aebec1c007f8156d&amp;id=3e3da720c2
```
    

Comments Per Post
-----------------

The subscribe box can be enabled on the homepage or any blog post. In the pages frontmatter set `subscribe: true`

    # collections/_posts/2021-07-20-targeting-keywords-for-traffic.md
    ---
    ...
    subscribe: true
    ---

# Footer
Footer config
-------------

There are several options to configure the footer from the `_config.yml`

    # _config.yml
    ...
```yml
    footer:
      enable_footer: true # show/hide the entire footer
      footer_title: "Jekyll Curate"
      footer_description: "Curate is a creative portfolio for Jekyll by Zerostatic Themes."
      enable_social_media_icons: true
      enable_menu_footer_primary: true
      enable_menu_footer_secondary: true
      enable_menu_footer_tertiary: false
      footer_primary_menu_title: "Projects"
      footer_secondary_menu_title: "Agency"
      footer_tertiary_menu_title: ""
```

Footer menus
------------

There are 3 menus available in the footer. You can add links to footer menus by editing `_data/menu.yml`

    # _data/menu.yml
```yml
    footer_primary:
      - name: Services
        url: /services/
        weight: 2
      - name: Work
        url: /work/
        weight: 3
      - name: Team
        url: /team/
        weight: 4
    footer_secondary:
      - name: Blog
        url: /posts/
        weight: 1
      - name: About
        url: /about/
        weight: 2
      - name: Privacy Policy
        url: /privacy/
        weight: 3
      - name: Terms and Conditions
        url: /terms-and-condition/
        weight: 4
    footer_tertiary:
      - name: Contact
        url: /contact/
        weight: 1
      - name: Buy Now
        url: https://www.zerostatic.io/theme/jekyll-advance/
        weight: 2
```

# Main Menu

Main Menu config
----------------

There are several options to configure the footer from the `_config.yml`

    # _config.yml
    ...
    
    menu: 
      show_dropdown_items_in_mobile_menu: true
      show_social_media_in_mobile_menu: true
    

Main menu
---------

Configure the main menu by editing `_data/menu.yml`
```yml
    # _data/menu.yml
    
    main:
      - name: Home
        url: /
        weight: 1
      - name: Projects
        url: /projects/
        weight: 2
        child:
          - name: "Project Layout 1"
            icon: "/assets/images/icons/wireframe-7.svg"
            icon_darkmode: "/assets/images/icons/wireframe-7-white.svg"
            description: "Default Project layout"
            url: /projects/project-1/
          - name: "Project Layout 2"
            icon: "/assets/images/icons/wireframe-5.svg"
            icon_darkmode: "/assets/images/icons/wireframe-5-white.svg"
            description: "Right side layout"
            url: /projects/project-2/
          - name: "Project Layout 3"
            icon: "/assets/images/icons/wireframe-6.svg"
            icon_darkmode: "/assets/images/icons/wireframe-6-white.svg"
            description: "Left side layout"
            url: /projects/project-3/
          - name: "Project Layout 4"
            icon: "/assets/images/icons/wireframe-8.svg"
            icon_darkmode: "/assets/images/icons/wireframe-8-white.svg"
            description: "Top layout"
            url: /projects/project-4/
      - name: Blog
        url: /blog/
        weight: 2
      - name: About
        url: /about/
        weight: 3
      - name: Contact
        url: /contact/
        weight: 4
```

Nested / dropdown menu
----------------------

The main menu supports nested menus.

For sub menus to work, you need to nest the menu items under the `child` property when editing the `_data/menu.yml`

    # _data/menu.yml
    main:
    
```yml
      - name: Services
        url: /services/
        weight: 1
        child:
        - name: "Web Development"
          url: "/services/web-development/"
        - name: "Web Design"
          url: "/services/web-design/"
        - name: "UX"
          url: "/services/user-experience/"
        - name: "Branding"
          url: "/services/branding/"
    
```
Responsive / Mobile Menu
------------------------

This theme comes with a high quality responsive menu. This menu uses the `main` menu from `_data/menu.yml`.

**[⬆ back to top](#table-of-contents)**
