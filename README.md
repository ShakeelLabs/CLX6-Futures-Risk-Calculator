# CLX6 Futures Risk Calculator

Blue/yellow, mobile-friendly position sizing and stop-loss risk calculator built for the **The5ers 50K Swing 50E Futures Evaluation** account on **Black Arrow One**.

## Instrument setup
- Black Arrow One symbol: `CLX6`
- TradingView reference chart: `CL1!`, 1-hour timeframe
- Tick size supplied by user: **$0.01**
- Mini tick value supplied by user: **$10 per tick**
- Micro tick value in this calculator: **$1 per tick as an unverified assumption** based on a 10 Micro : 1 Mini relationship. Verify on Black Arrow One before any live trade.
- Overnight size cap used by calculator: **1 Mini or 10 Micro**

## Features
- Enter daily dollar risk, entry price, stop-loss price, and Mini/Micro contract type.
- Calculates tick distance, estimated risk per contract, max whole contracts, and estimated total risk.
- Rounds fractional tick distances upward to avoid understating risk.
- Shows a red warning if risk-based quantity exceeds the selected overnight cap.
- Responsive layout; no external libraries or remote services required.

## Deploy with GitHub Pages
1. Keep `index.html` and `README.md` in the repository root on the `main` branch.
2. In repository settings, open **Pages**.
3. Select **Deploy from a branch**, branch `main`, folder `/(root)`, then save.
4. After deployment completes, the expected site address is:
   https://ShakeelLabs.github.io/CLX6-Futures-Risk-Calculator/

## Risk calculation
- Ticks to SL = ceil(abs(Entry − Stop Loss) / 0.01)
- Risk per contract = ticks to SL × tick value
- Risk-based quantity = floor(daily risk budget / risk per contract)
- Overnight eligible quantity = min(risk-based quantity, the overnight cap)

## Important limitations
- Confirm the CLX6 Mini/Micro contract mapping and tick values in Black Arrow One. The Micro tick value is currently a clearly marked assumption.
- Commissions, fees, slippage and execution differences are excluded; real losses can be higher.
- The calculator is a risk arithmetic tool, not a trading signal or guarantee.
- It does not import XAUUSD / spot-gold contract properties.
