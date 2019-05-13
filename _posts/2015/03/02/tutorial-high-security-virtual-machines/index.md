---
Tutorial: High Security Virtual Machines
---
<article class="post-listing post-8547 post type-post status-publish format-standard has-post-thumbnail hentry category-articles category-deepdot-news tag-high tag-machines tag-security tag-virtual">
<div class="post-inner">
<p class="post-meta">
<span>Posted by: <a href="https://www.deepdotweb.com/author/tr3x0r/" title="">TR3X0R </a></span>
<span>March 2, 2015</span>
<span>in <a href="https://www.deepdotweb.com/category/articles/" rel="category tag">Articles</a>, <a href="https://www.deepdotweb.com/category/deepdot-news/" rel="category tag">Featured</a></span>
<span><a href="https://www.deepdotweb.com/2015/03/02/tutorial-high-security-virtual-machines/#comments">27 Comments</a></span>
</p>
<div class="clear"></div>
<div class="entry">
<p><strong>Utilizing Virtualization to Increase Information Security</strong></p>
<p>Anonymity, privacy and information security are issues that affect all people in today’s digital age, not just cyber-criminals and drug dealers. You might handle company secrets that competitors or hackers could use to wreak havoc upon your company and steal from your customers. You might work in a conservative setting in which your sexual orientation or political views would subject you to negative stereotyping. Perhaps you’re a medicinal cannabis user in a state with hostile laws surrounding the issue. Attorneys, doctors and accountants constantly face frivolous lawsuits that could destroy their careers, while journalists documenting governmental abuses could find themselves in all sorts of trouble before they know it. Maybe you simply value discretion in your personal relationships and communications, and expect a reasonable amount of privacy in your daily life.</p>
<p>The bad news is that obtaining such a measure of privacy is increasingly difficult, and <em>uncommon</em>, in today’s technological landscape, and I have no turn-key solution for this problem. The good news is that I can provide several simple security measures that are easy to implement and go a very long way in defeating all but the most sophisticated intrusion attempts.</p>
<p><strong>Rule Number One: Don’t Have an Identity-Crisis</strong></p>
<p>Failing to separate your “public” digital life (primarily your social media and <em>non</em>-sensitive interpersonal communications) with your <em>expectedly private </em>life is the number one mistake people make when attempting to establish information security or anonymity. This most basic of principals seems inmate to hackers but the majority of people don’t understand why the “private” Facebook conversation they had with their lover or the phone call out of ear-shot from third parties are <em>sitting ducks</em> for hackers or government spies (in these two scenarios, the attack surface consists primarily of phishing and MITM vectors for the former and baseband exploitation and/or malicious iOS/Android apps for the later, all are quite easily accomplished).</p>
<p>It’s an uphill battle to make your Windows 8.X install secure (if that’s your goal, say hello to Windows Server 2012, in <em>core-mode</em>, and bye to your GUI’s). Sadly, OS X, Android, and iOS are also compromised, as are your ISP and cellular services. When it comes to high-security computing environments, unless you’re using a *nix-based OS specifically designed with security in mind (Subraph Linux, a Whonix setup, Tails OS, etc. ) you can count your daily OS out of the picture. Fortunately, using some basic principles, we can establish a relatively secure environment <em>within </em>our vulnerability-ridden daily workstations quickly and easily.</p>
<p>Many people are not ready to take the leap to convert their primary machine to, for example, a bare-bones Linux install, and give up all of their fun, privacy-invading/vulnerable Apps/Plugins/Widgets, and the method described in this article provides a healthy medium. If you’ve never used VirtualBox or VMware now is a good time to start. Beyond providing a platform to establish a more secure computing environment, virtualizing OS’s and servers can open many possibilities for technology professionals. Virtualization technology itself is mature and enterprise-quality. It provides for the standardization of development (and run-time) environments across diverse host types; many of your favorite cloud-based apps and websites run on virtualized servers. Virtualization also allows ordinary users an easy way of trying out new operating systems without committing a physical system to the project.</p>
<p>For this guide, we will use Oracle’s VirtualBox. Both VMware and VirtualBox offer free virtualization solutions as well as more robust “workstation” packages for commercial use, all of excellent quality. Virtualbox, however, has an <em>open-source </em>version that we will use as it provides some additional measure of security in knowing the codebase is community-reviewed. It should, however, be noted that exploits targeted at both of these softwares do exist. Merely virtualizing a secure OS by a non-secure OS is not DEFCON-1 level security, but it’s an excellent counter-measure to common exploits that average users can implement freely and easily.</p>
<p>I must also point out this rule goes two ways; when you are happily surfing the deep web from your high-security virtual machine, please, people, don’t hop over to your Facebook page or check your Gmail within your high-security environment. The reasons for this are numerous and hopefully obvious. In this context, having an identity crisis refers to mixing your private and non-private identities in any way.</p>
<p><strong>Rule Number Two: Don’t Be So Non-Volatile</strong></p>
<p>One of the easiest ways to lock-down your high-security environment is to simply use read-only (as ISO’s are by default) disk images as your guest. Most distributions of Linux have “Live-Install” iso images that can be downloaded and virtualized in minutes. No installation is required, no virtual drives need be created, and, more importantly, the guest OS writes nothing to the hard disk of the host. The filesystem of the guests resides entirely within the ISO, which is of locked size and content (attempting to write to an iso image will yield an I/O error). It’s <em>static, </em>and it contains everything our guest OS needs to function; web browsers, email clients and messaging clients are all included. That ISO of a new Linux spin you just downloaded isn’t changing, in size <em>or</em> content, whether we like it or not, and in this case we like that. It means everything the guest OS does resides only within our machine’s RAM. RAM is <em>volatile</em>; as soon it loses power (any time your machine is power-cycled, for example) all of its contents are erased, and in general its contents are erased and overwritten thousands of times per second. Effectively, what this means is as soon as you close your virtualization software and turn off your machine, all traces of the guest OS are eliminated from memory, and nothing is ever written to your host’s disk drive. We also have the added benefit of snappiness in our guest OS; RAM is much faster than hard disks, even solid state drives.</p>
<p>The only exceptions to this are when we tell the virtualization software to save the state of our machine to disk (ie “pausing” or “suspending” the state of the guest OS) or when the host OS commits the RAM the virtualization software is using to a swap file (or “paging” file, a portion of your disk drive used to emulate RAM). The first exception can easily be avoided: don’t save the state of your virtual machine when you’re done using it. Power it off. The second issue only occurs if your machine is starved for RAM and even then is only of concern for the usually very brief period of time in which the RAM is virtualized on disk. If you need to make sure your guest OS doesn’t touch swap memory on your device, you can use the linux command mlock(2) or adjust the “swappiness” of the guest linux OS. At any rate, your swap memory is normally purged upon closing of VirtualBox/VMware and most always purged (again) upon shutdown of the host OS.</p>
<p>This is a convenient way to ensure that our high-security virtual machine does not leave traces on our hard disk that could later be analyzed. In other words, the non-volatile memory of the host OS is never touched by the guest OS.</p>
<p><strong>Rule Number Three: NIC Your Problem in the Bud</strong></p>
<p>After choosing a security-oriented ISO image and creating our Virtual Machine (instructions below), we still must consider how the guest OS uses our host’s networking resources: our wifi and ethernet cards. By default, network address translation (NAT) is configured by the virtualization software such that the guest OS shares an IP address with the host. Effectively, this means the two share an internet connection and packets could be intercepted, in both directions on both machines. Furthermore, with this default configuration, malware compromising the virtualization software’s drivers (to translate your, for example, OS X host’s connection into the Linux guest’s world) increase the attack surface as well. The best and sure-fire way to prevent this is to nic (sic) the problem in the bud and use a <em>dedicated </em>network interface card on your guest OS. In layman’s terms: Go buy a $10-$20 wifi adapter and tell VirtualBox to connect it to your high-security Virtual Machine. For additional security, change the MAC address of your dedicated NIC (now controlled by the guest VM). These measures will ensure that the traffic between the host OS and the guest OS never mix.</p>
<p>It must be noted that any time you are virtualizing an OS, the <em>host </em>(the OS upon which your virtualization software such as VirtualBox or VMware is running) as well as any <em>network </em>(which the virtualized OS, the <em>guest</em>, connects to) might still be at-risk, so if you believe these things are already compromised or that you might be the target of an advanced persistent threat, you should operate with a <em>native </em>install of a high-security OS and only send packets over an iron-clad VPN or SOCKS5 proxy (for the moment even Tor can not provide absolute security, unfortunately).</p>
<p><strong>Instructions:</strong></p>
<ol>
<li>Download VirtualBox <a href="https://www.virtualbox.org/">here</a></li>
<li>Choose and download an appropriate Linux Live-Install ISO (we recommend Tails OS, which can be downloaded for free <a href="https://tails.boum.org/">here</a> )</li>
<li>Within VirtualBox, create a New Virtual Machine and choose Linux as the OS; selecting a Debian/Ubuntu 64-Bit architecture works fine for most distros.</li>
<li>Select Skip when asked to configure a virtual hard disk (we will be using only the ISO image to avoid making changes to our host’s disk drive)</li>
<li>Under the System Settings of your VM, adjust the RAM to at least 1024 and preferably 2048 MB (1-2 GB); most modern Linux machines require at least this much to function smoothly. Under the System-&gt;Processor preference pane, adjusting the number of processors of your VM to 2 will improve responsiveness by allowing for basic multithreading within the guest OS.</li>
<li>Under the Network settings of your VM, DISABLE all network adapters.</li>
<li>Start your VM, Select ISO, click the USB-Devices icon and switch over your external WiFi adapter.</li>
</ol>
<p>Be sure to get the latest versions of VirtualBox and Linux ISO, in this case <strong>TailsOS Version.</strong></p>
<p>For advanced users, <a href="https://www.whonix.org/"><strong>Whonix</strong> </a>is especially well-suited for virtualized high-security Tor portals and provides a convenient way to “torify” your primary OS’s traffic; the Whonix Gateway serves as the torifying layer, and the Whonix Workstation (an independent VM) can be used, or you can configure your primary OS to use the Whonix VM as a proxy. More on this topic in upcoming guides.</p>
<p><strong>Screenshots for Instructions</strong></p>
<p><span style="text-decoration: underline;">Step 1</span>: Download and install VirtualBox:</p>
<p><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/virtuabox.png"><img class="aligncenter  wp-image-8560" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/virtuabox.png" alt="virtuabox" width="696" height="369" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/virtuabox.png 1880w, https://www.deepdotweb.com/wp-content/uploads/2014/12/virtuabox-300x159.png 300w, https://www.deepdotweb.com/wp-content/uploads/2014/12/virtuabox-1024x543.png 1024w" sizes="(max-width: 696px) 100vw, 696px" /></a></p>
<p><span style="text-decoration: underline;">Step 2</span>: Download Tails OS. Advanced users might consider Whonix:</p>
<p><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/Tailsdown.png"><img class="aligncenter size-full wp-image-8562" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/Tailsdown.png" alt="Tailsdown" width="792" height="994" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/Tailsdown.png 792w, https://www.deepdotweb.com/wp-content/uploads/2014/12/Tailsdown-239x300.png 239w" sizes="(max-width: 792px) 100vw, 792px" /></a></p>
<p><span style="text-decoration: underline;">Step 3</span>: Create your VM. For smooth operation, one GB of RAM, and preferably two, is required. To further increase responsively add a second processor core.</p>
<p><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/createvm.png"><img class="aligncenter size-full wp-image-8548" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/createvm.png" alt="createvm" width="773" height="641" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/createvm.png 773w, https://www.deepdotweb.com/wp-content/uploads/2014/12/createvm-300x249.png 300w" sizes="(max-width: 773px) 100vw, 773px" /></a></p>
<p><span style="text-decoration: underline;">Step 4: </span>Select do not add a virtual hard drive:<span style="text-decoration: underline;"><br />
</span></p>
<p><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/harddrive.png"><img class="aligncenter size-full wp-image-8549" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/harddrive.png" alt="harddrive" width="772" height="643" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/harddrive.png 772w, https://www.deepdotweb.com/wp-content/uploads/2014/12/harddrive-300x250.png 300w" sizes="(max-width: 772px) 100vw, 772px" /></a></p>
<p>Ignore VirtualBox advising you your VM has no virtual disk; that’s exactly what we want in this case:</p>
<p><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/ignore.png"><img class="aligncenter size-full wp-image-8550" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/ignore.png" alt="ignore" width="775" height="643" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/ignore.png 775w, https://www.deepdotweb.com/wp-content/uploads/2014/12/ignore-300x249.png 300w" sizes="(max-width: 775px) 100vw, 775px" /></a> Add 2nd core:</p>
<p><img class="aligncenter size-full wp-image-8551" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/secondcore.png" alt="secondcore" width="774" height="643" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/secondcore.png 774w, https://www.deepdotweb.com/wp-content/uploads/2014/12/secondcore-300x249.png 300w" sizes="(max-width: 774px) 100vw, 774px" /></p>
<p><span style="text-decoration: underline;">Step 6</span></p>
<p>Again, unless you know exactly what you’re doing, it is best NOT to share network adapters between your VM and your regular desktop environment:</p>
<p><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/adapters.png"><img class="aligncenter size-full wp-image-8552" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/adapters.png" alt="adapters" width="772" height="639" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/adapters.png 772w, https://www.deepdotweb.com/wp-content/uploads/2014/12/adapters-300x248.png 300w" sizes="(max-width: 772px) 100vw, 772px" /></a></p>
<p><span style="text-decoration: underline;">Step 7</span></p>
<p>Fire up your secure VM. Upon the first startup, you will be prompted to choose an ISO for your startup disk:</p>
<p><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/fireupvm.png"><img class="aligncenter size-full wp-image-8553" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/fireupvm.png" alt="fireupvm" width="773" height="644" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/fireupvm.png 773w, https://www.deepdotweb.com/wp-content/uploads/2014/12/fireupvm-300x250.png 300w" sizes="(max-width: 773px) 100vw, 773px" /></a></p>
<p><strong>If your VM ever complains it doesn</strong><strong>’</strong><strong>t have a bootable drive, simply configure the setting in the </strong><strong>“</strong><strong>Storage</strong><strong>”</strong> <strong>preferences:</strong></p>
<p><strong><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/storage.png"><img class="aligncenter size-full wp-image-8554" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/storage.png" alt="storage" width="773" height="640" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/storage.png 773w, https://www.deepdotweb.com/wp-content/uploads/2014/12/storage-300x248.png 300w" sizes="(max-width: 773px) 100vw, 773px" /></a><br />
</strong></p>
<p><span style="text-decoration: underline;">Step 8</span></p>
<p>Once you’ve got your VM fired up, click the USB icon in the lower right of the VirtualBox windowed display and connect your independent network adapter. Tails will automatically randomize the MAC address; if you’re on a different Linux, issuing a command such as</p>
<p>#ifconfig wlan0 ether XX:XX:XX:XX:XX</p>
<p>Will add an additional measure of security in that your NIC does not use a vendor-specific MAC address (ie your Ralink wifi adapter won’t announce itself as “Ralink”)</p>
<p><a href="http://www.deepdotweb.com/wp-content/uploads/2014/12/tails.png"><img class="aligncenter  wp-image-8555" src="https://www.deepdotweb.com/wp-content/uploads/2014/12/tails.png" alt="tails" width="1132" height="637" srcset="https://www.deepdotweb.com/wp-content/uploads/2014/12/tails.png 1920w, https://www.deepdotweb.com/wp-content/uploads/2014/12/tails-300x169.png 300w, https://www.deepdotweb.com/wp-content/uploads/2014/12/tails-1024x576.png 1024w" sizes="(max-width: 1132px) 100vw, 1132px" /></a></p>
<p>Stay tuned on how to configure higher security configurations, implement roving MAC addresses, etc.</p>
</div>
<span style="display:none"><a href="https://www.deepdotweb.com/tag/high/" rel="tag">high</a> <a href="https://www.deepdotweb.com/tag/machines/" rel="tag">machines</a> <a href="https://www.deepdotweb.com/tag/security/" rel="tag">security</a> <a href="https://www.deepdotweb.com/tag/virtual/" rel="tag">virtual</a></span> <span style="display:none" class="updated">2015-03-02</span>
<div style="display:none" class="vcard author" itemprop="author" itemscope itemtype="http://schema.org/Person"><strong class="fn" itemprop="name"><a href="https://www.deepdotweb.com/author/tr3x0r/" title="Posts by TR3X0R" rel="author">TR3X0R</a></strong></div>
</div>
</article>
