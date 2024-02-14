# AustralianHedging Expert Advisor

The AustralianHedging Expert Advisor is a trading robot developed by the Forex Robot Easy Team. It utilizes an inverse correlation strategy to trade two currency pairs, EURUSD and AUDUSD. This strategy takes advantage of the negative correlation between these two pairs, opening trades when the correlation is high.

## Input Parameters

- FirstPair: The first trading tool, default is 'EURUSD'.
- SecondPair: The second trading tool, default is 'AUDUSD'.
- TradeFrequency: The frequency of trades in minutes, default is 1.

## Expert Initialization

The OnInit() function is the initialization function of the Expert Advisor. It enables auto-trading and validates the input parameters. If auto-trading is not enabled or the trading tools are not specified, the initialization will fail.

## Expert Tick

The OnTick() function is the main function that is called on every tick. It checks the trade frequency and only executes trades if the specified time has passed since the last trade. It calculates the inverse correlation between the two currency pairs using the iCorrelation() function and checks if the correlation is above 0.8. If the correlation is high, it opens trades with a lot size calculated based on the account balance. The trades are opened with the OrderSend() function and the ticket numbers are stored for error checking. The last trade time is updated after executing the trades.

## Expert Deinitialization

The OnDeinit() function is the deinitialization function of the Expert Advisor. It is called when the Expert Advisor is removed from the chart or when the terminal is closed. It closes all open trades by iterating through the orders using the OrdersTotal() function and closing each order with the OrderClose() function.

For detailed reviews and trading results of this product, please visit [this link](https://forexroboteasy.com/forex-robot-review/australianhedging-review-expert-inverse-correlation-strategy/).

Please note that ForexRobotEasy is not the official developer of this product. We only provide this sample code that can work as described in the product. To find the official developer of this product, please use MQL5.
