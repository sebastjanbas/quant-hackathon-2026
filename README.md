# Quant Hackathon App

**A personal finance and portfolio app with live market data and Monte Carlo risk simulation, built in 8 hours.**

University of Idaho Quant Hackathon 2026 · Team of 2 · 🏅 **Special Mention**

<!-- TODO: add a screenshot of the portfolio dashboard or simulation results -->

---

## What it does

- **Portfolio:** holdings, sector breakdown, and profit and loss, with **live stock and crypto prices** streamed into the dashboard
- **Risk simulation:** Monte Carlo projection of how your money could grow
- **Budget:** income and expense tracking with a "how long could I last" survival calculator
- **Accounts:** sign-in and protected routes

## What I built

- **Live market-data layer:** a Socket.io server streams prices from the Alpaca API to every connected client, so the portfolio updates without refreshing.
- **Auth and data:** authentication with route protection (Better Auth), the PostgreSQL layer, and app routing.
- **Portfolio module:** P&L calculations and keeping the dashboard in sync with live prices.
- **Monte Carlo simulation:** the user picks how much of their income goes into savings versus stocks and how many simulation runs to perform. The app simulates many possible futures and shows the range of outcomes, so the user can see which split tends to give the best return for the risk.

## Decisions under an 8-hour limit

- **Push, not polling:** a single WebSocket feed instead of every client polling for prices. Fewer API calls against Alpaca's rate limits and instant updates.
- **A user-controlled number of runs:** fewer runs return instantly while you explore, more runs give a smoother, more reliable distribution. The user decides the trade-off between speed and precision.
- **Shipped end to end:** auth, database, live data, and simulation all work together, rather than one polished feature and a set of mockups.

**Stack:** Next.js · React · TypeScript · PostgreSQL · Socket.io · Alpaca API · Recharts

<details>
<summary>Running locally</summary>

```bash
npm install
npm run dev
```

Requires Alpaca API keys and a PostgreSQL connection string in `.env`.

</details>
