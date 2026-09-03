# Nordic FCR constraint calculator

A single-page calculator for sizing a battery (BESS) against the Nordic frequency-containment reserve products — **FCR-N** and **FCR-D**. Enter the battery's ratings and it shows how much capacity you can realistically sell into each product, and the state-of-charge band the unit needs to hold to deliver.

**▶️ Open the calculator:** https://joshuaelliott11.github.io/nordic-fcr-calculator/

No install, no login — it runs entirely in the browser.

## What it tells you

For each product (FCR-N, FCR-D up, FCR-D down, and FCR-D up + down) the table gives:

- **Max power** — the largest capacity you can bid, after the inverter rating and the counter-reserve headroom are taken out.
- **Usable SoC band** — the floor and ceiling the battery must sit between to guarantee delivery, shown in both % and MWh.
- **Binding limit** — whether the bid is capped by *power* (the inverter/headroom) or by *energy* (a short pack that runs out before the endurance window is met).

Short packs get flagged when the energy reserve fills the pack and leaves no usable SoC window.

## How to use it

1. Enter **inverter power** and **duration** (or type the **energy** directly — the three stay linked).
2. Set the **usable window** to reflect depth-of-discharge limits or degradation, if you want SoC bands measured against real usable energy rather than nameplate.
3. Pick the **FCR-N energy-duration requirement**: 1.0 h pan-Nordic, or 1.25 h for DK2.
4. Read the results off the table. The "How the numbers are worked out" panel below explains the rules behind each figure.

## Caveats

Figures are indicative, for scenario framing — they don't guarantee a prequalification outcome, and real usable energy shifts with state of health over the life of the asset. Model constants: FCR-N NEM 34%, FCR-D NEM 20%, FCR-D endurance ⅓ h per direction.

## Editing

The whole thing is one file, [`index.html`](index.html). GitHub Pages deploys from `main` / root, so any change pushed to `main` republishes automatically.

---

*Built at Gridcog.*
