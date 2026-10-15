# Titanic Survival Analysis: Exploratory Data Analysis

An exploratory data analysis (EDA) of the Titanic passenger dataset, investigating which passenger characteristics were associated with survival.

## Research Question

**What types of passengers were more likely to survive the Titanic disaster?**

## Key Findings

Of the 891 passengers in the dataset, 342 (**38.4%**) survived.

| Factor | Finding |
| --- | --- |
| Sex | Women survived at **74.2%** vs **18.9%** for men |
| Passenger class | **63.0%** (1st), **47.3%** (2nd), **24.2%** (3rd) |
| Age | Children (0–12) had the highest survival rate at **58.0%**; passengers over 60 the lowest at **22.7%** |
| Sex + class | Women survived more often than men in every class; 3rd-class women (50.0%) outlived 1st-class men (36.9%) |

**In short:** women, children and first-class passengers were the most likely to survive; men, third-class passengers and older adults were the least likely.

> These are descriptive associations. They do not prove that any single factor caused survival.

## Project Structure

```
titanic-survival-eda/
├── data/
│   └── train.csv              # Titanic passenger data (891 rows, 12 columns)
├── notebooks/
│   └── titanic_eda.ipynb      # Full analysis with charts and conclusions
└── README.md
```

## Dataset

`data/train.csv` contains 891 passenger records with these columns:

| Column | Description |
| --- | --- |
| `PassengerId` | Unique passenger ID |
| `Survived` | 0 = did not survive, 1 = survived |
| `Pclass` | Passenger class (1 = upper, 2 = middle, 3 = lower) |
| `Name` | Passenger name |
| `Sex` | Male or female |
| `Age` | Age in years |
| `SibSp` | Number of siblings/spouses aboard |
| `Parch` | Number of parents/children aboard |
| `Ticket` | Ticket number |
| `Fare` | Ticket fare |
| `Cabin` | Cabin number |
| `Embarked` | Port of embarkation (C, Q or S) |

**Data quality:** `Cabin` is missing for 77.1% of passengers, `Age` for 19.9% and `Embarked` for 0.2%. There are no duplicate rows.

## Methodology

1. Inspect data structure, types, duplicates and missing values.
2. Calculate the overall survival rate as a baseline.
3. Compare survival rates by sex, passenger class and age group.
4. Examine sex and passenger class together.
5. Summarize findings, limitations and next steps.

Survival rates are calculated *within* each group, so differences in group size don't distort comparisons.

## Tools

- Python
- Pandas
- Matplotlib
- Seaborn
- JupyterLab

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/B0kkl/titanic-survival-eda.git
cd titanic-survival-eda

# 2. Install dependencies
pip install pandas matplotlib seaborn jupyterlab

# 3. Launch Jupyter and open the notebook
jupyter lab notebooks/titanic_eda.ipynb
```

The notebook loads the data with a relative path (`../data/train.csv`), so run it from inside the `notebooks/` folder or open it through JupyterLab as shown above.

## Limitations

- Findings are descriptive; sex, class and age are correlated with each other and with unmeasured factors.
- Age analysis excludes the 177 passengers with missing ages.
- The 60+ age group has only 22 passengers, so its rate is uncertain.
- Age groups are arbitrary bins chosen for readability.

## Next Steps

- Analyze fare, family size, embarkation port and titles extracted from names.
- Impute missing ages and re-check the age findings.
- Run statistical significance tests (e.g. chi-square).
- Build a baseline predictive model such as logistic regression.

## Data Source

The dataset is the Titanic training set, originally distributed through [Kaggle's Titanic competition](https://www.kaggle.com/c/titanic).
