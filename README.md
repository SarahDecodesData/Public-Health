# Measles Vaccination Coverage Among Children Aged 12–23 Months in Nigeria

## Table of Contents

- [Project Overview](#project-overview)
- [Purpose & Scope](#purpose-&-scope)
- [Research Question](#research-question)
- [Data](#data)
- [Analytical Population](#analytical-population)
- [Methodology](#methodology)
- [Variables](#variables)
- [Key Findings](#key-findings)
  - [Overall Vaccination Coverage](#overall-vaccination-coverage)
  - [Household Wealth](#household-wealth)
  - [Maternal Education](#maternal-education)
  - [Geopolitical Zone](#geopolitical-zone)
  - [Child Sex](#child-sex)
  - [Child Age](#child-age)
- [Sample Sizes](#sample-sizes)
- [Visualizations](#visualizations)
- [Limitations](#limitations)
- [Tools Used](#tools-used)
- [AI Assistance](#AI-assistance)
- [Conclusion](#conclusion)

---

## Project Overview

This project examines patterns of measles vaccination coverage among children aged 12–23 months in Nigeria using data from the Nigeria Multiple Indicator Cluster Survey (NICS).

The analysis focuses on whether measles vaccination coverage differs across selected demographic and socioeconomic characteristics, including household wealth, maternal education, geopolitical zone, child sex, and child age.

The project uses descriptive analysis and survey weights to estimate vaccination coverage within the analytical sample.

---

## Purpose & Scope

This project was conducted for **learning and portfolio-development purposes only**. It is an independent data-analysis exercise designed to develop practical skills in public health research, epidemiological analysis, Python, and working with survey microdata.

The analysis is not intended to provide clinical, medical, or public health recommendations, and the findings should not be interpreted as official estimates beyond the scope and limitations of the underlying survey data.

---

## Research Question

> **What are the patterns of measles vaccination coverage among children aged 12–23 months in the NICS sample?**

---

## Data

The analysis uses the [**NICS Child (CH) dataset**](https://microdata.nigerianstat.gov.ng/index.php/cat) from the Nigeria Multiple Indicator Cluster Survey.

The dataset was provided in SPSS `.sav` format and was imported into Python for analysis.

The original child dataset contained **29,335 observations**. After restricting the analysis to children aged 12–23 months and valid measles vaccination responses, the final analytical sample contained **2,058 children**.

### Data access

The original NICS Child dataset is not included in this repository because the dataset's terms of use restrict redistribution of the microdata.

The dataset can be obtained from [**the official source**](https://microdata.nigerianstat.gov.ng/index.php/cat).

The analysis notebooks document the data preparation and analysis steps performed using the locally stored dataset.

### Outcome Variable

The primary outcome is:

**IM16 — Ever received measles vaccination**

| Code | Meaning |
|------|---------|
| 1 | Yes |
| 2 | No |
| 8 | Don't know |
| 9 | Missing |

For the analysis, only responses coded **1 (Yes)** and **2 (No)** were included in the vaccination denominator.

Unknown, missing, and unavailable responses were not recoded as unvaccinated.

---

## Analytical Population

The analysis was restricted to children:

- Aged **12–23 months**
- With a valid response for measles vaccination (`IM16 = 1 or 2`)

### Final Sample

| Measure | Value |
|---|---:|
| Total analytical sample | 2,058 |
| Vaccinated | 1,380 |
| Not vaccinated | 678 |
| Age range | 12–23 months |
| Mean age | 17.43 months |
| Median age | 17 months |

---

## Methodology

The analysis was conducted using Python in Jupyter Notebook.

### Data Preparation

The following steps were performed:

1. Imported the NICS Child `.sav` dataset into Python.
2. Selected variables relevant to the research question.
3. Examined variable codes and missing values.
4. Restricted the dataset to children aged 12–23 months.
5. Excluded children with unknown or missing measles vaccination responses from the vaccination denominator.
6. Applied the child sample weight (`chweight`) when calculating vaccination coverage.

### Weighted Vaccination Rate

Vaccination coverage was calculated using the child sample weight.

The weighted vaccination rate was calculated as:

**Weighted vaccination rate = weighted number vaccinated / weighted number with valid vaccination status × 100**

This approach accounts for differences in the survey sampling weights across observations.

The analysis is descriptive and does not attempt to establish causal relationships between the characteristics examined and vaccination status.

---

## Variables

| Variable | Description | Categories / Measurement |
|---|---|---|
| `IM16` | Ever received measles vaccination | Yes / No |
| `windex5` | Household wealth quintile | Poorest, Second, Middle, Fourth, Richest |
| `melevel` | Mother's education level | None, Primary, Secondary, Higher, Non-formal |
| `Zone` | Geopolitical zone | North Central, North East, North West, South East, South South, South West |
| `HL4` | Child sex | Male, Female |
| `CAGE` | Child age | Age in months |
| `chweight` | Child sample weight | Survey weight |

---

# Key Findings

## Overall Vaccination Coverage

The weighted measles vaccination coverage among children aged 12–23 months was:

### **69.32%**

The corresponding unweighted vaccination rate was approximately **67.05%**.

---

## Household Wealth

Vaccination coverage varied substantially across household wealth groups.

| Wealth Group | Weighted Vaccination Rate |
|---|---:|
| Poorest | 41.04% |
| Second | 55.49% |
| Middle | 71.08% |
| Fourth | 81.36% |
| Richest | 80.90% |

Vaccination coverage increased substantially from the poorest to higher wealth groups.

The difference between the poorest and richest groups was approximately **39.86%**.

Coverage was slightly higher in the fourth wealth quintile than in the richest quintile, indicating that the relationship was not perfectly monotonic.

---

## Maternal Education

Vaccination coverage generally increased with the level of formal maternal education.

| Maternal Education | Weighted Vaccination Rate |
|---|---:|
| None | 48.10% |
| Primary | 70.53% |
| Secondary | 78.01% |
| Higher | 92.62% |
| Non-formal | 47.52% |

Children whose mothers had higher education had the highest observed vaccination coverage at **92.62%**.

The non-formal education group had coverage similar to the group with no formal education.

---

## Geopolitical Zone

There were substantial differences in vaccination coverage across geopolitical zones.

| Geopolitical Zone | Weighted Vaccination Rate |
|---|---:|
| North Central | 77.85% |
| North East | 58.98% |
| North West | 49.24% |
| South East | 82.34% |
| South South | 85.84% |
| South West | 72.51% |

The highest observed coverage was in the **South South (85.84%)**, while the lowest was in the **North West (49.24%)**.

The difference between these two groups was approximately **36.60 percentage points**.

---

## Child Sex

Vaccination coverage was relatively similar between male and female children.

| Child Sex | Weighted Vaccination Rate |
|---|---:|
| Male | 70.91% |
| Female | 67.62% |

The difference was approximately **3.29 percentage points**, which was smaller than the differences observed across wealth, maternal education, and geopolitical zone.

---

## Child Age

Vaccination coverage fluctuated across ages 12–23 months.

| Age (Months) | Weighted Vaccination Rate |
|---:|---:|
| 12 | 64.67% |
| 13 | 61.82% |
| 14 | 69.68% |
| 15 | 63.96% |
| 16 | 72.59% |
| 17 | 61.50% |
| 18 | 71.80% |
| 19 | 68.78% |
| 20 | 62.66% |
| 21 | 83.77% |
| 22 | 71.37% |
| 23 | 78.28% |

The results do not show a smooth or consistently increasing pattern across age.

The observed rates ranged from approximately **61.50% to 83.77%**.

Because some age-specific groups may contain relatively few observations, these differences should be interpreted descriptively rather than as evidence of a strong age-related effect.

---

# Sample Sizes

Sample sizes for the main categorical variables were examined to provide context for the vaccination estimates.

### Household Wealth

| Wealth Group | n |
|---|---:|
| Poorest | 382 |
| Second | 417 |
| Middle | 398 |
| Fourth | 429 |
| Richest | 432 |

### Maternal Education

| Education Level | n |
|---|---:|
| None | 461 |
| Primary | 346 |
| Secondary | 755 |
| Higher | 224 |
| Non-formal | 272 |

### Geopolitical Zone

| Zone | n |
|---|---:|
| North Central | 465 |
| North East | 276 |
| North West | 512 |
| South East | 268 |
| South South | 277 |
| South West | 260 |

### Child Sex

| Sex | n |
|---|---:|
| Male | 1,046 |
| Female | 1,012 |

The sex groups were relatively balanced. Sample sizes also varied across education and geopolitical zones, but none of the main categories had an extremely small sample.

---

# Visualizations

Three main visualizations were created to communicate the key patterns in vaccination coverage:

1. **Measles vaccination rate by household wealth**

<img width="2400" height="1500" alt="wealth_vaccination" src="https://github.com/user-attachments/assets/25bb07fa-a2e6-4e11-b9ff-95fdde2aef80" />

2. **Measles vaccination rate by maternal education**

<img width="2400" height="1500" alt="education_vaccination" src="https://github.com/user-attachments/assets/12184c9f-fd2a-48bb-9a03-9f5ea44877dc" />

3. **Measles vaccination rate by geopolitical zone**

<img width="2700" height="1500" alt="zone_vaccination" src="https://github.com/user-attachments/assets/1bb68d4c-1616-459b-9fd9-924ed9c260a6" />


These visualizations highlight the larger differences observed across socioeconomic and geographic characteristics.

The visualizations were created using **Matplotlib** in Python.

---

# Limitations

Several limitations should be considered when interpreting the results.

### 1. Descriptive analysis

This project uses descriptive analysis. The observed differences between groups should not be interpreted as causal relationships.

For example, the higher vaccination coverage observed among children of more highly educated mothers does not by itself demonstrate that maternal education causes higher vaccination coverage.

### 2. Missing and unknown vaccination responses

Only valid `IM16` responses of Yes or No were included in the vaccination denominator.

Responses coded as unknown, missing, or unavailable were excluded rather than treated as unvaccinated.

This means the results describe vaccination coverage among children with valid measles vaccination information.

### 3. Analytical sample

The final analytical sample consisted of **2,058 children**, substantially smaller than the original NICS Child dataset.

This reduction occurred because the analysis focused specifically on children aged 12–23 months with valid measles vaccination responses.

### 4. Survey weights

Survey weights were incorporated into the calculation of vaccination coverage.

However, this project does not implement a full complex-survey variance estimation procedure. Therefore, the analysis focuses on weighted descriptive estimates rather than confidence intervals or statistical significance testing.

### 5. Age-specific estimates

Vaccination rates were calculated separately for each month of age from 12 to 23 months.

Some age groups may have fewer observations than others, so fluctuations between individual months should be interpreted cautiously.

### 6. Limited set of explanatory variables

The project focuses on a small number of selected characteristics: wealth, maternal education, geopolitical zone, sex, and age.

Other factors that may be associated with measles vaccination were not examined.

---

# Tools Used

- **Python**
- **Jupyter Notebook**
- **Pandas**
- **Pyreadstat**
- **Matplotlib**
- **GitHub**

The SPSS `.sav` file was imported into Python using `pyreadstat`.

---

# AI Assistance

ChatGPT (OpenAI) was used throughout this project as a learning and development aid. It helped me understand Python and pandas concepts, interpret statistical and data-analysis methods, troubleshoot coding errors, and clarify aspects of working with survey microdata.

I independently carried out the data preparation, analysis, calculations, interpretation of results, and development of the project. I also reviewed and verified the analysis against the original NICS documentation and dataset. ChatGPT was used to support my learning and problem-solving process and was not treated as a source for the project's public health findings.

---

# Conclusion

This project examined measles vaccination coverage among children aged 12–23 months in the NICS sample using weighted descriptive analysis. The overall weighted vaccination coverage was 69.32%.

The analysis showed notable differences in vaccination coverage across household wealth, maternal education, and geopolitical zones. Coverage was substantially higher among children from higher-wealth households and among those whose mothers had higher levels of formal education. Geographic differences were also observed across Nigeria's geopolitical zones. In comparison, differences by child sex were relatively small, while vaccination rates varied across individual ages from 12 to 23 months without showing a consistent pattern.

This project was undertaken primarily as a **learning exercise in public health data analysis**. It provided practical experience working with survey microdata, preparing and filtering data, handling missing values, applying survey weights, calculating descriptive estimates, and creating visualizations using Python and Jupyter Notebook.

The findings are descriptive and should not be interpreted as evidence of causal relationships. The project demonstrates the process of using real-world public health survey data to investigate patterns in a health outcome while considering the limitations of the available data and analytical approach.

# Project Structure

A suggested project structure is:

```text
measles-vaccination-nigeria/
│
├── README.md
├── analysis/
│   └── measles_vaccination_analysis.ipynb
│
├── visualizations/
│   ├── wealth_vaccination.png
│   ├── education_vaccination.png
│   └── zone_vaccination.png
│
└── .gitignore
