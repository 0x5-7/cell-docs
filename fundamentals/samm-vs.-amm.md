# SAMM vs. AMM

## AMMs&#x20;

Let’s start with the shining moment of AMMs. One of the primary reasons why AMMs took off on Ethereum was because of its simplicity (no flexibility) and hence computational efficiency. The Ethereum network was too slow and expensive to support fully on-chain orderbook DEXs. That’s why lots of the CLOBs back then were fully off chain or hybrid.

Another game changer was the permissionless nature of DEX where everyone can just create a pair and inject liquidity into the pool. No sophisticated Algorithms or Bots are needed. That’s why there were and still are much more trading pairs on DEXs compared to CEXs.

There are other less-obvious advantages that are worth mentioning as well. AMMs are highly composable, you chain multiple hops very easily, compared to manually doing multiple hops on a CLOB. As a MM, you provide bi-directional liquidity by default on both sides.

## CLOBs&#x20;

2021 was the year of Alt L1s and L2s. Solana and Avalanche were some of the top L1s that stood out because of their high scalability. Then we started to see the explosion of CLOB DEXs like Serum (spot) and MangoMarket (perpetual) that benefited substantially from the sub-second block time and 65k TPS on Solana. We also saw dydx trading volume surpassing Coinbase.

The key benefit of CLOBs over AMMs is really the flexibility.&#x20;

* You can build AMM on top of CLOB by simulating the constant product curve. But not so much the other way around.&#x20;
* You can place limit orders at your expected price target as opposed to market buy/sell all the time on CPMMs.&#x20;
* You can build derivatives markets that allow users to hedge risks (with options) and access leveraged trading.&#x20;

On the other hand, if CLOBs can offer a similar user experience of CEX w/o KYC and much less fees, I can see its clear benefits. Remember not your keys, not your coins.

## SAMMs&#x20;

Then how does SAMM come into play? You might have noticed that CLOB is really missing the democratization of market making and the easiness of long-tail assets provision, and that is exactly what SAMM does to close the gap.

SAMM, or Smart AMM, is the liquidity gateway for CLOBs via simplified and automated LP tools. Whoever you are, there is a special space for you to explore and participate. Liquidity providers can seamlessly create or copy grid LP strategies like pro market makers, and capture high APY from price fluctuation. Crypto projects can accurately incentivize community LPs with native tokens, and build products atop with our highly-composable modules. CLOBs can enjoy lower slippage, better depth, and more markets.

You might have asked: what’s the difference between AMM and SAMM then? Why is it smart? We believe SAMM is superior to AMM in terms of strategy flexibility and composability. You could apply a _`short`_ and _`neutral`_ strategy compared to a default `long` strategy for AMMs, as well as apply leverages, which adds lots of flexibility. In addition, other financial products and protocols can be built atop our highly-composable modules.
