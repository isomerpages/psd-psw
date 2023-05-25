---
title: About Discovering Good@Work
permalink: /discovering-goodatwork/permalink/discovering-about/
description: ""
---
![](/images/JS%20Gen/about%20js.png)Discovering Good@Work Job Sprint is an opportunity for public officers to sign up for short 0.5- to 2-day job immersion programmes to find out more about public sector jobs that involve transformation and/or cross-agency work. The programmes can either be physical or virtual.

#### Objectives
* For public officers to learn more about transformative and/or inter-agency work.

* Opportunity for public officers to witness transformation on the ground.
 
* Allows officers to experience a real sense of change and contribute ideas towards ongoing transformation initiatives.  

* Strengthens cross-learning among agencies.



![](/images/10.jpg)
![](/images/1.jpg)

      }
    
    // fist we need to ask DOM for all p &gt; img tags
    let imgs = document.querySelectorAll('P &gt; IMG');
    for (let i = 1; i &lt; imgs.length; i++) {
      let h = imgs[i].naturalHeight;
      let w = imgs[i].naturalWidth;
      let pe = imgs[i].previousElementSibling;
      if (!pe) {
        continue;
      }
      if (pe.nodeName != "IMG") {
        continue;
      }
      let sh = pe.naturalHeight;
      let sw = pe.naturalWidth;
      if (sw != w || sh != h) {
        continue;
      }
      if (imgs[i].carousel) {
        continue;
      }
      if (!pe.carousel) {
        pe.carousel = [ pe ];
        setCarousel(pe);
      }
      pe.carousel.push(imgs[i]);
      imgs[i].carousel = pe.carousel;
      setCarouselEvents(imgs[i]);
      // set parent size
      pe.parentElement.style.minWidth = "calc(" + sw + "px + 2em)";
      pe.parentElement.style.minHeight = "calc(" + sh + "px + 2em)";
    }