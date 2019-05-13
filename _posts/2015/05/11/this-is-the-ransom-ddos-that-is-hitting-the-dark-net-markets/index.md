---
TRD Admin On The Ransom DDoS That Is Hitting The Dark Net Markets
---
<article class="post-listing post-10252 post type-post status-publish format-standard has-post-thumbnail hentry category-deepdot-news category-news-updates tag-admin tag-dark tag-ddos tag-hitting tag-markets tag-net tag-ransom tag-trd">
    
    <div class="post-inner">
    
    
    <p class="post-meta">
    
    <span>Posted by: <a href="https://www.deepdotweb.com/author/admin/" title="">DeepDotWeb </a></span>
    
    
    <span>May 11, 2015</span>
    <span>in <a href="https://www.deepdotweb.com/category/deepdot-news/" rel="category tag">Featured</a>, <a href="https://www.deepdotweb.com/category/news-updates/" rel="category tag">News Updates</a></span>
    
    <span><a href="https://www.deepdotweb.com/2015/05/11/this-is-the-ransom-ddos-that-is-hitting-the-dark-net-markets/#comments">29 Comments</a></span>
    </p>
    <div class="clear"></div>
    
    <div class="entry">
    
    <p><span style="text-decoration: underline;">The admin of <a href="http://www.deepdotweb.com/2015/04/08/therealdeal-dark-net-market-for-code-0days-exploits/">Therealdeal market</a> (<strong>http://trdealmgn4uvm42g.onion/</strong>) provided us with some insights about the recent  DDo&#8217;s attacks that are hitting all the major DNM&#8217;s in the past week:</span></p>
    <p>In the past few days, it seems like almost every DN market is being hit by DDoS attacks. Our logs show huge amounts of basic http requests aiming for dynamic pages, probably in attempt to (ab)use as many resources as possible on the server side, for example by requesting for pages that execute many sql queries or generate captcha codes.</p>
    <p>As we are security oriented we manged to halt the attack on our servers the moment it showed up in the logs. Although this required fast thinking, due to the fact that dealing with this kind of attack over tor is not the same as dealing with such attack over clearnet. New addresses? Shifting Pages? Waiting? All these did not work for other markets&#8230;</p>
    <p>Here you can see the beginning and failure, as caught by <a href="https://dnstats.net/market/TheRealDeal">Dnstats</a>:<br />
    <a href="http://www.deepdotweb.com/wp-content/uploads/2015/05/failddos.png"><img class="aligncenter size-full wp-image-10253" src="https://www.deepdotweb.com/wp-content/uploads/2015/05/failddos.png" alt="failddos" width="585" height="324" srcset="https://www.deepdotweb.com/wp-content/uploads/2015/05/failddos.png 585w, https://www.deepdotweb.com/wp-content/uploads/2015/05/failddos-300x166.png 300w" sizes="(max-width: 585px) 100vw, 585px" /></a>As you can see, our market&#8217;s response time spiked to almost 70 seconds while our market&#8217;s usual response time is insanely fast, almost like most clearnet sites. But also, you can see that the response time was back to 2-3 seconds a little after. Here is an example of a darknet market that didn&#8217;t know how to combat this problem:<br />
    <a href="http://www.deepdotweb.com/wp-content/uploads/2015/05/gooddos.png"><img class="aligncenter size-full wp-image-10254" src="https://www.deepdotweb.com/wp-content/uploads/2015/05/gooddos.png" alt="gooddos" width="564" height="300" srcset="https://www.deepdotweb.com/wp-content/uploads/2015/05/gooddos.png 564w, https://www.deepdotweb.com/wp-content/uploads/2015/05/gooddos-300x160.png 300w" sizes="(max-width: 564px) 100vw, 564px" /></a><br />
    The flat line at 0 seconds meaning there was no response from the server.</p>
    <h3>The Problem</h3>
    <p>As opposed to cleanet attacks, where mitigation steps could be taken by simply blocking the offending IP addresses,when it comes to tor, the requests are coming from the localhost (127.0.0.1) IP address as everything is tunneled through tor.<br />
    <a href="http://www.deepdotweb.com/wp-content/uploads/2015/05/screenshot.png"><img class="aligncenter  wp-image-10255" src="https://www.deepdotweb.com/wp-content/uploads/2015/05/screenshot.png" alt="screenshot" width="1012" height="579" srcset="https://www.deepdotweb.com/wp-content/uploads/2015/05/screenshot.png 1301w, https://www.deepdotweb.com/wp-content/uploads/2015/05/screenshot-300x172.png 300w, https://www.deepdotweb.com/wp-content/uploads/2015/05/screenshot-1024x586.png 1024w" sizes="(max-width: 1012px) 100vw, 1012px" /></a></p>
    <p>Another problem is the fact that the attackers are using the same user-agent of tor browser &#8211; hence we cannot drop packets based on UA strings.</p>
    <p>The attackers are also aiming for critical pages of our site &#8211; for example the captcha generation page. Removing this page will not allow our users to login, or will open the site to bruteforce attempts. Renaming this page just made them aim for the new url (almost instantly, seems very much automated). One of the temporary solutions was to run a script that constantly renamed and re-wrote the login page after 1 successful request for a captcha&#8230; Attacks then turned into POST requests aiming for the login page.</p>
    <h3>Solutions</h3>
    <p>If you are a DNM owner or just the security admin, check your webserver logs. There is something unique in the HTTP requests, maybe a string asking you to pay to a specific address. (assuming these are the same offenders). Otherwise there might be something else &#8230; Hint: you might need to load tcpdump during an attack.</p>
    <p>Hopefully, you are not using some kind of VPS and have your own dedicated servers and proxy servers. Or if you are using some shit VPS, then hopefully you are using KVM or XEN. (first reason being the memory is leakable and accessible by any other user of the same service).</p>
    <p>The other reason is &#8211; control on the kernel level. You can drop packets containing specific strings by using iptables, or use regex too. This is <strong>one example</strong> of a commad that we executed (amongst others) to get rid of the offenders, we cannot specify all of them, so be creative! iptables -A INPUT -p tcp &#8211;dport 80 -m string &#8211;algo bm &#8211;string &#8220;(RANSOM_BITCOIN_ADDRESS)&#8221; -j DROP Where (RANSOM_BITCOIN_ADDRESS) is the unique part of the request&#8230;</p>
    <p><strong>To Other Market Admins:</strong></p>
    <p>There are additional things to be done, but if we expose them, this will only start a cat and mouse game with these attackers. If you are a DNM admin feel free to sign up as a buyer at TheRealDeal Market and send us a message (including your commonly used PGP), since at the end of the day even though you might see us a competitor in a way, there are some things (like people stuck without their pain medication from mexico) that are priceless&#8230;</p>
    <p><em>Thanks to <a href="http://www.deepdotweb.com/2015/04/08/therealdeal-dark-net-market-for-code-0days-exploits/">Therealdeal market</a> admin (<strong>http://trdealmgn4uvm42g.onion/</strong>) for providing us with this info!</em></p>
    
    
    </div><!-- .entry /-->
    <span style="display:none"><a href="https://www.deepdotweb.com/tag/admin/" rel="tag">admin</a> <a href="https://www.deepdotweb.com/tag/dark/" rel="tag">dark</a> <a href="https://www.deepdotweb.com/tag/ddos/" rel="tag">ddos</a> <a href="https://www.deepdotweb.com/tag/hitting/" rel="tag">hitting</a> <a href="https://www.deepdotweb.com/tag/markets/" rel="tag">markets</a> <a href="https://www.deepdotweb.com/tag/net/" rel="tag">net</a> <a href="https://www.deepdotweb.com/tag/ransom/" rel="tag">ransom</a> <a href="https://www.deepdotweb.com/tag/trd/" rel="tag">trd</a></span>				<span style="display:none" class="updated">2015-05-11</span>
    <div style="display:none" class="vcard author" itemprop="author" itemscope itemtype="http://schema.org/Person"><strong class="fn" itemprop="name"><a href="https://www.deepdotweb.com/author/admin/" title="Posts by DeepDotWeb" rel="author">DeepDotWeb</a></strong></div>
    
    
    </div><!-- .post-inner -->
</article><!-- .post-listing -->
