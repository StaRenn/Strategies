![npm](https://img.shields.io/npm/v/@debut/community-core)
![npm](https://img.shields.io/npm/dm/@debut/community-core)
![NPM](https://img.shields.io/npm/l/@debut/community-core)
[![Support me on Patreon](https://img.shields.io/endpoint.svg?url=https%3A%2F%2Fshieldsio-patreon.vercel.app%2Fapi%3Fusername%3Dbusinessduck%26type%3Dpatrons%26suffix%3DEnterprise%2520users&style=flat)](https://patreon.com/businessduck)
[![Telegram crypto trading orders stream](https://badgen.net/badge/tg/crypt:stream/blue?icon=telegram)](https://t.me/debutjs)
[![Telegram stocks trading orders stream](https://badgen.net/badge/tg/stocks:stream/cyan?icon=telegram)](https://t.me/debutjs2)
# Trading Strategies Based on Debut/Community Edition

Debut is an ecosystem for developing and launching trading strategies. An analogue of the well-known `ZenBot`, but with much more flexible possibilities for constructing strategies. All you need to do is come up with and describe the entry points to the market and connect the necessary [plugins](https://github.com/debut-js/Plugins) to work. Everything else is a matter of technology: **genetic algorithms** - will help you choose the most effective parameters for the strategy (period, stops, and others), **ticker selection module** - will help you find an asset suitable for the strategy (token or share), on which it will work best.

Debut is based on the architecture of the core and add-on plugins that allow flexible customization of any solutions. The main goal of the entire Debut ecosystem is to simplify the process of creating and launching working trading robots on various exchanges.

## Available for

<p>
    <img src="https://github.com/debut-js/Core/blob/master/.github/assets/alpaca.png" alt="Alpaca API" width="64">
    <img src="https://github.com/debut-js/Core/blob/master/.github/assets/binance.png" alt="Binance API" width="64">
    <img src="https://github.com/debut-js/Core/blob/master/.github/assets/tinkoff.png" alt="Tinkoff API (Russia only)" width="64">
    <a href="https://www.patreon.com/bePatron?u=57560983"><img src="https://github.com/debut-js/Core/blob/master/.github/assets/buy2.png" alt="Request implementation" width="64"></a>
</p>

## Community edition
We believe in the power of the community! That is why we decided to publish the project. The community version is free, but it has some limitations in commercial use (income from trading startups is not commerce), as well as technical differences in testing strategies. Join the community, join **[developer chat](https://t.me/joinchat/Acu2sbLIy_c0OWIy)**

## Enterprise edition ($15/mo [buy now!](https://www.patreon.com/bePatron?u=57560983))
The Enterprise version is a fully functional version of Debut, with a maximum of possibilities for emulating real market behavior.

Aggregation of candles:
All candles are aggregated from incoming data from shorter time periods. This allows you to get access to any timeframe on the fly with only 1 candle stream real by subscription. So you can get daily candles from 15 minute ones.

Tick ​​emulation:
On the basis of candlestick aggregation, a mechanism for filling candles of any timeframe from OHLC / OLHC ticks of 1-minute candles has been created. This allows you to create more than 60 price ticks in one 15-minute interval or 240 ticks inside each 1 hour candle.

<table>
<thead>
<tr>
<th> Functionality </th>
<th> Community </th>
<th> Enterprise </th>
</tr>
</thead>
<tbody> <tr>
<td> Strategy Tester </td>
<td align="center"> ✅ </td>
<td align="center"> ✅ </td>
</tr>
<tr>
<td> Emulation of OHLC ticks in the tester </td>
<td align="center"> ✅ </td>
<td align="center"> ✅ </td>
</tr>
<tr>
<td> Search modle (finder) suitable for the strategy of assets </td>
<td align="center"> ✅ </td>
<td align="center"> ✅ </td>
</tr>
<tr>
<tr>
<td> M1 candlestick data for tick emulation </td>
<td align="center"> ❌ </td>
<td align="center"> ✅ </td>
</tr>
<tr>
<td> Synthetic emulation of ticks in the tester (tick size no more than 0.75%) </td>
<td align="center"> ❌ </td>
<td align="center"> ✅ </td>
</tr>
<tr>
<td> Access to major candles from working timeframe</td>
<td align="center"> ❌ </td>
<td align="center"> ✅ </td>
</tr>
<tr>
<td> <b>Alpaca</b> supports `5min`, `15min` and others Debut timeframes </td>
<td align="center"> ❌ </td>
<td align="center"> ✅ </td>
</tr>
</tbody> </table>

## Strategy Import from TradingView ($1000 [buy now!](https://www.patreon.com/bePatron?u=57560983))
If you need help transferring a strategy from TradingView to the Debut ecosystem. Transferring a strategy takes up to 3 business days. You can also request to create a strategy based on an article or your own formula.

We are streaming Enterprise-based deals live on our [telegram channel](https://t.me/debutjs)

**Find out the price by sending a request to [sales@debutjs.io](mailto:sales@debutjs.io)**

**Remember!** Starting a bot and trading in general requires careful study of the associated risks and parameters.
Incorrect settings can cause serious financial losses.

The project has two starting trading strategies "For example" how to work with the system.

An example of the strategy [SpikesG](/src/strategies/spikes-grid/ReadMe.md) in 200 days. Optimization was carried out in 180 days and 20 days of free work on untrained data.
An initial deposit of *$500 was used*

<p align="center"> <img src="/src/strategies/spikes-grid/img/BATUSDT.png" width="800"> </p>

Strategy statistics were collected based on the [plugin statistics](https://github.com/debut-js/Plugins/tree/master/packages/stats), follow the link to learn more about the meaning of some statistics.

Visualization is done using the [Report plugin](https://github.com/debut-js/Plugins/tree/master/packages/report).

## System requirements
To work, you need [NodeJS 14.xx/npm 7.xx](https://nodejs.org/en/) ([installation instructions](https://htmlacademy.ru/blog/boost/tools/installing-nodejs))

## [Documentation](https://debutjs.io)

## Project file structure

```
| - .tokens.json - custom access tokens for working with the exchange
| - schema.json - description of the location of the startup files
| - public/- folder for finder reports (created when finder starts)
| - src/
    | - strategies/
        | - strategy1/- strategies directory
            | - bot.ts - Strategy implementation
            | - meta.ts - Meta data, for launching and for optimization
            | - cfgs.ts - Configurations, for launching in tester and genetic
        | - strategy2/
        ...

```

# Installation and configuration

### Obtaining API tokens

### Installing tokens
To work, you need to create a .tokens.json file, add a token to it for work.

For Tinkoff ([instructions](https://tinkoffcreditsystems.github.io/invest-openapi/auth)):

```json
{
    "tinkoff": "YOUR_TOKEN",
    "tinkoffAccountId": "YOUR_ACCOUNT_ID",
}

Get your tinkoff accounts by this hack and copy one of available account identity to `tinkoffAccountId`:

```javascript
tinkoffTransport.api.users.getAccounts({}).then(res => {
    console.log(res);
});
```

For Binance ([instructions](https://www.binance.com/ru/support/faq/360002502072)):
```json
{
    "binance": "YOUR_TOKEN",
    "binanceSecret": "YOUR_SECRET"
}
```

For Alpaca ([Alpaca instructions](https://alpaca.markets/docs/api-documentation/api-v2/)):
```json
{
    "alpacaKey": "YOUR_TOKEN",
    "alpacaSecret": "YOUR_SECRET"
}
```
All tokens can be getted by call: `cli.getTokens()` also you can use any field name for the token.

## Installing npm packages
To install packages, run:
```bash
npm install
```

## Creating strategy
Command will create strategy in src/strategies direction with bot.ts, cfgs.ts and meta.ts files inside and add it to schema.json
```bash
npm run plop StrategyName
```

## Build the project
```bash
npm run compile
```

*It is recommended to build before each test run*

` npm run compile && npm run ... `

## Start testing on historical data
Historical data will be loaded automatically at startup All loaded data is saved in the `history` folder in the root of the project, then reused.

**Before starting, make sure:**
* The `cfgs.ts` file contains the ticker you need
* To get history in the` .tokens.json file `a token may be required
* The history of a stock or token exists in the requested number of days

To start, run the command:
```bash
npm run testing -- --bot=FTBot --ticker=CRVUSDT --days=200 --gap=20
```

To view the test results in a browser, execute
```bash
npm run serve
```

The results will be available for viewing on `http://localhost: 5000/`

You can read more about the test run parameters in the [documentation](https://debutjs.io/ru/#/)

## Run genetic optimization

Run the command:

```bash
npm run genetic -- --bot=FTBot --ticker=CRVUSDT --days=200 --gap=30 --gen=12 --pop=2000 --log
```

More details about the launch parameters of the genetics can be found in the [documentation](https://debutjs.io/)

After starting with the --log parameter, the geneticist will output data to the console

```bash
Binance history loading from Wed Nov 18 2020 03:00:00 GMT + 0300 (Moscow Standard Time) ...

----- Genetic Start with 17314 candles -----

Generation: 0
Generation time: 5.15 s
Stats: {
   population: 100,
   maximum: 20.8,
   minimum: -1.24,
   mean: 2.5174,
   stdev: 3.8101996325652054
}
Generation: 1
...
```

## Run genetic optimization with tickers/tokens selection
Run the command:
```bash
npm run finder -- --bot=FTBot --ticker=CRVUSDT --days=200 --gap=30 --gen=12 --pop=2000 --log
```
Use the `--crypt` option to take crypto pairs from the`./Crypt.json` file (By default, there are actual Binance cross-margin pairs)

By default, a set of stock tickers is used for streaming optimization from the file `stocks.json`

You can read more about the parameters for launching streaming genetics in the [documentation](https://debutjs.io/)

## Starting a strategy

Install any process manager for NodeJS, for example PM2,,,

```bash
npm install -g pm2
```

Execute the launch command, the path to the strategy launch file in the `./Out` directory.
An example of such a file can be found here `/src/bootstrap.ts`

``` bash
pm2 start ./out/bootstrap.js
```

Further, for operation and monitoring, you can use `pm2` command:

`pm2 list` - a list of active processes

`pm2 delete $ pid` - stop a process

`pm2 log` - to view the logs of running processes

and other commands, which can be found in the documentation of the process manager.

# Debut is flexible for any tools

## Buy / Sell ratio

A measure of the activity rating of buyers and sellers for several pairs. This tool is based on the method of counting all purchases listed on the exchange and all sales, they are calculated for several large tokens dominating the market. Parameter `tickers` = ['ETH', 'BTC', 'ETC', 'XRP']; A fast and slow moving average (SMA) is used to smooth and track changes in activity. Further, for less voluminous tokens (altcoins), the correlation between the change in their price and the change in the buyer's index is calculated. Deals are formed for a certain coin according to the simple logic that if the buyer's activity is above 50% and the price correlation is high, or the share of buyers is less than 50% and the price correlation is high (falling).

#### Start
```bash
npm run compile && node ./tools/buysellratio/index.js
```

### Screenshot
![preview](.github/workflows/bsratio.png)
