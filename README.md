# Nordic FCR constraint calculator

A single-page tool for sizing a battery against the Nordic frequency-containment reserve products, **FCR-N** and **FCR-D**. Put in the battery's ratings and it works out how much capacity you can actually sell into each product, plus the state-of-charge band the unit has to stay within to deliver.

**Live version:** https://joshuaelliott11.github.io/nordic-fcr-calculator/

It runs entirely in the browser, so there's nothing to install and no login.

## What it shows

The table covers four cases: FCR-N, FCR-D up, FCR-D down, and FCR-D up and down together. For each one you get three things:

- **Max power:** the largest capacity you can bid once the inverter rating and the counter-reserve headroom have been taken out.
- **Usable SoC band:** the floor and ceiling the battery needs to stay between, given in both percent and MWh.
- **Binding limit:** which tells you whether the bid is capped by power (the inverter and headroom) or by energy. The energy case is what happens when a short pack runs out before it meets the endurance window.

If the energy reserve fills the pack and leaves no room to move, the calculator flags that case as **infeasible**.

## Using it

Enter the **inverter power** and **duration**, or type the **energy** directly, since the three values stay linked. If you want the SoC bands measured against real usable energy rather than nameplate, drop the **usable window** to reflect depth-of-discharge limits or degradation. Then pick the **FCR-N energy-duration requirement**, either 1.0 h for the pan-Nordic case or 1.25 h for DK2.

The results update in the table as you type. The panel underneath, "How the numbers are worked out", sets out the rules behind each figure if you want to check the working.

## A few caveats

The figures are indicative and meant for scenario framing. They don't guarantee a prequalification outcome, and real usable energy drifts with state of health over the life of the asset. The model assumes **FCR-N NEM of 34%**, **FCR-D NEM of 20%**, and **FCR-D endurance of a third of an hour** per direction.

## Editing

Everything lives in one file, `index.html`. Pages deploys from the `main` branch, so anything you push there goes live on its own.

Built at Gridcog.
