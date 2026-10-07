# GROUPCHAT: Telegram alerts for FOMO and Pump.fun traders

GROUPCHAT is a Telegram bot that sends real-time alerts of what top traders do on
[FOMO](https://fomo.family) and on Pump.fun: buys, sells, written theses and callouts,
each with the contract address and one-tap links to Axiom, Terminal and Dexscreener.
It does not trade for you.

- Bot: https://t.me/GROUPCHAT_ALERTS_BOT
- Website: https://groupchat-bot.tech
- Status: live. Free trial on Telegram; the current price is shown in the bot with /subscribe.

This repository holds public documentation and methodology only. The bot's source code
is not published here.

> GROUPCHAT is an independent project. It is not affiliated with, endorsed by or
> operated by FOMO or Pump.fun.

## What it does

| | |
|---|---|
| Platforms | FOMO trader activity and Pump.fun callouts |
| FOMO chains | Solana, BNB Chain, Base, Ethereum, Monad, Robinhood Chain, Arc |
| Alert types | Buys, sells, theses (the trader's stated reason and bag size), callouts, and Trending alerts when 5+ tracked traders buy the same coin within 30 minutes |
| In every alert | Contract address, trade size and market cap, one-tap links (Axiom, Terminal, Dexscreener and more) |
| Filters | Per chain, minimum trade size, individual traders or whole styles |
| Traders tracked | 1,100+, each scored 0 to 100 |
| Delivery | Telegram, so no tab to keep open and it works with your phone locked |

## How it works

1. Start the bot on Telegram. The free trial begins on /start.
2. Choose who to follow: pick individual traders from the table, or follow a style
   (Day holds, 1h flips, Multi-day holders and others). New traders that fit a style are
   added for you.
3. Set optional filters (chains, minimum trade size).
4. Alerts arrive in your Telegram chat as the activity appears on the source feed.

You sign in with Telegram. The bot never asks for a private key or seed phrase. Anyone
who asks you for one is not us.

## How traders are scored

Most trader rankings use the trader's own fills. That ignores the gap between their trade
and your alert. GROUPCHAT replays each call from the last 30 days against price candles as
if you had bought about one minute after the alert, after fees, and scores the result from
0 to 100. A call is a FOMO trader's first buy into a token, or a Pump.fun callout.

Each trader profile shows: score, share of calls that rose 50% within 15 minutes of the
alert, typical time to peak within 24 hours, typical entry market cap, calls analysed,
alerts per day, and how high each of their last 12 calls ran (and where it stood an hour
later). Traders whose alerts lost money on average for followers are muted; traders with
too few calls are marked unrated.

This is a historical replay, not a prediction. A high score can still lose.
Details: https://groupchat-bot.tech/how-we-score-traders

## Speed: how it was measured

| Measurement | Result |
|---|---|
| Window | Oct 5 to Oct 8, 2026 |
| Sample | 8,521 FOMO alerts |
| What is timed | From the moment the trade shows up on the source feed to the moment the first Telegram message is posted |
| Median time to post | 0.34 s |
| Posted in under 1 s | 94% |
| Covers 9 in 10 alerts | within 0.8 s |
| Pump.fun callouts | median 0.31 s, 95% under 1 s |

Distribution of FOMO alerts by time to post:

| 0 to 0.25 s | 0.25 to 0.5 s | 0.5 to 0.75 s | 0.75 to 1 s | 1 to 2 s | 2 to 5 s | 5 s+ |
|---|---|---|---|---|---|---|
| 29.2% | 48.2% | 12.0% | 4.6% | 3.9% | 1.4% | 0.7% |

What this does not include: any delay before a trade appears on the source feed, and the
time Telegram takes to deliver the message to your device. These figures describe
GROUPCHAT's own processing, and will be re-measured and dated here when they change.

## Price

Free trial, then a 30-day plan paid inside the bot with /subscribe. It does not
renew automatically. After the trial ends without a subscription, alerts are limited:
contract addresses and links are hidden.

## Links

- Home: https://groupchat-bot.tech
- FOMO trader alerts in Telegram: https://groupchat-bot.tech/fomo-trader-alerts
- Pump.fun callout alerts in Telegram: https://groupchat-bot.tech/pump-fun-callouts-alerts
- How GROUPCHAT scores traders: https://groupchat-bot.tech/how-we-score-traders
- Terms: https://groupchat-bot.tech/terms
- Privacy: https://groupchat-bot.tech/privacy

## Contact

Message the bot on Telegram: https://t.me/GROUPCHAT_ALERTS_BOT

## License

Documentation in this repository is licensed under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The bot itself is proprietary.
