# Student Alcohol Consumption and Psychological Wellness

An exploratory analysis of the relationship between self-reported alcohol
consumption and self-reported psychological wellness among university students,
built with pandas, matplotlib, and seaborn.

> **Status:** Complete

---

## Question

Is self-reported alcohol consumption associated with self-reported
psychological wellness among university students? Does the number of students
who drink vary by year of study?

## Dataset

- **Source:** [Student Smoking, Alcohol, and Psychological Wellness Data](https://data.mendeley.com/datasets/7y66xb3gmc/2) (Mendeley Data)
- **Size:** 1,164 rows, 14 columns (`Dataset_version-2.csv`)
- **Published:** 16 December 2024 (collection date not stated by the authors)
- **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

> **Attribution:** "Student Smoking, Alcohol, and Psychological Wellness Data"
> by Wahid Tausif Islam, licensed under
> [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
> DOI: [10.17632/7y66xb3gmc.2](https://doi.org/10.17632/7y66xb3gmc.2).
> The source data was used unmodified; derived summary variables were computed
> for this analysis.

Note: the source page describes 1,163 responses, while version 2 of the CSV
contains 1,164 rows. This analysis uses the file as distributed.

Key variables used:

| Variable | Description |
|---|---|
| `Frequency of alcohol consumption` | Categorical data used to split respondents into drinkers and non-drinkers |
| `Psychological Wellness` | Self-reported, five levels: Poor, Below average, Average, Good, Excellent |
| `Year of study` | 1st through 4th year, plus graduate student |

## Findings

- Respondents split into 1,057 who reported consuming alcohol and 107 who
  reported that they do not
- Among drinkers, 94.2% reported below-average or poor psychological wellness,
  compared with 14.0% of non-drinkers
- The pattern inverts at the other end: 3.1% of drinkers reported good or
  excellent wellness, against 74.8% of non-drinkers
- The gap is far larger than typical survey associations of this kind, which
  is itself a reason for caution rather than confidence (see Limitations)

![Number of alcohol drinkers by year of study](figures/drinkers_by_year.png)

Drinker count peaked at 4th year, with a high of approximately 300 respondents

## Method

1. Loaded version 2 of the raw survey data and inspected column types and values
2. Split respondents into two groups on `Frequency of alcohol consumption`:
   those who drink and those who selected "Don't consume alcohol"
3. Within each group, classified `Psychological Wellness` into three bands:
   Below average/Poor, Average, and Good/Excellent
4. Computed the prevalence of each wellness band within each group as a share
   of that group's total
5. Assembled a comparison table from the derived prevalence rates
6. Counted drinkers by year of study and plotted the result with seaborn,
   ordering the categories from 1st year through graduate student

No rows were dropped and no source values were altered.

## Repository structure

```
.
├── data/
│   └── raw/              # source data, CC BY 4.0 (see Attribution)
├── figures/              # exported charts
├── notebooks/
│   └── analysis.ipynb    # main analysis
├── requirements.txt
├── LICENSE
└── README.md
```

## Setup

```bash
git clone https://github.com/jzh3/student-alcohol-analysis.git
cd student-alcohol-analysis
pip install -r requirements.txt
```

The dataset is included in `data/raw/` under CC BY 4.0. Open the notebook and
run all cells.

## Limitations

- All measures are self-reported and subject to recall and social desirability
  bias, which typically leads to underreporting of alcohol consumption
- The survey is cross-sectional, so the association reported here is
  correlational only; nothing in this analysis establishes that drinking
  affects wellness, or that wellness affects drinking
- The size of the difference between groups is unusually large for survey data.
  The source may be partly synthetic, and the wellness measure is a single
  self-rated item rather than a validated measurement. Treat the magnitude as
  a property of this dataset rather than an estimate of a real-world effect
- The two groups are very unequal, with roughly ten drinkers for every
  non-drinker, so the non-drinker percentages rest on 107 responses
- No rows were excluded, so missing or inconsistent responses remain in the
  data as collected
- Respondent recruitment is not described by the source, so the sample cannot
  be assumed to represent university students generally

## License

Code in this repository is released under the MIT License (see `LICENSE`).
The dataset in `data/raw/` is licensed separately under CC BY 4.0 and remains
subject to that license and its attribution requirement.

---

Built by Xiwen Zhang · [LinkedIn](https://linkedin.com/in/xiwen-zhang30)

