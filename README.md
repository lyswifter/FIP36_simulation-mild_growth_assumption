# FIP36_simulation-mild_growth_assumption

We simulate Filecoin network dynamics post FIP36, specificly what’s the SP’s ROI looks like at any time of points in next 6 years by assuming
1. this FIP will go live in nv17 (early Nov)
2. RB power add/expire and QAP add/expire on epoch basis after this FIP, which can be modified by yourself to check how SP’s ROI will change accordingly

The ROI doesn’t include operation and hardware costs, nor gas fees because that’s variant SP by SP, it’s just fil based return, concretely, 365 days of block reward divides pledge, you need to dedicate the gas fee, collateral and fiat cost from the aggregated block reward by yourself based on your own cost structure. In short, you might see much lower ROI in your real business operation than the model tells you.

This model is written by python Jupiter notebook, if you don’t have experience but still want to try it, you can download Anaconda and use “jupyter notebook” command to start it, and you will find tons of online guides to make the learning curve not intimidate at all.

Caveat! This notebook should not be viewed as financial decisions by any means, there might be defects of simulating Filecoin consensus or false assumptions of network parameters and etc. Although it’s worth to mention that with two months of emulation from Jun 17 to Aug 22, it’s pretty close between the model output and network data (block rewards and circulation).

Again, you are free to modify any part of the model, especially the part in “## Assumptions we can modify” code block, and re-run the notebook to check how that impact SP’s ROI. By changing these assumptions and compare the results, we have observations as below:

1. SP ROI will continue to drop and will be in below 20% fil based APY range after FIP36
2. Larger total daily QAP commit to the network will make the SP ROI dip faster,
3. Larger total daily QAP commit to the network will make SP ROI dip deeper
4. There will be a turning point where SP will see ROI raise again, this point mark that baseline power overtakes QAP, which is determined by consensus pledge using max(QAP, baseline) as denominator, and again larger daily QAP, later we will see.that time point.

Since this APY is only about (block reward)/pledge, so with 20% to 30% fil-based APY SP will enter “bleeding zone”), assuming in real operation, SP still need to deduce the cost of collateral(30%ish loaning rate at this moment) cost of gas (0.6% of pledge for 50x sector to 30% of pledge for 1X sector), hardware and datacenter cost, fixed cost (team, network, etc)

Based on above 4 observations, we infer that
1. After a relatively short period of roll out shock (1 to 3 month), we will see new committed QAP quickly shrinked, as larger daily total QAP means SPs collectively push their ROI further down in quicker way, down to the road, more and more SPs will stop committing new QAP until no one can be profitable for doing so,
2. The network will be more unstable than stable (short term growth by roll out shock and long term shrink for negative incentive for SPs)
2. Therefore there will be no long term benefit in terms of locking more tokes in TVL.
3. When SPs stop committing new QAP, other tracks of Filecoin ecosystems like Fil+ might see negative impact as well.