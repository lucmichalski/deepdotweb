---
Firefox 52 Adds a Tor-Like Font Whitelist to Prevent Fingerprinting through OS Fonts
---
<article class="post-listing post-17489 post type-post status-publish format-standard has-post-thumbnail hentry category-deepdot-news category-news-updates tag-4830 tag-adds tag-fingerprinting tag-firefox tag-font tag-fonts tag-os tag-prevent tag-torlike tag-whitelist">
    <div class="post-inner">
    <p class="post-meta">
    <span>Posted by: <a href="https://www.deepdotweb.com/author/caliens/" title="">C. Aliens </a></span>
    <span>January 13, 2017</span>
    <span>in <a href="https://www.deepdotweb.com/category/deepdot-news/" rel="category tag">Featured</a>, <a href="https://www.deepdotweb.com/category/news-updates/" rel="category tag">News Updates</a></span>
    <span><a href="https://www.deepdotweb.com/2017/01/13/firefox-52-adds-tor-like-font-whitelist-prevent-fingerprinting-os-fonts/#respond">Leave a comment</a></span>
    </p>
    <div class="clear"></div>
    <div class="entry">
    <p>Researchers from Mozilla scheduled a release for a stable build of Firefox 52—this build’s significance came from a Tor-esque privacy implementation. In the user-submitted bug report, <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1121643">Bug 1121643</a> from 2015, a user posted that a system’s fonts exposed information about that user. Then, Tor developers, as another user commented, issued a patch to “<a href="https://gitweb.torproject.org/tor-browser.git/commit/?h=tor-browser-38.1.0esr-5.0-1&amp;id=2a36205b70076fc26145400addaa383142d71c81">Bug #13313: Pref &#8216;font.system.whitelist</a>.&#8217;” Tor’s patch to the font fingerprinting initially landed in a remote tracking branch of an early version—<a href="https://gitweb.torproject.org/tor-browser.git/tag/?h=tor-browser-38.1.0esr-5.0-1&amp;id=tor-browser-38.1.0esr-5.0-1-build3">5.0-1-build3</a>—of tor-browser-38.1.0esr-5.0-1. And the “bug fix,” if you will, has stayed with Tor since and will become a part of Firefox as of March 7, 2017.</p>
    <p><img class="wp-image-17491 aligncenter" src="https://www.deepdotweb.com/wp-content/uploads/2017/01/word-image-4.jpeg" srcset="https://www.deepdotweb.com/wp-content/uploads/2017/01/word-image-4.jpeg 526w, https://www.deepdotweb.com/wp-content/uploads/2017/01/word-image-4-300x173.jpeg 300w" sizes="(max-width: 526px) 100vw, 526px" /> Browser fingerprinting, just like any form of de-anonymization, is not a new type of internet tracking. In many recent cases, the issue relied heavily on human error. Granted, the de-anonymization or pseudo-identification of a browser’s user works both ways. Firefox often pulled privacy techniques from Tor developers and builds and in turn Tor relied on Mozilla’s Firefox Extended Support Release builds to compose the Tor Browser Bundle.</p>
    <p>A primary relationship, security-wise, began to grow between both organizations after the <a href="https://www.deepdotweb.com/2016/06/28/fbi-is-trying-to-hide-their-tor-exploit-for-good/">FBI refused to disclose their Tor exploit</a>—one that also affected Firefox users. Firefox developers started working on the “Tor Uplift project” that ultimately aimed to reduce <a href="https://www.deepdotweb.com/2016/07/10/mozilla-implementing-tor-privacy-features-firefox-builds/">fingerprinting in Firefox builds</a>. The fixes first implemented were often basic ones. For instance: if a website requested the variable “screen.orientation.angle” from a Firefox user, Firefox started returning the virtually worthless value of “0.”</p>
    <p>Similarly, in 2016, security researcher Jose Carlos Norte demonstrated a javascript flaw in Tor that allowed fingerprinting through page scrolling. Threat actors, in theory, could take advantage of a security flaw like the one Norte disclosed. He notably pointed out that most known methods of browser fingerprinting originated from issues with javascript implementation. We covered the potential <a href="https://www.deepdotweb.com/2016/03/19/yet-another-way-you-can-be-fingerprinted-while-using-tor/">flaw in a 2016 article</a>:</p>
    <p>“The mouse wheel event in Tor Browser (and most browsers) leaks information of the underlying hardware used to scroll the web page. The event provides information about the delta scrolled, however, if you are using an ordinary computer mouse with a mouse wheel, the delta is always three, but if you are using a trackpad, the deltas are variable and related to your trackpad and your usage patterns.” (<a href="http://jcarlosnorte.com/security/2016/03/06/advanced-tor-browser-fingerprinting.html">jcarlosnorte.com</a>)</p>
    <p>Mozilla’s font whitelist patch, in the proposed version and theory, implements a list of OK fonts or technically “whitelist” fonts. A request for a machine’s font family would then, and again—in theory—prevent the website from identifying the operating system beyond a predefined level. While this patch originated from a similar one and current functionality in Tor, the implementation differs slightly. And possibly to a fault. <a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1121643">The end of the bug report that</a> ultimately initiated the development of a font whitelist ended with “The scope of this feature is very narrow. Is there a second bug that builds on this one? If not, should I make one […]?”</p>
    </div>
    <span style="display:none"><a href="https://www.deepdotweb.com/tag/52/" rel="tag">52</a> <a href="https://www.deepdotweb.com/tag/adds/" rel="tag">adds</a> <a href="https://www.deepdotweb.com/tag/fingerprinting/" rel="tag">fingerprinting</a> <a href="https://www.deepdotweb.com/tag/firefox/" rel="tag">firefox</a> <a href="https://www.deepdotweb.com/tag/font/" rel="tag">font</a> <a href="https://www.deepdotweb.com/tag/fonts/" rel="tag">fonts</a> <a href="https://www.deepdotweb.com/tag/os/" rel="tag">os</a> <a href="https://www.deepdotweb.com/tag/prevent/" rel="tag">prevent</a> <a href="https://www.deepdotweb.com/tag/torlike/" rel="tag">torlike</a> <a href="https://www.deepdotweb.com/tag/whitelist/" rel="tag">whitelist</a></span> <span style="display:none" class="updated">2017-01-13</span>
    <div style="display:none" class="vcard author" itemprop="author" itemscope itemtype="http://schema.org/Person"><strong class="fn" itemprop="name"><a href="https://www.deepdotweb.com/author/caliens/" title="Posts by C. Aliens" rel="author">C. Aliens</a></strong></div>
    </div>
</article>
