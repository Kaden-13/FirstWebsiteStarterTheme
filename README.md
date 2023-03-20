# [Alembic](https://alembic.darn.es/)
[![Gem Version](https://badge.fury.io/rb/alembic-jekyll-theme.svg)](https://badge.fury.io/rb/alembic-jekyll-theme)

⚗ A Jekyll boilerplate theme designed to be a starting point for any Jekyll website.

![Screenshot](https://raw.githubusercontent.com/daviddarnes/alembic/master/screenshot.png)

[<img src="https://cdn.buymeacoffee.com/buttons/default-yellow.png" width="217"/>](https://buymeacoffee.com/daviddarnes#support)

## Contents
- [About](#about)
- [Features](#features)
- [Examples](#examples)
- [Installation](#installation)
- [Customising](#customising)
- [Configuration](#configuration)
  - [Gem dependency settings](#gem-dependency-settings)
  - [Site settings](#site-settings)
  - [Site performance settings](#site-performance-settings)
  - [Site navigation](#site-navigation)
  - [Custom fonts](#custom-fonts)
- [Using includes](#using-includes)
- [Page layouts](#page-layouts)
- [Page and Post options](#page-and-post-options)
- [Credits](#credits)

## About Me

I turned 20 this year, and I have lived in utah my whole life. Although, I love to travel and visit new places. Some of the places that I really want to visit are:[Australia](https://www.state.gov/wp-content/uploads/2022/02/shutterstock_1025960785-2560x1300.jpg), [Japan](https://www.japan.travel/en/), [Korea](https://english.visitkorea.or.kr/). All of those places just seem like amazing places to explore and have fun for a while. Other than that I have been to many different states.



## Sports

Growing up I played sports such as: `Basketball`, `Football`, and `Baseball` and in doing so I've had a lot of opportunites to travel and expirience new things. Places I have been to include California, Idaho, Vegas, and Arizona. Sports in my opinion teach you a lot about how a family should function, how you need to talk/treat the people around, and how to work hard for what you want.

## Accident Prone

When I was a kid in grade school from around 3rd grade - 6th grade, I had around 5 major injuries. Some still affect me today. Although, not significantly like most people would think. Now, my first injury that started it all was a [Buckle Fracture](https://www.rch.org.au/kidsinfo/fact_sheets/Fracture_care_buckle_injury/#:~:text=A%20buckle%20fracture%20in%20the,heal%20quickly%20without%20any%20problems.) that I got messing around on a tramp and tried to cath myself when I was bounce around 15 feet in the air by my older brother and his friend. After that came a [Torn Achilles](https://www.mayoclinic.org/diseases-conditions/achilles-tendon-rupture/symptoms-causes/syc-20353234) I got from my friend landing on the back of my foot when he was trying to be funny and jumped on me, while i was getting up. Next, I happend to [Hyperextend](https://my.clevelandclinic.org/health/diseases/22481-hyperextended-knee#:~:text=A%20hyperextended%20knee%20is%20an,place%20and%20help%20it%20move).) my elbow and broke two bones and barely missed my [Growth Plate](https://www.niams.nih.gov/health-topics/growth-plate-injuries#:~:text=The%20growth%20plate%20is%20the,longer%20than%20they%20are%20wide.). Those are the most painful out of them, but I had two major [Concussions](https://www.cdc.gov/headsup/basics/concussion_whatis.html#:~:text=Print-,What%20Is%20a%20Concussion%3F,move%20rapidly%20back%20and%20forth.) that absolutely are the scariest of them, because concussions can cause permanent brain damage or damage your memory retention.

## Configuration

There are a number of optional settings for you to configure. Use the example [`_config.yml`](https://github.com/daviddarnes/alembic/blob/master/_config.yml) file in the repo and use the documentation below to configure your site:

### Gem dependency settings

`twitter`, `author` and `social` values will need to be changed to the projects' social information or removed. Look for the `Gem settings` comment within the `/_config.yml` file. These values are for the [jekyll-seo-tag](https://github.com/jekyll/jekyll-seo-tag) - follow the link to find out more.

### Site settings

You'll need to change the `description`, `title` and `url` to match with the project. You'll also need to replace the logos, default social and default offline images in the `/assets/` directory with your own graphics. Setting the site language can be done with `lang`, the theme will default to `en-US`. The `email` needs to be changed to the email you want to receive contact form enquires with. The `disqus` value can be changed to your project username on [Disqus](https://disqus.com), remove this from the `/_config.yml` file if you don't want comments enabled. Look for the `Site settings` comment within the `/_config.yml` file. The `repo` setting is optional, for now, and can be removed entirely, if you wish.

Google Analytics can be enabled via the site configuration too. Add your tracking ID to the `/_config.yml` file in the following method: `google_analytics: 'UA-XXXXXXXX-1'`. By default all IPs of site visitors are anonymous to maintain a level of privacy for the audience. If you wish to turn this off set the `google_analytics_anonymize_ip` key to `false`.

Date format can be customised in the `/_config.yml` with the option `date_format` (please refer to Liquid date filters documentation for learning about formatting possibilities). Only placeholder formatting is supported, do not try to use ordinal dates introduced in Jekyll 3.8.

The `short_name` option within `/_config.yml` is to add a custom name to the site's web application counterpart. When the website is added to a device this name will appear alonside the app icon. The short name will default to the site title if this isn't set.

### Site performance settings

Alembic comes with a couple of options to enhance the speed and overall performance of the site you build upon it.

By default the built in Service Worker is enabled, and will work on a 'network first' method. Meaning if there's no internet connection the content the Service Worker has cached will be used until the connection comes back. It will always look for a live version of the code first. To disable the Service Worker add an option called `service_worker` with a value of `false` in the `/_config.yml` file.

Another option to speed up Alembic is to enable inline CSS, which is off by default. You can enable this by setting `css_inline: true` inside your `/_config.yml` file. By switching to inline styles you bypass the use `/assets/styles.scss`, any custom styles will need to be added in `/_includes/site-styles.html` or in a new custom file.

Please note that these options aren't a "silver bullet" for making your site faster, make sure to audit and debug your site to get the best performance for your situation.

### Site navigation

There are a total of 4 different navigation types:

- `navigation_header`: The links shown in the header (it is also used on the 404 page)
- `navigation_footer`: The links shown in the footer
- `social_links`: The social icon links that are shown in the sidebar
- `sharing_links`: The social sharing buttons that are shown at the bottom of blog posts

All navigations can be edited using the `_config.yml` file. To see example usage either look for the `Site navigation` comment within the `/_config.yml` file or see [the nav-share.html include](#nav-sharehtml).

If there are no items for the `navigation_header` or `navigation_footer`, they will fallback to a list of pages within the site. The `social_navigation` properties should either be one that is already in the list (so `Twitter` or `Facebook`) or a regular `link`, this is so an icon can be set for the link.

### Custom fonts

Alembic comes with custom fonts served from Google fonts. By default it requests Merriweather but this can be any font from any provider assuming it supports requesting fonts in the same manner and does not require javascript.

This can be configured under the `custom_fonts` key.

- `urls`: The urls supplied to you from your font provider (eg https://fonts.googleapis.com/css2?family=Merriweather). For best performance try to use as few urls as possible
- `preconnect`: (optional) If your font provider serves the font files from another domain it can be useful to make a connection to that domain in advance. For example google load the font files from fonts.gstatic.com. This can be omitted if not required

If you want to customise this further you can find the include for custom fonts in `_includes/site-custom-fonts.html`.

## Using includes

There are 2 main types of includes: ones designed for the site and ones that are designed as shortcodes. Here are a list of the shortcode includes:


