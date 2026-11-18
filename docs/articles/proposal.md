# Project proposal

**To: BST260 Teaching Team, Fall 2026**

For my final project, I plan to use two datasets introduced in class to
study BMI and blood pressure, and differences in the size of reported
foodborne outbreaks. I will present these as two separate analyses.

## BMI and blood pressure

My first question is: **Among adults aged 40 and older, how is BMI
associated with systolic blood pressure?**

I will use `NHANESraw` from the [NHANES R
package](https://cran.r-project.org/web/packages/NHANES/NHANES.pdf),
which contains data from 2009–2012. Each observation represents one
participant. BMI will be a continuous exposure, and average systolic
blood pressure (`BPSysAve`, in mmHg) will be the outcome.

I will start with summary statistics and a scatterplot, then use
survey-weighted linear regression to account for the NHANES sampling
design. I plan to adjust for age, sex, race/ethnicity, education,
income-to-poverty ratio, and survey cycle. These variables capture
demographic, social, and time differences that may relate to both BMI
and blood pressure. I will report the estimated difference in blood
pressure for a 5-unit increase in BMI, with a 95% confidence interval.

I will summarize missing values and initially analyze participants with
complete information. I will also check how excluding participants with
missing income affects the results. The data are cross-sectional, so the
analysis cannot show that BMI causes changes in blood pressure.

## Foodborne outbreak setting and size

My second question is: **Among reported foodborne outbreaks, does the
number of illnesses differ between restaurant and private-home
food-preparation settings?**

I will use the [CDC outbreak data](https://www.cdc.gov/nors/data/)
provided in the package as `waterborne`. Each observation represents one
outbreak. I will select foodborne outbreaks from 2009–2023 reported in a
single US state or DC. Setting will be a categorical exposure, with
private homes as the reference; the outcome will be the reported illness
count. I will exclude other settings and records with missing, unknown,
or mixed restaurant/home settings, and document these exclusions.

I will compare the distribution of outbreak sizes using tables and
plots. I plan to use quasi-Poisson regression, adjusting for year,
season, and state to account for differences over time and across
locations. I will also examine whether adjusting for pathogen type
changes the comparison among outbreaks with that information available.

Reporting may differ by setting, and these data do not include the total
number of people exposed. Therefore, larger reported outbreaks would not
necessarily mean a higher individual risk of illness.

## Final project

I will write one vignette for each dataset, documenting its source and
cleaning steps, descriptive statistics, analysis, findings, and
limitations. I will also write reusable R functions for data preparation
and summaries, check that the package builds correctly, and publish the
vignettes on my pkgdown site, **BST260 final project**. I will confirm
any required approval for the NHANES question with the teaching team.
