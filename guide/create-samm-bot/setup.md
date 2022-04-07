# Setup

## Bot Lifecycle

The entire lifecycle of a bot can be described as the following:

#### 1. Grid trigger (Optional and Coming Soon)

> This optional parameter determines if the bot will immediately start or get triggered when the market price reaches the triggering price.

#### 2. Bot initialization

> Params 1, 2, 3, 4, 5, 10 determines the grid structure.&#x20;

#### 3. Open position for Long/Short strategy

> For `neutral` strategy, the bot will start without any position
>
> For `Long` strategy, the bot will start will a long position proportional to the grid setup
>
> For `Short` strategy, the bot will start will a short position proportional to the grid setup

#### 4. Place grid orders

> The bot will place sell orders above the market price and buy orders below the market price.&#x20;

#### 5. Update grids as market moves

> As the market moves, certain orders will get filled and new orders will be placed accordingly.

#### 6. Stop trigger (Optional and Coming Soon)

> This is another optional parameter that allows bot to stop itself when the price drops below the lower stop limit or when the price goes above the upper stop limit.

#### 7. Stop bot

> Manually stop the bot operations when desired. All the potions and open orders will remain untouched. But bot won't create new orders.

#### 8. Close bot (4 steps)

> This is a manual process to close bot completely in 4 separate steps:
>
> 1. Close open orders and redeem market making rewards
> 2. Settle PnL (Profit and Loss)
> 3. Withdraw from mango
> 4. Withdraw from bot

{% hint style="info" %}
Note: Cell charges 10% performance fee, when the bot is profitable. No fees will be charged if the bot is losing money.
{% endhint %}

## Bot Parameters



![Create Bot Form](<../../.gitbook/assets/image (3) (1).png>)

#### 1 - Bot Name

The name of your bot is randomly generated for you. But you can always name it differently. This is mainly for others to see it when it reaches the Top 10 for a given pair.

#### 2 - Bot Type

`Long`: the bot starts with long position and then executes grid buy and sell trades, ideal for trending and volatile bull markets&#x20;

`Short`: the bot starts with short position and then executes grid buy and sell trades, ideal for trending and volatile bear markets&#x20;

`Neutral`: the bot starts with no position and then executes grid buy and sell trades, ideal for range-bound markets without clear directions

`Enhanced Neutral`: similar to neutral bot but clears any long or short position every 6 hours, ideal for volatile markets without clear directions

{% hint style="info" %}
Note: This cannot be changed once bot started
{% endhint %}

#### 3 - Grids (Grid Count)

This defines the density of the grid. The denser the grid you specify, the higher the frequency of trades will be. However your per grid is also lower. So it’s a tradeoff between many small trades vs. fewer larger trades.

The minimum is 2

The maximum is 100

{% hint style="info" %}
Tip: Market making (placing bids and asks) on certain protocols, like Mango Market, has extra **rewards**. So a higher frequency could translate into a higher profit from rebating.
{% endhint %}

#### 4/5 - Lower & Upper Price

Set the lower price and upper price of the grid range. If the bot is out of range, no more positions will be opened.

For a BTC Long bot, assuming the price range is set to be $40,000 \~ $50,000

* if the market price moves up to $51,000, the bot will sell all your BTC and get a full bag of USDC, so you are forced to sell high and take profit
* if the market price moves down to $39,000, the bot will buy low and the rest of the USDC will be used to purchase BTC.

{% hint style="info" %}
Note: This cannot be changed once bot started
{% endhint %}

#### 6 - Start Price

This is the market price when bot starts. Bot will open a position based on the start price for a Long/Short strategy if no Grid Trigger specified.

{% hint style="info" %}
Note: This is determined by bot
{% endhint %}

#### 7 - Grid Quantity (Qty/Order)

> grid\_quantity = total\_investment / sum(prices)

#### 8 - Grid Interval

> grid\_interval = (grid\_upper\_limit - grid\_lower\_limit) / grid\_count __&#x20;

#### 9 - Profit / Grid

> profit\__per\__grid = grid\__interval \* grid_\_quantity + rebate

#### 10 - Amount

Total investment amount.

{% hint style="info" %}
Note: You CANNOT deposit more once bot is created. But you can copy the param and crate another bot if you want to add more investment.
{% endhint %}

#### 11 - Lower Stop Limit (Stop Loss)\*

This is optional.

Coming soon

#### 12 - Upper Stop Limit (Take Profit) - Optional\*

This is optional

Coming soon
