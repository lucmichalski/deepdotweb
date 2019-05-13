---
Introduction to Zcash, the anonymous Bitcoin
---
<article class="post-listing post-15564 post type-post status-publish format-standard has-post-thumbnail hentry category-articles category-deepdot-news tag-anonymous tag-bitcoin tag-introduction tag-zcash">
    <div class="post-inner">
    <p class="post-meta">
    <span>Posted by: <a href="https://www.deepdotweb.com/author/kptx/" title="">kptx </a></span>
    <span>September 29, 2016</span>
    <span>in <a href="https://www.deepdotweb.com/category/articles/" rel="category tag">Articles</a>, <a href="https://www.deepdotweb.com/category/deepdot-news/" rel="category tag">Featured</a></span>
    <span><a href="https://www.deepdotweb.com/2016/09/29/introduction-to-zcash-the-anonymous-bitcoin/#comments">6 Comments</a></span>
    </p>
    <div class="clear"></div>
    <div class="entry">
    <p>Bitcoin is an anonymous currency – this is one of greatest misconceptions surrounding Bitcoin which is, In a sense, the exact contrary of anonymous as every transaction is publicly listed on the Blockchain. Even though a wallet address does not reveal personal information about its owner, there are still ways to discover to whom the wallet belongs via blockchain analysis. This means that Bitcoin is a pseudonymous cryptocurrency since it replaces our personal information with a random segment of numbers and letters, a wallet address.</p>
    <p>When Bitcoin was first created, Satoshi Nakamoto mentioned the importance of using multiple addresses to preserve one&#8217;s privacy, and even doing so won&#8217;t save you from potential blockchain analysis. Using a coin mixer Is a less than ideal approach, as fungibility is not assured (The coins you get out may be &#8220;dirtier&#8221; than the ones you&#8217;ve put in). <a href="http://z.cash">ZCash</a> wants to solve these problems once and for all.</p>
    <p><em>&#8220;Privacy is necessary for an open society in the electronic age. Privacy is not secrecy. A private matter is something one doesn&#8217;t want the whole world to know, but a secret matter is something one doesn&#8217;t want anybody to know. Privacy is the power to selectively reveal oneself to the world.&#8221; </em>Eric Hughes, A Cypherpunk&#8217;s Manifesto</p>
    <p>Forked from Bitcoin, ZCash (ZEC) has many similarities to it, like the 21 million supply cap, the 4 years halving timeframe, and although ZCash offers faster blocks and smaller rewards they add up to Bitcoin&#8217;s issuance rate.</p>
    <p>ZCash makes use of ZK-Snarks (zero-knowledge Succinct Non-interactive ARgument of Knowledge) to deliver 100% untraceable transactions. In ZCash, coins can be transparent or protected. When value is transparent it behaves just like it would with Bitcoin and can be seen by anyone on the public ledger.</p>
    <p>When value is protected it is carried by notes that specify an amount and the destination address. The destination address will have two public keys, the paying key, and the transmission key. The transmission key is used to encrypt the payments in a &#8220;key-private asymmetric encryption scheme&#8221;, meaning that there is no way to connect the encryption to the public key it was encrypted to. The only person that can decrypt the information is the holder of the private key that corresponds to that transmission key, which is called the viewing key. Since the encryption is key-private, other users cannot see the amount that is being transferred, nor can they associate the encrypted transaction to the transmission key owner. The key owner can now use the viewing key to scan the blockchain and decrypt the note that was sent to him, allowing him to know where the coins were sent from.</p>
    <p>To each note there is a cryptographically associated note commitment, and a nullifier that are publicly known. The nullifier ensures that the spent coins cannot be double-spent, and the note commitment allows them to be used by the new owner. Although these are connected, it is impossible to correlate the commitment with its nullifier without knowing the transaction they refer to, and it is also impossible to compute the nullifier without the destination&#8217;s spending key, which is the equivalent of a private key in Bitcoin as it allows you to spend the coins owned.</p>
    <p>What we&#8217;re left with is a system, where the validators know that there is no double-spending going on due to the commitments that are made, but the spender is only required to prove that some commitment has been revealed without revealing which one, meaning that there is no way to link an amount of spent coins to the transaction in which they were spent. This puts Zcash at an advantage when compared with other anonymous cryptocurrencies that mix a limited number of transactions between themselves, and thus are easier to track.</p>
    <p>Bitcoin uses SHA256 as a Proof of Work algorithm, and the development of Application-specific integrated circuit miners for that algorithm has led the mining difficulty to increase exponential putting Bitcoin mining in the hands of a few large operations. ZCash will use a new asymmetric memory-hard algorithm that makes ASIC development unfeasible, Equihash. This is extremely important to ensure that mining does not become centralized as it has become with Bitcoin, but it also has a downside, as it makes Zcash the perfect candidate for botnet mining since it&#8217;s an untraceable cryptocurrency with a CPU friendly algorithm.</p>
    <p>Zcash will have no premine or Initial Coin Offering period, and will instead have a &#8220;Founder Reward&#8221;, which will be deducted from the block rewards mined for the first 4 years. 20% of the block rewards will be allocated to the Zcash team and its initial investors during this time, which will amount to 10% of the total zcash supply, 21 million ZEC.</p>
    <p>Zcash was set to launch on the 26<sup>th</sup> of September, but its release date was pushed back to October 28<sup>th</sup> to give time for additional auditing, which will be performed by three separate auditing companies. The Beta testnet is currently live and can be run by anyone by following the official <a href="https://github.com/zcash/zcash/wiki/Beta-Guide">zcash beta guide</a>. Despite having no value, testnet coins or TAZ can be mined by following the <a href="https://www.cryptocompare.com/mining/guides/how-to-mine-zcash/">Zcash mining guide</a>.</p>
    <p>Despite its anonymous nature, it is highly unlikely that zcash will be used in the deep web markets anytime soon for two reasons:</p>
    <ul>
    <li>In order for exchanges to add zcash has a trading pair, a fair amount of Zcash needs to be mined, in order to provide exchange liquidity.</li>
    <li>Zcash is untested technology and much can go wrong. It took the deepweb 2 years to add Monero, and the same may happen to Zcash.</li>
    </ul>
    <p>But if Zcash withstands the trial of time, it is possible that it may one day become the currency of the deepweb.</p>
    <p><em>&#8220;As much as people now love the idea and the benefits of blockchain technology, time and time again they bring up two issues that blockchains currently do not address: scalability and privacy. I believe that the technology that Zcash is working on is currently the best in class in its ability to address the privacy challenge.&#8221; </em>Vitalik Buterin, Founder and Chief Scientist at Ethereum.</p>
    </div>
    <span style="display:none"><a href="https://www.deepdotweb.com/tag/anonymous/" rel="tag">anonymous</a> <a href="https://www.deepdotweb.com/tag/bitcoin/" rel="tag">bitcoin</a> <a href="https://www.deepdotweb.com/tag/introduction/" rel="tag">introduction</a> <a href="https://www.deepdotweb.com/tag/zcash/" rel="tag">zcash</a></span> <span style="display:none" class="updated">2016-09-29</span>
    <div style="display:none" class="vcard author" itemprop="author" itemscope itemtype="http://schema.org/Person"><strong class="fn" itemprop="name"><a href="https://www.deepdotweb.com/author/kptx/" title="Posts by kptx" rel="author">kptx</a></strong></div>
    </div>
</article>
