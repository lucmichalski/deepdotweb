---
Interview: Monero&#8217;s fluffypony talks about current developments and the future of cryptocurrency
---
<article class="post-listing post-16636 post type-post status-publish format-standard has-post-thumbnail hentry category-articles category-deepdot-news tag-cryptocurrency tag-current tag-developments tag-fluffypony tag-future tag-interview tag-moneros tag-talks">
    
    <div class="post-inner">
    
    
    <p class="post-meta">
    
    <span>Posted by: <a href="https://www.deepdotweb.com/author/babysnoop/" title="">babysnoop </a></span>
    
    
    <span>November 29, 2016</span>
    <span>in <a href="https://www.deepdotweb.com/category/articles/" rel="category tag">Articles</a>, <a href="https://www.deepdotweb.com/category/deepdot-news/" rel="category tag">Featured</a></span>
    
    <span><a href="https://www.deepdotweb.com/2016/11/29/interview-moneros-fluffypony-talks-current-developments-future-cryptocurrency/#respond">Leave a comment</a></span>
    </p>
    <div class="clear"></div>
    
    <div class="entry">
    
    <p>Anyone currently having a closer look into the world of cryptocurrencies, would have likely stumbled across <a href="https://getmonero.org/home">Monero</a>, a privacy focused cryptocoin that is gaining a lot of traction right now. We travel to Plettenberg Bay, South Africa to have lunch (and of course beer) with <a href="https://twitter.com/fluffyponyza">fluffypony</a>, one of Monero&#8217;s core team members. The topic of our discussion was Monero&#8217;s current developments and the future of cryptocurrency. For a better overview the interview is split into the following seven sections.</p>
    <ul>
    <li>The community</li>
    <li>Instant transactions &amp; Double Spends</li>
    <li>Dark Net Markets</li>
    <li>Privacy</li>
    <li>Third party wallets</li>
    <li>New GUI</li>
    <li>The Future of Cryptocurrency</li>
    </ul>
    <p><span style="text-decoration: underline;">The community</span></p>
    <p><strong>Around </strong><a href="https://github.com/fluffypony/monero/graphs/contributors"><strong>70</strong></a><a href="https://github.com/fluffypony/monero/graphs/contributors"><strong> developers on Github have contributed to the project</strong></a><strong> but your core team of seven is seemingly small for a crypto currency that&#8217;s currently </strong><a href="http://coinmarketcap.com/currencies/views/all/"><strong>ranked number five in terms of </strong></a><a href="http://coinmarketcap.com/currencies/views/all/"><strong>market cap</strong></a><strong>. Do you feel like there is currently enough community support and are you happy with the size and level of involvement of the core team?</strong></p>
    <p>We are happy with the level of involvement and the direction that the project is going. That being said, we of course are constantly looking for new people to come in and contribute. In terms of the core team, people do come and go, but I think it&#8217;s size should stay the same as it&#8217;s focus is more towards stewardship as opposed to development.</p>
    <p><span style="text-decoration: underline;">Instant transactions &amp; Double Spend</span></p>
    <p><strong>Bitcoin is vulnerable to </strong><a href="https://en.bitcoin.it/wiki/Double-spending"><strong>double spends</strong></a><strong> (an exploit which reverses a transaction) which is an issue for &#8216;time critical&#8217; transactions like paying for a beer at a pub. Is Monero equally vulnerable to double spends right now? If yes, are there currently any plans to make Monero more resistant?</strong></p>
    <p>Like with Bitcoin, if you control 50% of the mining network, you could basically do whatever you want, including double spends – a very real vulnerably. If you want to double spend but don&#8217;t have 50% of the network, you can engage in a <a href="http://www.coindesk.com/bitcoin-bug-guide-transaction-malleability/">transaction malleability attack</a>, which is achieved by modifying the signature of a transaction so that it is still valid and rebroadcast it. Monero has a different malleability attack surface compared to Bitcoin, but that is not to say that we don’t suffer from malleability attacks. To make Monero more resistant to these sort of attacks we are looking to add a layer on top of the existing architecture such a <a href="https://github.com/BUSEC/TumbleBit">TumbleBit</a> or <a href="https://lightning.network/">Lightning Network</a> which are off-blockchain technologies that reduce transaction times.</p>
    <p><strong>Do you think a single cryptocurrency could be fungible (untraceable) and instant at the same time the same way physical cash is?</strong></p>
    <p>Absolutely. A lot of work will have to be done, but it&#8217;s coming. New projects such as TumbleBit could be the key. TumbleBit is a layer two system that is capable of making instant payments without being too much of a privacy sacrifice as it mixed transactions in a decentralized way.</p>
    <p><span style="text-decoration: underline;">Dark Net Markets</span></p>
    <p><strong>The price of Monero has been very volatile in the past few months, arguably due to the </strong><a href="https://www.deepdotweb.com/2016/08/23/alphabay-oasis-markets-begin-accepting-monero-payments/"><strong>adoption by Dark Net markets such as Oasis (now offline) and Alpha Bay</strong></a><strong>. Some people were betting on the possibility that Monero will replace Bitcoin in world of Dark Net Markets. Do you believe this is likely to happen? why or why not?</strong></p>
    <p>My gut feeling is no, because for the most part, Bitcoin is enough and its silly to believe that something else can come along and take the throne away from Bitcoin for no reason. No technology can claim dominance to the point where it can&#8217;t be replaced, but Bitcoin has so many people behind it and money invested, not to mention the amount of time that it has been tested. However I do believe that Monero will continue to exist as a hedge against Bitcoin. It could be that in future Bitcoin will be outlawed because it is traceable. A crypto exchange might lock you out of your funds because your coins were once used for something nefarious. In such case Monero could bemore appealing to a larger group of people.</p>
    <p><span style="text-decoration: underline;">Privacy</span></p>
    <p><strong>According to </strong><a href="https://getmonero.org/knowledge-base/about"><strong>Monero&#8217;s official web site, outsiders have no means of uncover the origin, </strong></a><a href="https://getmonero.org/knowledge-base/about"><strong>destination, or amount transacted with Monero</strong></a><strong>. You and your team are currently working on improving the way Monero hides transaction amounts using a process called </strong><a href="https://eprint.iacr.org/2015/1098.pdf"><strong>ring confidential  </strong></a><a href="https://lab.getmonero.org/pubs/MRL-0005.pdf"><strong>transactions or RingCT for short</strong></a><strong>. Is this change being done because the existing architecture can currently be broken or are you simply making provisions for the future?</strong></p>
    <p>Security is a process and there are always new attacks you need to defend against, so you can&#8217;t just sit by idly and say “now were done with security” &#8211; if you say you’re done, you’re not done! We are always asking ourselves how do we reduce time based attacks or meta data linkage which is clearly an issue when dealing with a blockchain as it containing lost of data for an attacker to analyse. Both with Bitcoin and Monero, the blockchain is like a Sudoku puzzle and we are making sure the Monero puzzle is significantly larger and thus harder to solve than the Bitcoin puzzle. People come up with interesting ideas of how Monero could be broken (which helps us refine our security) but nobody has come up with a concrete way of breaking Monero.</p>
    <p><strong>By switching to RingCT you will be replacing the so called ring signatures of you underlying protocol </strong><a href="https://cryptonote.org/"><strong>CryptoNote</strong></a><strong> (please correct me if I&#8217;m wrong). Is this comparable to changing the engine in your car? are you nervous something might break?</strong></p>
    <p>RingCT will be an additional ring signature. We are not replacing the core ring signature which is part of CrypoNote. This can be compared to a hybrid car, where we already have a petrol engine and now were adding an electric one as well. I am not nervous about something breaking, we are confident that our mechanism is robust as RingCT has been deployed on testnet (a blockchain in a testing environment) for months and we have spend a lot of time fiddling with it. On top of this, we designed Monero in a way that if you crack one mechanism, you don’t crack all of them. It is a great testament to the <a href="https://lab.getmonero.org/">Monero Research Lab</a> as well as <a href="https://github.com/gmaxwell">Greg Maxwell</a> who created confidential transactions in the first place.</p>
    <p><strong>Will people still be able to use older wallets such as hydrogen helix?</strong></p>
    <p>No, you will have to upgrade to use RingCT because your node will not understand the new transactions causing you to be forked off the network. That being said, we will never lock people out of their funds. As long as you have access to your wallet file or your 25 word mneumonic seed, you will be able to restore your wallet no matter how far into the future.</p>
    <p><strong>How far are you guys with RingCT?</strong></p>
    <p>Its done and running on testnet. RingCT will be launched on the main blockchain (mainnet) by January 2017. We actually pulled the deadline forward to enable people to start making RingCT transaction early, however RingCT transactions will be optional until September 2017. I recommend that by December people upgrade to the newest release of Monero, so that they don’t experience slow synchronization with the network.</p>
    <p><span style="text-decoration: underline;">Third party wallets</span></p>
    <p><strong>As you know, </strong><a href="https://jaxx.io/"><strong>Jaxx</strong></a><strong> (a popular web wallet) is planning to add Monero to its repertoire but is currently falling behind with its integration. Do you see any massive issues that threaten the integration and do you think users will be able to hold Monero in their Jaxx wallet before</strong></p>
    <p><strong>2017?</strong></p>
    <p>I’ve been dealing a lot with the Jaxx team and I must say they are really clued up and understand how Monero works. I don’t see any major issues that threaten the integration, but it is a challenge because Monero is not based on Bitcoin which means the entire integration needs to be done from scratch and this is a lot of work. I see Monero on Jaxx before 2017, the team is very motivated.</p>
    <p><a href="https://getmonero.org/getting-started/choose"><strong>Monero&#8217;s official website</strong></a><a href="https://getmonero.org/getting-started/choose"><strong> states that the full Monero client will &#8220;afford you the maximum privacy Monero has to offer&#8221;</strong></a><strong>. How much worse exactly is it when I choose an alternative to the full client i.e. not running my own node?</strong></p>
    <p>There is always a privacy compromise with not running your own node i.e. not downloading the blockchain and running the wallet software on your computer. When using a third party wallet you are reliant on someone else scanning every single transaction for outputs that belong to you and that means that they need to hold one part of your private key (the private view key). This does not let the third party spend your funds, but it allows them to see all your incoming transactions. We try to encourage our users to run full nodes because there is nothing worse than privacy theatre, where people think they are getting private transactions, but their actually not.</p>
    <p><span style="text-decoration: underline;">New GUI</span></p>
    <p><strong>The Monero developers have been working hard on a graphical user interface (GUI) which </strong><a href="https://github.com/monero-project/monero"><strong>source code</strong></a><strong> is now available. Is there any important Monero function you are still struggling to fit into the GUI?</strong></p>
    <p>Right now the basic functions such as sending &amp; receiving transaction and synchronizing with the network are all there. We do want to add more advanced functionality such as smart-mining which is a type of mining (blockchain review process) that runs is the background to a threshold and prevents your processor from burning out.</p>
    <p><strong>People with unstable internet connections might have a hard time downloading the blockchain. Will the new GUI support usage of remote nodes i.e. leaching of an existing blockchain?</strong></p>
    <p>Yes, it will support remote nodes, but again we are trying to discourage this, because the stress on the remote nodes that are open to this functionality will be insane. Also your level of privacy will be negatively affected if your are using a remote node because based on what you are doing, the node you are connected to can infer certain information that should be private to you.</p>
    <p><strong>If I download the new GUI and decide to run my own node, what&#8217;s the damage? How big is the blockchain?</strong></p>
    <p>The raw blockchain is at about 2.5 GB and once its on disk and denormalized for performance, it sits at just under 10 GB which will obviously grow over time but not at an insane rate&#8230; <a href="http://cryptomining-blog.com/tag/ethereum-blockchain-size/">unlike </a><a href="http://cryptomining-blog.com/tag/ethereum-blockchain-size/">Ethereum</a> [giggles].</p>
    <p><strong>How close are you to releasing official GUI binaries for Mac, Win and Linux? Can you tell me something about your built set-up?</strong></p>
    <p>When Monero 0.10.1 (named Wolfram Warptangent) is released we will publish the GUI binaries for all major OS&#8217;s as a separate download. We are still waiting for some contributors to finish of code, but I can image we will roll out the new release by the end of November. Our build set-up includes three versions of Mac, multiple versions of Windows, ARM, freeBSD, and Linux on 32 &amp; 64 bit.</p>
    <p><span style="text-decoration: underline;">The Future of Cryptocurrency</span></p>
    <p><strong>How do you envision the future of crypto-currency? do you reckon people will be taught cryptography at kindergarden and run their own crypto-currency nodes at home?</strong></p>
    [Laughs].. In an ideal world sure&#8230; People are slow to change, but when they do change, they adopt things whole heatedly. It was only a few years ago when everyone wanted to own a Blackberry because it had a full keyboard all other phones were a piece of junk.. Today its bizarre to even image a keyboard on a phone. When people start using cryptocurrecny not for investment purposes, but to actually pay and get paid with it, we will start to see the formation of a so called circular economy (an economy where all dealing are done with the same form of payment). There are signs that this might happened. <a href="http://backpage.com/">Backpage</a> (a goods and services site) for example had it&#8217;s VISA and Mastercard accounts shut down and is now only receiving Bitcoin. Because of this, Backpage starts paying its staff in Bitcoin who will then try to pay their rent in Bitcoin and so on. If we fast forward five or ten years it could very well be that this circular cryptocurrency economy will kick in and that people will stop having to constantly shift out of cryptocurrency i.e. into Dollars, Euros, etc.. and if that happens we know that cryptocurrency won – it will just take time.</p>
    <p><strong>Author&#8217;s Twitter: <a href="https://twitter.com/babysn00p">@babysn00p</a></strong></p>
    
    
    </div><!-- .entry /-->
    <span style="display:none"><a href="https://www.deepdotweb.com/tag/cryptocurrency/" rel="tag">cryptocurrency</a> <a href="https://www.deepdotweb.com/tag/current/" rel="tag">current</a> <a href="https://www.deepdotweb.com/tag/developments/" rel="tag">developments</a> <a href="https://www.deepdotweb.com/tag/fluffypony/" rel="tag">fluffypony</a> <a href="https://www.deepdotweb.com/tag/future/" rel="tag">future</a> <a href="https://www.deepdotweb.com/tag/interview/" rel="tag">interview</a> <a href="https://www.deepdotweb.com/tag/moneros/" rel="tag">moneros</a> <a href="https://www.deepdotweb.com/tag/talks/" rel="tag">talks</a></span>				<span style="display:none" class="updated">2016-11-29</span>
    <div style="display:none" class="vcard author" itemprop="author" itemscope itemtype="http://schema.org/Person"><strong class="fn" itemprop="name"><a href="https://www.deepdotweb.com/author/babysnoop/" title="Posts by babysnoop" rel="author">babysnoop</a></strong></div>
    
    
    </div><!-- .post-inner -->
</article><!-- .post-listing -->
