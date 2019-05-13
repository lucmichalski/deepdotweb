---
On Public and Private WiFi, VPNs, Tor, and Virtual Machines
---
<article class="post-listing post-14804 post type-post status-publish format-standard has-post-thumbnail hentry category-articles category-deepdot-news tag-machines tag-private tag-public tag-tor tag-virtual tag-vpns tag-wifi">
    <div class="post-inner">
    <p class="post-meta">
    <span>Posted by: <a href="https://www.deepdotweb.com/author/caliens/" title="">C. Aliens </a></span>
    <span>July 15, 2016</span>
    <span>in <a href="https://www.deepdotweb.com/category/articles/" rel="category tag">Articles</a>, <a href="https://www.deepdotweb.com/category/deepdot-news/" rel="category tag">Featured</a></span>
    <span><a href="https://www.deepdotweb.com/2016/07/15/on-public-and-private-wifi-vpns-tor-and-virtual-machines/#comments">12 Comments</a></span>
    </p>
    <div class="clear"></div>
    <div class="entry">
    <p>If you require privacy while connected to the internet – and I mean really require it – there is no reason to only make it part of the way to being safe. In the world we live in today, it&#8217;s foolish to ever assume you&#8217;re completely untraceable. The most we can accomplish is making it as difficult as possible for the tracing to happen. Nearly every tool we use for privacy has been compromised in some way or another; users are repetitively making careless mistakes and the government is successfully capitalizing on them. Nobody is secure.</p>
    <p>That being said, there are ways to make tracking you down so increasingly difficult that only the most well-funded and militantly dedicated entities will pursue you. One instance of this type of set-up, while not as complex as it could be, involves running Tor with multiple VPNs—inside virtual machines. It&#8217;s admittedly a major pain in the ass, but it&#8217;s one of  the most secure ways to access the internet. I&#8217;ll be covering the basics of running Tor within a VPN within a virtual machine.</p>
    <p><strong>VPNs</strong></p>
    <p>VPNs can be very secure – in fact, a good one could be potentially unbreakable. It&#8217;s important to make absolutely sure that the VPN you use is trustworthy. DDW has a great <a href="https://www.deepdotweb.com/vpn-comparison-chart/">comparison chart</a> of some of the top services on the market. I would also recommend <a href="https://www.reddit.com/r/vpn">r/VPN</a> and<a href="https://www.reddit.com/r/vpnreviews"> r/VPNReviews</a> as starting points. One of the biggest issues we see talked about in regard to VPNs is logging. Many services claim they don&#8217;t keep user logs, but are either intentionally misleading or painfully negligent. The comparison chart points out that you want a VPN that respects your privacy, uses encryption, supports OpenVPN, has a no logging policy and prioritizes Bitcoin as payment. This isn&#8217;t an article about picking VPNs so finding one that fits your needs and meets the criteria above is up to you.</p>
    <p>I&#8217;ll start with one of the most common ways to lose your anonymity, even when using an excellent VPN. DNS Leaking. Internet service providers assign DNS servers to clients on the network and are able to track whenever you send a request to the assigned server. However, when you use a VPN, any DNS requests are supposed to be sent to an anonymous server – through the VPN – preventing the ISP from tracking it. The leak can happen when your browser mistakenly forgets that you&#8217;re running a VPN and sends the request to default DNS servers, resulting in the same tracking you were trying to avoid. Leaks are a simple fix, but it&#8217;s easy to be unaware until it&#8217;s too late. The easiest way to check for leaks is to use <a href="http://www.dnsleaktest.com/">dnsleaktest.com</a> and run the standard test option. There will be a list of DNS servers. You want the location to be somewhere other than the country where you are actually located and you need to make sure name in the ISP column is not your actual ISP.</p>
    <p>If you are seeing your own location and DNS servers hosted by your ISP – you have a leak – but it&#8217;s not a hard problem to solve. By far, the easiest way to eliminate a DNS leak is by simply eliminating the ISP&#8217;s DNS server and replacing it with a 3<sup>rd</sup> party one. Some good examples of these are <a href="https://developers.google.com/speed/public-dns/">Google&#8217;s Public DNS server </a>@ 8.8.8.8 or the <a href="https://www.opendns.com/">OpenDNS server</a> @ 208.67.222.222. You can do your own review of alternate DNS servers, but those two are well-known and generally have several advantages over others.</p>
    <p>There&#8217;s also programs that can cause DNS leaks. There&#8217;s very few I am aware of but I believe the main culprit here would be <a href="https://en.wikipedia.org/wiki/Teredo_tunneling">Teredo clients</a>. To my knowledge, they aren&#8217;t default in any current operating systems, but XP, Vista, and potentially builds of Windows 7 had Teredo support and clients built in. Run Command Prompt as Administrator and enter the following without quotes: “netsh interface teredo set state disabled”. You may need to reboot. And for re-enabling: “netsh interface teredo set state type=default”.</p>
    <p>Back to the topic at hand. To benefit from the most possible safety a VPN can offer, you&#8217;re going to need to sign up using an anonymous I.P. address and a method of payment that can&#8217;t be traced back to you in any conceivable way. For those who don&#8217;t know, the majority of crypto-currency is good for this. Obviously Bitcoin is at the top of this list. Using a good <a href="https://en.wikipedia.org/wiki/Cryptocurrency_tumbler">tumbler</a> is generally a recommend step to obfuscating bitcoin transactions, destinations, and starting points. Otherwise, they are <a href="https://news.bitcoin.com/law-enforcement-continues-invest-bitcoin-tracking-services/">traceable</a> to some degree. The nature of the blockchain allows transactions to be traced and once your wallet address is known, it&#8217;s only a matter of time before all incoming and outgoing bitcoin movements can be trackable. Again,<em> to a degree</em>. Here&#8217;s a site that lets you do exactly that. <a href="http://walletexplorer.com/">WalletExplorer.com</a>. A good example of coins being traced would be when people buy Bitcoins with a service like Coinbase and send the coins directly to their darknet market wallet, and then have Coinbase close the account for illegal activity.</p>
    <p>There&#8217;s a major downside to using tumblers – losing your money – either accidentally or using a link to a scam tumbler that&#8217;s set up like a real one. There is only one bitcoin cleaner I will recommend and that&#8217;s <a href="https://www.deepdotweb.com/2014/06/22/introducing-grams-helix-bitcoins-cleaner/">Grams&#8217;s Helix</a>. I don&#8217;t think there has been a single report of missing coins and Grams has repeatedly proven themselves to be trustworthy. There&#8217;s always arguments for both sides of the fence on bitcoin tumbling, but like I read on Reddit at some point: everyone using the deepweb recommends turning off Javascript. It&#8217;s not always essential to being safe, but it&#8217;s much safer to have it off than on.</p>
    <p><strong>Tor</strong></p>
    <p>We&#8217;ve learned that blindly running Tor alone isn&#8217;t safe either: researchers just found more than <a href="https://www.deepdotweb.com/2016/07/07/researchers-found-over-100-snooping-tor-hsdir-relays/">100 snooping Tor relays</a> and the web is well aware of the<a href="https://www.deepdotweb.com/2016/06/28/fbi-is-trying-to-hide-their-tor-exploit-for-good/"> FBI&#8217;s Tor exploit</a> that they refuse to release.  Beyond that, Tor is just like any other program; it has bugs, some of which are major security threat, and it&#8217;s possible they won&#8217;t be discovered until someone takes advantage of them. Even if they aren&#8217;t compromised by the NSA or FBI, having your Tor traffic de-anonymized by a 3<sup>rd</sup> party could be far worse than having clearnet traffic intercepted.</p>
    <p>Just to go into brief detail regarding potential threats on Tor, we&#8217;ll take a look at traffic confirmation hacks. The Onion Project, on their blog, has an article about how “<a href="https://blog.torproject.org/blog/one-cell-enough">One cell is enough to break Tor&#8217;s anonymity</a>&#8221; and it gives a pretty good explanation of how it works. Traffic confirmation hacks are not extremely complicated and Tor is not meant to stop these hacks from happening as it would take more resources than they can afford to use. This kind of hack occurs when an attacker is able to observe relays on both ends of a Tor circuit. If the first relay is an entry guard and the last relay knows the destination, this information can absolutely be used to deanonymize the user.</p>
    <p>That being said, for what Tor advertises to do, it does very well. The issues referred to here aren&#8217;t an unknown conspiracy theory; The Onion Project talks about them on their own blog and it goes right along with the concept of this article: making it increasingly difficult to be compromised, not impossible.</p>
    <blockquote><p>Because we aim to let people browse the web, we can&#8217;t afford the extra overhead and hours of additional delay that are used in high-latency mix networks like <a href="http://freehaven.net/anonbib/#mixmaster-spec">Mixmaster</a> or <a href="http://freehaven.net/anonbib/#minion-design">Mixminion</a> to slow this attack. That&#8217;s why Tor&#8217;s security is all about trying to decrease the chances that an adversary will end up in the right positions to see the traffic flows.</p>
    <p>The way we generally explain it is that Tor tries to protect against traffic analysis, where an attacker tries to learn whom to investigate, but Tor can&#8217;t protect against traffic confirmation (also known as end-to-end correlation), where an attacker tries to confirm a hypothesis by monitoring the right locations in the network and then doing the math. And the math is really effective. There are simple packet counting attacks (<a href="http://freehaven.net/anonbib/#SS03">Passive Attack Analysis for Connection-Based Anonymity Systems</a>) and moving window averages (<a href="http://freehaven.net/anonbib/#timing-fc2004">Timing Attacks in Low-Latency Mix-Based Systems</a>), but the more recent stuff is <a href="http://www.lightbluetouchpaper.org/2007/05/28/sampled-traffic-analysis-by-internet-exchange-level-adversaries/">downright scary</a>, like Steven Murdoch&#8217;s PET 2007 paper about achieving high confidence in a correlation attack despite seeing only 1 in 2000 packets on each side (<a href="http://freehaven.net/anonbib/#murdoch-pet2007">Sampled Traffic Analysis by Internet-Exchange-Level Adversaries</a>).</p></blockquote>
    <p>And one of the last points worth making about Tor alone is that your ISP would know you&#8217;re using Tor unless bridges are used. Therefore the chance that you would lose plausible deniability – in the most extreme cases – is always there. The likelihood of a problem similar to this ever arising is pretty slim, but it&#8217;s worth noting. This <a href="http://www.businessinsider.com/harvard-student-used-tor-for-bomb-threat-2013-12">Harvard student</a>, in 2013, displays a great example of how the FBI were able to determine that he had called in the bomb threat. He was simply selected as a suspect by being one of a few people who used Tor that morning and, of course, confessed when confronted by agents.</p>
    <p>It&#8217;s really no surprise that the majority of issues that occur when using Tor seem to be caused by user error and human stupidity, but there are several small issues that, especially when they stack, can render your security useless. This is why I recommend running both a VPN and Tor at the same time. Some will argue that it&#8217;s a pointless measure or that it&#8217;s more work than it&#8217;s worth, but given some of the issues pointed out above, I disagree.</p>
    <p>Here&#8217;s an infographic /u/SecureThoughts <a href="https://www.reddit.com/r/TOR/comments/2r2xac/for_those_of_us_who_use_a_vpn_tor_together_i_made/">posted on Reddit</a> some time back that demonstrates what running both would look like:</p>
    <p><a href="https://www.deepdotweb.com/wp-content/uploads/2016/07/vpnstor1.png"><img class="aligncenter size-full wp-image-14805" src="https://www.deepdotweb.com/wp-content/uploads/2016/07/vpnstor1.png" alt="vpnstor1" width="1000" height="600" srcset="https://www.deepdotweb.com/wp-content/uploads/2016/07/vpnstor1.png 1000w, https://www.deepdotweb.com/wp-content/uploads/2016/07/vpnstor1-300x180.png 300w" sizes="(max-width: 1000px) 100vw, 1000px" /></a></p>
    <p>There&#8217;s an overwhelming amount of “double encryption” in the picture, and for my needs, that&#8217;s perfect. Breaking that would require a significant amount of resources and it would certainly discourage people from attempting the task.</p>
    <p><strong>VMs</strong></p>
    <p>Taking this one step further is terrifyingly complex and is only recommended for those who are absolutely terrified of being spied on or simply enjoy <em>feeling</em> impenetrable. The extra step I am referring to is adding in Virtual Machines.  More complexity can be achieved using a chain of VMs with Whonix, but it&#8217;s too complex to get into here. The basic concept is that even if someone gets through your VPN and Tor, they won&#8217;t know anything about your actual machine. And, although unlikely, if ransomware were ever to make it&#8217;s way down Tor nodes, if your machine got infected, you could just purge the VM and be done with it.</p>
    <p>If you&#8217;re interested in taking the plunge, good VM software will be needed. The market standard is currently <a href="https://www.virtualbox.org/wiki/Downloads">VirtualBox</a>. It&#8217;s great software and is open source. Free, too. Running a Linux distro is the best option for a whole array of reasons. Arguably, you&#8217;d want to run different operating systems on virtual machines. Different from both each other and host machines. There&#8217;s a bunch of potential Linux distributions out there, but, for the sake of being brief, I&#8217;ll suggest Ubuntu for the user friendly experience and Arch for the customization and control.</p>
    <p>Once you&#8217;ve installed VirtualBox and downloaded your Linux distribution’s .iso, (<a href="http://www.ubuntu.com/desktop">here&#8217;s Ubuntu&#8217;s</a>) you&#8217;re going to want to set it up in a way that will best work for you. I&#8217;ll run through what I recommend for first time users. Inside VirtualBox, select &#8216;New&#8217; and choose your OS. In this case Ubuntu. You won&#8217;t need much RAM for a single VM instance, so 1GB will likely do. You can change this in the future. Use defaults for storage; it&#8217;s dynamic so space can grow if you end up using more than planned. Then hit &#8216;Create.&#8217;</p>
    <p>There&#8217;s some extra tweaking that I would recommend doing in both the General/Advanced tab and USB tab: disable &#8216;Shared Clipboard/Drag&#8217; and Drop and &#8216;Enable USB Controller.&#8217; Under Storage and CD select &#8216;Choose a virtual CD/DVD disk file&#8217; and find your .iso image you downloaded from before. You can now run the VM and go through the OS install. It&#8217;s up to you whether or not you want to use encrypted LVM in disc partitioning; I can&#8217;t really comment either way.</p>
    <p>When you have your system installed, I would immediately turn off networking and then disable WebGL. In Firefox type “about:config” in the URL bar and set “webgl.disabled” to true. You can turn networking back on at this point. Now you&#8217;re going to need to set up the system for running a VPN. Since the instructions for other types of VPNs may vary depending on the service, I&#8217;ll explain the process for Open-VPN services.</p>
    <p>Open Terminal and then type:</p>
    <ol>
    <li>sudo apt-get install network-manager-openvpn</li>
    <li>sudo restart network-manager</li>
    </ol>
    <p>Review the .crt and .key files your VPN gave you and find the VPN server you want to be connecting to. You will need to use the IP address instead of the hostname. You’ll also need to know the server port number and connection type which will be either UDP or TCP. If you&#8217;re routing via Tor, use TCP. Otherwise UDP. Check the cipher type and if none, use Network Manager as default. If your VPN provides a ta.key, you’ll need to know the number at the end of the tls-auth line for the key direction.</p>
    <p>You&#8217;re going to need to copy all your VPN certificates and key files to the OpenVPN directory. Open Terminal again.</p>
    <ol>
    <li>cd /home/user/path-to-the-files</li>
    <li>sudo cp ca.crt client.crt client.key ta.key /etc/openvpn/</li>
    </ol>
    <p>And then you&#8217;re going to need to set up the VPN from within Network Manager.</p>
    <ol>
    <li><strong>VPN → Add → Create. Enter the IP of your server.</strong></li>
    <li>If your VPN provides only a ca.key;
    <ol>
    <li>Password → Enter username and password.</li>
    <li>CA Certificate → Places → File System → etc → find your ca.crt.</li>
    <li>Then Advanced → General → “Use Custom Gateway Port” and enter the port number.</li>
    </ol>
    </li>
    <li><strong>If your VP provides ca.key, client.crt and client.key, but not ta.key;</strong>
    <ol>
    <li>Select Certificates(TLS)</li>
    <li>Replicate the steps above for uploading the ca.crt key, but also for client.crt and client.key.</li>
    <li>Then Advanced → General → “Use Custom Gateway Port” and enter the port number.</li>
    </ol>
    </li>
    <li><strong>If your VPN provides ca.key, client.crt, client.key and ta.key, and requires a password for connection;</strong>
    <ol>
    <li>Password with Certificates (TLS) → Enter username and password.</li>
    <li>Add the ca.crt and client.crt as described above.</li>
    <li>Then Advanced → General → “Use Custom Gateway Port” and enter the port number.</li>
    <li>TLS Authentication → Use additional TLS authentication → Key File and upload your ta.key.</li>
    </ol>
    </li>
    </ol>
    <p>Check <a href="http://whatismyipaddress.com/">Whatismyipaddress</a> to see if the VPN is connecting successfully. If it doesn&#8217;t connect, use Google. That&#8217;s about all I can cover here without rambling on any more than I already have. I&#8217;d recommend using <a href="https://github.com/adrelanos/VPN-Firewall">VPN-Firewall</a> to check for VPN leaks. It&#8217;s a pretty easy setup. <a href="https://www.whonix.org/wiki/Main_Page">Whonix</a> has some great information on chaining multiple virtual machines as well as documentation about most of this stuff. I&#8217;d recommend checking it out.</p>
    <p>That&#8217;s it for now. Good luck.</p>
    </div>
    <span style="display:none"><a href="https://www.deepdotweb.com/tag/machines/" rel="tag">machines</a> <a href="https://www.deepdotweb.com/tag/private/" rel="tag">private</a> <a href="https://www.deepdotweb.com/tag/public/" rel="tag">public</a> <a href="https://www.deepdotweb.com/tag/tor/" rel="tag">tor</a> <a href="https://www.deepdotweb.com/tag/virtual/" rel="tag">virtual</a> <a href="https://www.deepdotweb.com/tag/vpns/" rel="tag">vpns</a> <a href="https://www.deepdotweb.com/tag/wifi/" rel="tag">wifi</a></span> <span style="display:none" class="updated">2016-07-15</span>
    <div style="display:none" class="vcard author" itemprop="author" itemscope itemtype="http://schema.org/Person"><strong class="fn" itemprop="name"><a href="https://www.deepdotweb.com/author/caliens/" title="Posts by C. Aliens" rel="author">C. Aliens</a></strong></div>
    </div>
</article>
