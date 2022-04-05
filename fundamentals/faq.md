# FAQ

## Does Bot charge trading fees like CEXs do?

Cell currently integrates with Mango Market with Serum on the pipeline. Neither CLOB DEXs charge fees for bid/ask limit orders.

In fact, if the bot is running on protocols like Mango Market, you will be receiving MNGO as [market making rewards](https://docs.mango.markets/mango/liquidity-incentives).&#x20;

## What happens when Bot is out of range?

If the bot is out of range, no more positions will be opened.

For a BTC Long bot, assuming the price range is set to be $40,000 \~ $50,000

* if the market price moves up to $51,000, the bot will sell all your BTC and get a full bag of USDC, so you are forced to sell high and take profit
* if the market price moves down to $39,000, the bot will buy low and the rest of the USDC will be used to purchase BTC.

For a Short bot, it's basically the opposite of it.

For a Neutral bot, you will be holding roughly half of the total investment in short/long positions.

## What are the differences between Long, Short, and Neutral strategies?

`Long`: the bot starts with long position and then executes grid buy and sell trades, ideal for trending and volatile bull markets&#x20;

`Short`: the bot starts with short position and then executes grid buy and sell trades, ideal for trending and volatile bear markets&#x20;

`Neutral`: the bot starts with no position and then executes grid buy and sell trades, ideal for range-bound markets without clear directions

`Enhanced Neutral`: similar to neutral bot but clears any long or short position every 6 hours, ideal for volatile markets without clear directions

