@parameters shows the results of our estimation exercise, and the fit of the three estimated models is plotted below, in @medwealth and @medshare.

```{include} parameters.tex
```

The only mechanism available to the Life Cycle Portfolio (LCP) model to match everything -- the life cycle profile of wealth and the portfolio share path after retirement -- is its choice of the consumer's relative risk aversion coefficient, $\CRRA$. Greater risk aversion has two effects: It means that the consumer has a stronger precautionary motive for saving, and that the consumer will be less willing to hold risky assets.

Economists generally think (based on other kinds of evidence) that the range of plausible values of risk aversion is in the range of 2 to 5. 

But when $\CRRA$ is in this range, the model fails badly: It massively underpredicts life cycle saving (wealth-to-income ratios are much smaller than in the data), and massively overpredicts the proportion of their assets that consumers will want to invest in risky assets (even with $\rho=5$). 

The best the model can do is to pick $\CRRA$ of about 8, which lines up nicely with the large literature finding that portfolio choice models require a very high $\CRRA$ in order to prevent agents from putting all their assets in the risky form.

The "criterion" column of @parameters is a measure of the size of the errors each model makes (the lower the criterion, the closer the model is to the targeted data).

<!-- Tried to turn this into a footnote but that caused compile errors - maybe footnotes are not allowed in included files?
[^criterion]

[^criterion]: The criterion is the minimum value that the objective function achieves for each model-- the smallest weighted squared distance between simulated moments and empirical moments.
-->

The LCP model performs poorly by this measure, as illustrated in the figures.
The $\rho$ that balances all of the objectives as well as possible is one that induces considerably more saving during the working life than we see -- this is the consequence of the intense precautionary motive against income risk. But, after retirement, the model exhibits the behavior that led us to define the \emph{drawdown failure} above: The data does not show consumers drawing down their wealth rapidly after retirement.

```{figure} figures/median_wealth
:label: medwealth
:align: center 

Median Wealth to Income Ratio for different portfolio models. The red line indicates median wealth-to-income ratios for College educated households in the Survey of Consumer Finances. Wealth is `networth` and income consists of wages, social security, and retirement income. 
```

```{figure} figures/median_share
:label: medshare
:align: center 

Median Portfolio Share for different portfolio models. The red line shows the target moments from @Aboagye2024. 
```

As discussed above, there are many options for modifying the model, some of which can ameliorate or eliminate the wealth drawdown problem. The most commonly considered modification is to add a bequest motive, which we do in a conventional way in the Warm-Glow Portfolio model (orange lines on figures), which estimates a much more realistic CRRA coefficient of $\CRRA = 4.65$.
The other two parameters the model estimates essentially amount to the answers to two questions: "How rich do you have to be before you start caring about leaving a bequest" and "for consumers who want to leave a bequest, how would they divide an extra dollar of wealth between more consumption for themselves versus a larger bequest." 

The model fits the data best when these variables both take on implausible values. The first, captured by the "bequest shifter" column of @parameters, measures the amount of wealth you need before the bequest motive "kicks in." The value in the table implies that almost everybody is motivated by bequest saving. The second parameter, labeled "bequest factor" in @parameters, implies that when the bequest motive kicks in, it is so intense that when the consumer gets a positive income surprise (say, a small lottery winning), their response is not to plan to spend most if it in their lifetime, but rather to devote almost all of it to accumulating a bigger bequest. This is strongly in conflict with a large literature that finds that the response of consumption to surprise income shocks (the Marginal Propensity to Consume) is quite large.

But, with the extremely strong bequest motive, the Warm-Glow model is able to match the high levels of wealth observed deep into retirement.
That is, these consumers do not quickly draw down their assets because they take great pleasure in passing their estate on to their heirs.
<!-- The bequest motive magnitude $\alpha$ and shifter term $\underline{a}$ are somewhat complicated to interpret, but the upshot is that the bequest motive applies for essentially *everyone*.-->
In contrast, the literature has generally found (e.g. @deNardiBequest) that the bequest motive comes into play only for relatively wealthy households, and is mostly inoperative around median wealth.[^median]
[^median]: This discrepancy might arise because of the simplified approach we have used here, matching *only* the median wealth-to-income ratio by age, rather than wealth levels conditional on income.

Digging deeper, the Warm-Glow model predicts that saving behavior *when young* is strongly motivated by the bequest motive.
Recall from the discussion of the [Survey of Consumer Finances](https://doi.org/10.17016/8799) and @jaherGilded that very few older people ascribe their wealth-holding behavior to a bequest motive, and yet the Warm-Glow model has the saving choices of *40 year olds* driven \emph{mainly} by the urge to bequeath.
Even if a model can *mechanically* reproduce observed data features or hit empirical targets, that does not make it "right" or "true," especially if its underlying logic is implausible and contradictory to other kinds of evidence.
And as discussed above, the bequest motive is inconsistent with an investment advisor's fiduciary duty *to the client* (rather than to the client's heirs).
We include the Warm-Glow model in our presentation not to advocate for it, but merely to demonstrate that there are *multiple ways* for life-cycle models to generate more realistic wealth trajectories in retirement.

Our final specification also has the agents value wealth itself as a motivation to retain assets later in life, but in a way that is more consistent with consumers' self-reported motives for saving..
The Wealth-in-Utility-Function (WIUF) / TRP Portfolio model estimates a CRRA $\CRRA$ coefficient of about 4.88 and a wealth share of utility $\delta$ coefficient of 0.16.
This result is significant because the CRRA $\CRRA$ coefficient required to match the wealth accumulation patterns is much lower than that of the standard Life-Cycle Portfolio choice model.[^caveat]
As seen in @medwealth, the WIUF / TRP model (green line) does not need to overshoot wealth accumulation in early life by nearly as much as the basic LCP model, as agents want to retain assets in retirement to generate utility directly.
Compared to the Warm-Glow model, the TRP specification does predict more wealth accumulation early in life, but for more immediate reasons: young consumers value money and liquidity *now*, rather than planning at age 35 to leave a large bequest at age 80.

[^caveat]: The two measures of risk aversion are not strictly comparable in the model with TRP utility, risk aversion applies to an aggregate of consumption and assets. Consumers are averse either to fluctuations in consumption OR fluctuations in wealth.

Moreover, because the CRRA parameter doesn't need to be so high, the WIUF model can more accurately match the target risky assets share moments (red dashed line in @medshare), which come from @Aboagye2024. <!-- we need to say more about portfolio share figure earlier -->
That paper presents the typical glide-path of target-date funds (TDFs) which provide a basis for much of commercial financial advice.
While the whole life-cycle glidepath is provided in @Aboagye2024, here we only target (and plot) those moments starting at age 70.
The model fit with respect to risky asset share is comparable for the Warm-Glow model, generally matching the level and recommended shallow downward slope.
The basic LCP model, however, badly fits the risky asset share too low due to the high $\CRRA$ value needed in its attempt to match the life-cycle wealth pattern.
