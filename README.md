# Annuity Yield Curve

![Yield Curves](/misc/yield_curves.png)

This repository hosts the annuity yield curve, i.e. the yield curve at which life insurance companies effectively borrow from their customers by selling new annuity policies. The data is available from **1989** to **2021**, usually **twice per year**, for a cross-section of about **20 individual companies** and **aggregated**.

The [individual company data](/data/implied_rates_linear_long.csv) is indexed by the `date` on which the prices were surveyed, the NAIC company number `co_num`, and the `horizon` in years of the yield. The yield `rate` is given in percent for continuous compounding. The [aggregated data](/data/implied_rates_linear_long_agg.csv) does not have the `co_num` column. If you think there is an update due, please open an issue.

# Procedure

![Flow Chart](/misc/mermaid-diagram-20210624110523.png)

The annuity prices are gathered from the [Annuity Shopper Magazine](https://www.immediateannuities.com/annuity-shopper/as-archive.html) and are supplemented by high-frequency data that is kindly provided by [BluePrint Income](https://www.blueprintincome.com/). The applicable annuitant mortality tables are taken from the [Society of Actuaries](https://mort.soa.org/).

The payoff patterns of policies that are offered by the same life insurer identify different parts of the insurer-specific yield curve. This is similar to how U.S. Treasury bonds with different maturities imply the [Treasury yield curve](https://www.treasury.gov/resource-center/data-chart-center/interest-rates/Pages/TextView.aspx?data=yield) and highly-rated corporate bonds imply the [HQM yield curve](https://www.treasury.gov/resource-center/economic-policy/corp-bond-yield/pages/corp-yield-bond-curve-papers.aspx).
