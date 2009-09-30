---
title: Pullfolio Themes Howto
layout: default
---

<a href="http://github.com/ayn/pullfolio-theme-howto"><img style="position: absolute; top: 0; right: 0; border: 0;" src="http://s3.amazonaws.com/github/ribbons/forkme_right_darkblue_121621.png" alt="Fork me on GitHub" /></a>


Pullfolio.com Themes Howto
================================
This repository provides information of how [Pullfolio](http://pullfolio.com) custom themes work. After upgrading to a **trial** or purchasing a **pro** subscription, you will be able to clone one of the provided themes and modify from there, or create a new theme from scratch (only recommended for experts!). You have complete control of the look and feel of your Pullfolio site by customizing the theme files.

Overview on theme directory structure
-------------------------------------
<pre>
[theme name]
   |__ assets
   |__ layouts
   |__ templates
</pre>

The _assets_ folder contains your CSS stylesheets:

  * _style.css_ - this is loaded for all browsers, and should contain most of the CSS for your theme
  * _ie.css_ - this is loaded for all versions of Internet Explorer
  * _ie6.css_ - this is loaded for IE6 and lower

The _layouts_ folder contains 3 partials:

  * __footer.liquid_ - this is the footer of your site
  * __header.liquid_ - header
  * __sidebar.liquid_ - sidebar, this is empty in most of the default Pullfolio themes

The _templates_ folder contains templates for your site:

  * _about.liquid_ - this is the information displayed in the About page (http://yoursite.com/about)
  * _contact.liquid_ - this should contain contact info, the *@contact_form* instance variable contains a default contact form for you to receive email inquiries
  * _portfolios.liquid_ - this is rendered at http://yoursite.com/portfolios, if you want to have a page that display all (or a selection of) your portfolios, if you create one, you should add a link to this in __header.liquid_
  * _portfoilio.liquid_ - this is the most important file in a theme, it is used to display a portfolio
  
Variables you have access to in a theme
---------------------------------------
In all pages, you have access to the follow variables:

  * _portfolio_ - current or default portfolio
    * _name_ - name of portfolio
    * *artist_statement*
    * _photos_ - array of photos
    * *friendly_id* - url format of this portfolio
  * _user_
    * _login_, _email_, *site_title*, *site_description*, _agent_, _bio_, _phone_, _blog_, *friendly_id*, *custom_domain*
    * *has_blog?*, *has_agent?*, *has_phone?* - returns true if you have entered blog, agent, and phone, respectively in account info
  * _photos_ - essentially the same as portfolio.photos, you would typically use a for loop to list all of them in *portfolio.liquid*, each of these photos contains:
    * _title_ - title of image
    * _description_ - photo description
    * _photopage_url_ - this is the URL to the Flickr photopage, to satisfy [Flickr's guidelines](http://www.flickr.com/guidelines.gne), **you must include a link back to Flickr when you display any image off of Flickr**
    * *url_square*, *url_thumbnail*, *url_small*, *url_medium*, *url_original* - URLs to different sizes of the image
    * *url_large* - provides URL to the large size image if available, otherwise, it returns URL to the medium
  * in _contact.liquid_, you have access to:
    * *@contact_form* - if you display this instance variable it will include a email contact form, you can style it with CSS if you so desire
  * in _about.liquid_, you have access to:
    * *@buddy_icon* - this is the URI of your Flickr buddy icon

Available Liquid filters
------------------------
  * *display_galleriffic(portfolio)* - display [gallerrific](http://www.twospy.com/galleriffic/) code block for a given portfolio, you invoke this by
      { portfolio | display_galleriffic }
  * *asset_url(asset)* - this provides a URI to something in the assets folder
  * *link_to_page*, *link_to_portfolio* - provides links to page or portfolio, see _header.liquid for how to use them
  
Example Themes
==============
signature-on-black
------------------
This is the code of our _Signature on Black_ theme, it uses our helpers (aka Liquid filters) to provide optimized performance by utility MemCached.

signature-on-black-without-filters
----------------------------------
This is the same signature-on-black theme with a re-written _portfolio.liquid_ to show how to go through the photos of the portfolio to generate the HTML block:

<script src="http://gist.github.com/198407.js"></script>

Download
--------
You can download these theme examples in either [zip](http://github.com/ayn/pullfolio-theme-howto/zipball/master) or [tar](http://github.com/ayn/pullfolio-theme-howto/tarball/master) formats:

<div class="download">
  <a href="http://github.com/ayn/pullfolio-theme-howto/zipball/master">
    <img border="0" width="90" src="http://github.com/images/modules/download/zip.png"></a>
  <a href="http://github.com/ayn/pullfolio-theme-howto/tarball/master">
    <img border="0" width="90" src="http://github.com/images/modules/download/tar.png"></a>
</div>

You can also clone the project with [Git](http://git-scm.com) by running:
    $ git clone git://github.com/ayn/pullfolio-theme-howto

You can also view the source code [on GitHub](http://github.com/ayn/pullfolio-theme-howto).

Useful links
============
  * [Liquid Templating Language](http://www.liquidmarkup.org/) - you can learn all about Liquid here
  * [jQUery](http://jquery.com/)
  * [jQuery UI](http://jqueryui.com/)
  * [Galleriffic](http://www.twospy.com/galleriffic/)

Contributors
============
  * [Raymond Law](http://rayvinly.com)
  * [Andrew Ng](http://blog.andrewng.com)

&copy; 2009 [Pullfolio.com](http://pullfolio.com), themes examples are released under the MIT license