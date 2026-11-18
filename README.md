# Betting Suite Pro

**Real odds compared across bookmakers, betting math tools and a personal betting journal — built with Python and Streamlit.**

🔗 **Live app:** https://ai-betting-suite-pro-e4yhr2juf86jm8kxdhfq2v.streamlit.app/

![Betting Suite Pro](https://media.contra.com/image/upload/w_1100/w80ri4y0bv9wag6hdkur.png)

> This is a showcase repository. The application source code is kept private.

---

## What it does

Betting Suite Pro helps sports bettors decide with numbers instead of gut feeling.

- **Real odds comparison** — best available odds across bookmakers. If a market is missing, the app leaves it out instead of inventing data.
- **Value and surebet scanners** — find prices that beat the market.
- **Betting math tools** — surebet, Kelly stake sizing, hedging and bet-slip calculators, with the formulas shown so every result can be checked.
- **Personal journal** — log bets and results, and set your own play limits.
- **Odds movement history** — the server stores the best price over time for each competition.
- **Closing Line Value (CLV)** — link a bet to a real match and compare your odds with the last price before kick-off. CLV measures price quality; it does not promise profit.
- **Saved alerts** — value or odds-movement rules, with an optional Telegram summary.
- **Accounts** — registration, login and an optional "keep me signed in for 30 days" on personal devices.

## Tech stack

| Area | Tools |
|---|---|
| App & UI | Python, Streamlit |
| Database & auth | Supabase (PostgreSQL with Row Level Security) |
| Data sources | The Odds API, football-data.org, API-Football, TheSportsDB |
| Notifications | Telegram Bot API |
| Testing | pytest, with a simulated Streamlit layer |
| Deployment | Streamlit Community Cloud, GitHub Actions |

## How it is built

- **Thin UI, pure logic.** The Streamlit interface contains no formulas; all betting math lives in a separate, side-effect-free module that is fully unit-tested.
- **Separate data layer.** External APIs and database access each have their own module, so a provider can be swapped without touching the UI.
- **Security in the database, not only in the app.** Access rules (who can read which journal entries, voucher limits, admin rights by account ID) are enforced with Supabase Row Level Security policies and SQL migrations.
- **API budget control.** Odds are cached for 30 minutes and new requests stop when remaining credits run low, so the free API tier lasts the whole month.
- **Offline tests.** The test suite runs without internet access or API keys.

## Responsible use

Gambling is regulated. The app includes self-set play limits, and any paid access must follow local licensing, age (18+) and responsible-gambling rules.

---

## About the builder

Built by **Ioan Rus** — business launch strategist and MVP builder. I help founders, coaches and small businesses turn an idea into a live product: offer, landing page, email funnel and working web app.

- Portfolio & services: https://contra.com/john_rus_h7defuit
- Malt: https://www.malt.com/profile/ioanrus
