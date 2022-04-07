---
description: $$$
---

# Profits

## Profits Breakdown

There are 2 major sources of profit running a grid bot, `Bot Profit` and `Position Profit`

### Bot Profit

{% hint style="success" %}
bot\_profit = strategy\_profit + market\_making\_rewards
{% endhint %}

#### Strategy Profit

This is the gain by executing the grid strategy 7/24. The bot will constantly enqueue the Buy/Sell orders in a LIFO (Last In, First Out) manner, and make money by earning the price difference of a single (or sometimes multiple) grid interval(s).&#x20;

$$
Profit_i = Q * D_i
$$

$$
P_b = Profit_1 + Profit_2 + ... + Profit_n
$$

Let's take a look at an example below. Assume we have a grid setup for ETH that goes between 2500 \~ 3500, with a $200 interval, and the qty/order is 1ETH. Then the sequence of the orders would be:

Initial:  1ETH@3200                                                                            -> queue size = 1

t1:        1ETH@3200    |    1ETH@3100                                              -> queue size = 2

t2:        1ETH@3200    |    1ETH@3100    |    1ETH@2900                -> queue size = 3&#x20;

t3:        1ETH@3200    |    1ETH@3100                                              -> queue size = 2

At t3, the first order match (Buy2@2900 and Sell1@3100) happens, and bot helps us make a $200 profit with a grid quantity (Q) of 1ETH, and price difference (Di) of $200.

$$
Profit_1 = 1ETH * ($3100 - $2900) = $200
$$

![](<../../.gitbook/assets/image (4).png>)                     ![](<../../.gitbook/assets/image (7).png>)     &#x20;



#### Market Making Rewards&#x20;

This comes from rebates received when the bot places limit orders on the orderbook.&#x20;

![Mango Market, for example, gives 3bp (0.03%) Maker rewards currently.](<../../.gitbook/assets/image (1).png>)

### Position Profit

Position profit (P\_p) is self explanatory. It is the profit by holding the positions since bot started. This can also be a loss in the case of a reversal market from the time your strategy started.

{% hint style="success" %}
position\_profit = (current\_market\_price - avg\_position\_cost) \* position\_size
{% endhint %}

### APR

We show Bot APR (APR\_b) and Total APR (APR\_t) throughout the product. They are calculated as following:

$$
APR_b = (P_b / Investment) / Duration * 365
$$

$$
APR_t = ((P_b + P_p)/ Investment) / Duration * 365
$$

## How to check Bot Profits?

You can go to the Portfolios page to check profits of all your running bots.&#x20;

