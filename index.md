---
title: Pullfolio FAQ
layout: default
---

FAQ
===

**Q: How do I create a custom theme?**  
A: Check our [Pullfolio Theme Howto Page](/theme-howto.html)

**Q: Can I remove the Flickr Link in my portfolio site?**  
A: The link is there because we serve photos directly off Flickr, per [Flickr community guidelines](http://www.flickr.com/guidelines.gne), you must link back to Flickr when you do that:
> **Do link back to Flickr when you post your Flickr content elsewhere.**  
> The Flickr service makes it possible to post content hosted on Flickr to outside web sites. However, **pages on other web sites that display content hosted on flickr.com must provide a link from each photo or video back to its page on Flickr**.

**Q: My custom domain doesn't work!**  
A: For custom domain to work, you must update your domain records to setup a **CNAME** record for that hostname to point to **pullfolio.com**, if you are using your top-level domain, you also have to create an **A record** that points to our IP address: **75.101.165.33** After this is setup, it might also take a day or 2 for the DNS records to update.

**Q: How do I link my Flickr account with Pullfolio?**  
A: You typically link your accounts upon signup, if you want to do it again, go to [http://pullfolio.com/oauth_consumers/flickr/](http://pullfolio.com/oauth_consumers/flickr/)

**Q: My new photos are not showing up at my site!**  
A: This is because we cache the portfolio photos for 24 hours, you can manually refresh the cache with the *Refresh Cache* link in your [Portfolio admin page](http://pullfolio.com/portfolios/admin).

**Q: Do private photos show up in my site?**  
A: Yes they do! If you don't want a photo to appear on the site, don't tag it (if you setup your portfolio to pull from tag) or include it in the photoset (if you're pulling from a photoset).


_More soon..._