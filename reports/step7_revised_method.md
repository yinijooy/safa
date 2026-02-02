# Method

## Participants

We recruited participants through the SAPA (Synthetic Aperture Personality Assessment) online platform (Condon & Revelle, 2014) between 2013 and 2017. A total of 23,679 individuals participated in the study. After quality control procedures, data from 23,647 participants were included in the final analyses. We excluded 32 participants based on the following criteria: (a) insufficient responses (fewer than 10 items answered; n = 1), and (b) straight-lining patterns (identical responses across all answered items; n = 31), which indicate low-quality or non-engaged responding.

For state-level analyses, we included 9 U.S. states with sample sizes of at least 100 participants each (California, Michigan, Illinois, Texas, Pennsylvania, Florida, New York, Washington, and Virginia), resulting in a final sample of 7,308 respondents. This minimum sample size threshold was chosen to ensure stable parameter estimates with standard errors below 0.1.

## Measures

Personality traits were assessed using 696 items from the International Personality Item Pool (IPIP; Goldberg et al., 2006). Items were rated on a 6-point Likert scale ranging from 1 (very inaccurate) to 6 (very accurate). The IPIP scales have demonstrated good psychometric properties in prior research (Goldberg et al., 2006; Johnson, 2014). Seven major personality scales were computed:

**Big Five personality traits.** We computed five broad personality domains using the IPIP-NEO scoring key: Openness to Experience (NEO_O), Conscientiousness (NEO_C), Extraversion (NEO_E), Agreeableness (NEO_A), and Neuroticism (NEO_N). Each scale was calculated as the mean of relevant items after applying reverse-scoring where indicated in the scoring key.

**Ideology.** Conservative ideology was computed as the average of standardized scores, following the approach used in prior SAPA research (Lanning et al., 2022):

    Ideology = mean(z(MPQ Traditionalism), z(NEO Liberalism) × -1)

Higher scores indicate more conservative ideological orientation.

**Honesty-Humility.** This composite scale was computed as the average of three standardized component scores, consistent with prior work on the HEXACO model (Ashton & Lee, 2007):

    Honesty-Humility = mean(z(NEO Morality), z(NEO Modesty), z(HEXACO Honesty-Humility))

## Procedure

The SAPA project employed a planned missingness design in which each participant responded to a randomly selected subset of the total item pool (Revelle et al., 2016). On average, participants completed 86 items out of 696 total items, resulting in an overall item-level missing rate of 87.6%. This design feature is intentional and allows for efficient assessment of a large item pool while minimizing participant burden.

## Data Analysis

All analyses were conducted using Python 3.11 with pandas, numpy, scipy, matplotlib, and seaborn. Analysis code is available at [repository URL upon publication]. Scale scores were computed using the scoring key matrix (superKey696.csv), with appropriate reverse-scoring applied. For composite scales (Ideology and Honesty-Humility), we used z-score transformations to ensure equal weighting of component scales.

Correlations among personality scales were computed using pairwise complete observations. Given the large sample sizes (N > 10,000), we relied on the central limit theorem for normal approximation in statistical inference. For state-level analyses, we calculated Critical Ratios (CR) using the following formula:

    CR = (State Mean - Grand Mean) / SE

where SE is the standard error of the state mean. Given the 63 comparisons (7 scales × 9 states), we used |CR| > 3.0 as a conservative threshold for statistical significance, corresponding to p < .003 under normal approximation. This threshold provides protection against Type I error inflation due to multiple comparisons.

## Limitations

Several limitations should be noted. First, the online convenience sample may not be representative of the general U.S. population, and self-selection bias may affect the generalizability of findings. Second, the planned missingness design results in varying sample sizes across scales due to differential item availability. Third, state-level analyses are limited to 9 states with sufficient sample sizes, which may not capture the full range of regional variation. Fourth, all measures are based on self-report, which may be subject to social desirability and other response biases. Finally, cross-sectional data preclude causal inferences about the relationships among personality traits and regional differences.
