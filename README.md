# Manchester Private Rent Analysis

This is a small exploratory data analysis project about private rent changes in Manchester between January 2016 and January 2026.

I built this project to practise working with public data in Python and to turn a few raw CSV files into a clear, readable analysis. The project focuses mainly on annual percentage change in private rents, rather than monthly rent prices themselves. I also use two smaller snapshot datasets to compare rent changes by bedroom number and average rent levels across selected areas.

## Data source

The data comes from the Office for National Statistics private rents data. I used three CSV files for this project.

1. `Mcr_AnnualChangeInRents.csv` contains annual percentage change in private rents over time for Manchester, North West, England, and the United Kingdom.

2. `Mcr_ChangeInAverageRentsByBedroom Number.csv` shows annual percentage change in average rents by bedroom number for Manchester.

3. `Mcr_AverageRentMcrComparedWithNW.csv` compares average rent levels between Manchester and wider benchmark areas.

The main time-series analysis uses the first dataset. The other two datasets are used as extra context for the latest period.

## Questions I wanted to answer

The notebook is organised around four questions.

1. How did Manchester's annual rent-change rate move between 2016 and 2026?

2. How did Manchester compare with North West, England, and the United Kingdom?

3. Did recent rent changes differ by bedroom number?

4. How did Manchester's average rent level compare with wider benchmarks?

## Project structure

```text
.
├── README.md
├── requirements.txt
├── manchester_rent_analysis.ipynb
├── data/
│   ├── Mcr_AnnualChangeInRents.csv
│   ├── Mcr_ChangeInAverageRentsByBedroom Number.csv
│   └── Mcr_AverageRentMcrComparedWithNW.csv
└── figures/
    ├── annual_rent_change_over_time.png
    ├── annual_change_distribution.png
    ├── rolling_volatility_6m.png
    ├── latest_month_comparison.png
    ├── bedroom_type_comparison.png
    └── average_rent_level_comparison.png
```

## Main chart

![Annual rent change over time](figures/annual_rent_change_over_time.png)

## What the analysis does

The notebook starts by loading and inspecting the three datasets. I then clean the column names, select the areas needed for comparison, and reshape the main dataset from wide format into long format so that it is easier to analyse and visualise.

After cleaning, I check the data for missing values, duplicated area-month rows, date range, record counts by area, monthly coverage, and possible unusual values. These checks are included because I wanted the project to show not only the final charts, but also the basic validation steps behind them.

The analysis then compares Manchester with North West, England, and the United Kingdom over time. It also looks at the distribution of annual rent-change values, a simple six-month rolling volatility measure, the latest-month comparison, rent change by bedroom number, and average rent levels.

## Main findings

Manchester had the highest mean annual rent-change rate across the full period in this dataset. It also showed greater volatility than the wider benchmark areas, meaning the annual rent-change rate moved more sharply from month to month.

The strongest Manchester value in the period was 12.8% in July 2024. By January 2026, Manchester's annual rent-change rate was lower than the North West figure, which suggests that the latest month did not simply follow the full-period average pattern.

In the bedroom comparison dataset, one-bedroom properties showed the highest recent annual percentage change. In the average rent comparison, Manchester's average rent was much higher than the North West figure, but still below the England average.

## Limitations

This is an exploratory project, so the findings are descriptive. The project does not test what caused rent changes in Manchester.

The main dataset shows annual percentage change, not the underlying monthly rent price for each area. The bedroom and average-rent datasets are January 2026 snapshots, so they add useful context but should not be treated as full time series. The project also compares only a small number of selected areas. A fuller analysis would need additional data on housing supply, wages, population change, student demand, migration, and local labour-market conditions.

## How to run it

Install the required Python libraries first.

```bash
pip install -r requirements.txt
```

Then open the notebook and run the cells from top to bottom.

```text
manchester_rent_analysis.ipynb
```

The notebook should read the CSV files from the `data/` folder and save the charts into the `figures/` folder.

## Skills practised

This project helped me practise a few core data analysis skills: reading and inspecting CSV files, cleaning column names and data types, reshaping data from wide to long format, checking basic data quality, creating exploratory charts, and writing up findings with clearer limitations.

It is a small first portfolio project rather than a full housing-market study. The aim is to show a clear and reproducible analysis workflow using public data, pandas, matplotlib, and seaborn.
