# Relationship-between-the-Economic-trend-and-The-result-of-US-Election-2024
# Economic Trends & US Election 2024 Analysis

[![Python](https://img.shields.io/badge/Python-3.x-blue)](https://www.python.org/)
[![Data Analysis](https://img.shields.io/badge/Analysis-Economics-green)](https://pandas.pydata.org/)
[![Statistics](https://img.shields.io/badge/Statistics-Regression-orange)](https://scikit-learn.org/)
[![Ca' Foscari](https://img.shields.io/badge/Institution-Ca'%20Foscari-red)](https://www.unive.it/)

## Overview

This project investigates the relationship between economic indicators and voting patterns in the **2024 US Presidential Election**. Using data from **50 US states plus DC**, we analyze how macroeconomic trends from 2020-2023 influenced voter decisions across states.

**Core Question**: *Is there a relationship between economic trends and the result of the US Election 2024?*

## Team

| Name | ID | Role |
|------|----|----|
| **Van Duc Dao** | 908607 | Data Processing & Analysis |
| **Trang Linh To** | 908463 | Data Management & Visualization |
| **Edoardo Bernaus** | 889072 | Regression Analysis & Insights |

**Institution**: Ca' Foscari University of Venice  
**Course**: Computer Programming and Data Management  
**Date**: 2025

## Problem Statement

### Research Question
Does economic performance influence voting behavior in US elections? Specifically:
- Do states with higher economic growth support certain parties?
- Do states with higher per capita income lean toward specific candidates?
- Does population growth correlate with election outcomes?
- Do job creation rates affect electoral results?

### Significance
Understanding economic-electoral relationships is crucial for:
- **Political analysts** predicting election outcomes
- **Economists** understanding voter sentiment
- **Policymakers** designing economic policies with political awareness
- **Researchers** studying political behavior

## Dataset Overview

### Scope
- **Geographic Coverage**: 50 US States + District of Columbia (51 entities)
- **Time Period**: 2020 Census data compared with 2023 economic data
- **Election Data**: 2024 US Presidential Election results
- **Data Quality**: No missing values, fully cleaned dataset

### Key Variables Analyzed

#### Economic Indicators
| Variable | Description | Source |
|----------|-------------|--------|
| **GDP** | Gross Domestic Product by state | Bureau of Economic Analysis |
| **Per Capita GDP** | GDP adjusted for population | BEA |
| **CGDP** | Chained (real) GDP (inflation-adjusted) | BEA |
| **Personal Income (PI)** | Total personal income earned | BEA |
| **Disposable Personal Income (DPI)** | Income after taxes available for spending | BEA |
| **Per Capita DPI** | DPI adjusted for population | BEA |
| **Personal Consumption Expenditures (PCE)** | Consumer spending | BEA |
| **Per Capita PCE** | PCE per person | BEA |
| **Regional Price Parities (RPP)** | Cost of living adjustments | BEA |
| **Employment** | Total jobs by state | Bureau of Labor Statistics |
| **Jobs/Population Ratio** | Employment rate metric | BLS |
| **Population** | State population | US Census Bureau |

#### Electoral Variables
| Variable | Description |
|----------|-------------|
| **Republican Votes** | Total votes for Republican candidate |
| **Democrat Votes** | Total votes for Democratic candidate |
| **Total Votes** | Sum of all votes cast |
| **Election Margin** | Difference between parties (absolute percentage) |
| **Swing Margin** | Margin of victory measure |
| **Result** | Winner in each state (REPUBLICAN or DEMOCRAT) |

### Data Processing Steps
1. ✅ **Data Cleaning**: Removed invalid votes, standardized formats
2. ✅ **Data Merging**: Combined 2020, 2023 economic data with 2024 election results
3. ✅ **Feature Engineering**: Created percentage changes (2020→2023)
4. ✅ **Geographic Alignment**: Matched state names across multiple datasets
5. ✅ **Validation**: Verified data consistency across sources

## Methodology

### Approach

#### 1. Exploratory Data Analysis (EDA)
- **Univariate Analysis**: Distribution of each economic metric by state
- **Bivariate Analysis**: Relationships between economic indicators and electoral results
- **Spatial Analysis**: Geographic mapping of economic and electoral patterns
- **Comparative Analysis**: 2020 vs 2023 economic snapshots

#### 2. Summary Statistics
Analyzed the overall index (2020 & 2023):
- State-level GDP distributions
- Personal income patterns
- Total jobs by state
- Personal consumption patterns
- Population density variations
- Regional price parity differences

Per capita analysis:
- Disposable personal income per capita
- GDP per capita
- Jobs/population ratio
- Consumer spending per capita

#### 3. Regression Analysis
Two main regression frameworks:

**Model A: Election Margin Analysis**
```
Dependent Variable: Election Margin (Republican vs Democrat)
Independent Variables:
  → Per Capita GDP, Per Capita PCE, RPP
  → Jobs/Population Ratio, Per Capita DPI
  → % Change GDP, % Change PCE, % Change DPI
  → % Change Jobs, % Change Population
```

**Model B: Swing Margin Analysis**
```
Dependent Variable: Swing Margin (party distance increase)
Independent Variables:
  → Same as Model A
  → Measures polarization and certainty of outcome
```

### Statistical Methods
- **Correlation Analysis**: Pearson correlation coefficients
- **Linear Regression**: OLS regression with scatter plots
- **Spatial Visualization**: Choropleth maps showing state-level patterns
- **Hypothesis Testing**: Significance of relationships

## Key Findings

### Major Results

#### 1. **Per Capita GDP & Election Outcome** (Correlation: -0.6512)
🔴 **Strong Negative Correlation**
- **Finding**: Higher per capita GDP strongly correlates with **Democratic voting**
- **Interpretation**: Wealthy, urbanized states (CA, MA, CT, NY) vote Democratic
- **Explanation**: Coastal, industrialized, service-based economies are Democratic-leaning
- **Rural Exception**: Wyoming, Montana, Kansas (Republican despite some economic metrics)

#### 2. **Personal Consumption Expenditures & Election Outcome** (Correlation: -0.7728)
🔴 **Strongest Negative Correlation**
- **Finding**: Higher per capita PCE strongly predicts **Democratic states**
- **Interpretation**: States with higher consumer spending lean Democratic
- **Data**: Massachusetts, Connecticut, New Jersey show high PCE and vote Democratic
- **Mechanism**: Consumer-driven economies in urban areas correlate with Democratic support

#### 3. **Jobs/Population Ratio & Election Outcome** (Correlation: -0.5223)
🟡 **Moderate Negative Correlation**
- **Finding**: Higher employment rates slightly favor Democratic candidates
- **Exception**: Republican-leaning states (Wyoming, South Dakota, Nebraska) have HIGH jobs/population
- **Takeaway**: Regional economic structures matter more than just job numbers

#### 4. **Regional Price Parities & Election Outcome** (Correlation: -0.7843)
🔴 **Very Strong Negative Correlation**
- **Finding**: Higher cost of living correlates with **Democratic voting**
- **Interpretation**: Expensive urban states vote Democratic; affordable rural states vote Republican
- **Note**: RPP is wage-adjusted, showing real purchasing power differences

#### 5. **Per Capita DPI Change & Election Outcome** (Correlation: 0.4088)
🟢 **Moderate Positive Correlation**
- **Finding**: States with **increasing disposable income favor Republicans**
- **Key States**: Texas and Florida (high DPI growth, voted Republican)
- **Interpretation**: Income growth in growing states (esp. Sun Belt) supports Republicans

#### 6. **GDP Growth (% Change) & Election Outcome** (Correlation: 0.6318)
🟢 **Strong Positive Correlation**
- **Finding**: States with **higher GDP growth voted Republican**
- **Period**: 2020-2023 GDP growth favors Republican candidates
- **Implication**: Economic momentum and growth benefit the incumbent party's opposition

#### 7. **Population Change & Election Outcome** (Correlation: 0.2315)
🟢 **Weak Positive Correlation**
- **Finding**: Growing populations slightly favor **Republican states**
- **Examples**: Texas, Florida, Arizona growing and voting Republican
- **Exception**: Louisiana (counterexample with population growth but voted Republican)

#### 8. **Employment Growth & Election Outcome** (Correlation: 0.3758)
🟢 **Moderate Positive Correlation**
- **Finding**: Job creation correlates with **Republican support**
- **Interpretation**: States adding jobs at faster rates vote Republican
- **Context**: Likely reflects Republican strongholds in growing regions (South, Southwest)

### Swing Margin Insights (Polarization)

**Weak relationships with swing margin suggest**:
- Economic factors affect WHO wins but NOT HOW MUCH they win
- States are becoming more polarized regardless of economic conditions
- Economic messaging matters, but partisan identity is stronger than economics

### Geographic Patterns

**Democratic-Leaning Regions**:
- Northeast (MA, CT, NY, VT) - High GDP, high PCE, high RPP
- West Coast (CA, WA, OR) - Tech economies, high cost of living
- Upper Midwest (IL, MN) - Industrial, urban centers
- Mid-Atlantic (MD, NJ) - Suburban, affluent

**Republican-Leaning Regions**:
- Great Plains (WY, MT, ND, SD, NE) - Agricultural, rural
- South (TX, FL, GA, NC) - Rapidly growing, lower costs, population influx
- Rust Belt (portions of PA, OH, MI) - Economic transition challenges
- Mountain West (AZ, ID, NV) - Growing populations, lower density

## Conclusions

### Main Takeaways

1. **Economic Structure Matters Most**
   - Per capita wealth and consumption patterns are the strongest predictors
   - Urbanized, service-based economies vote Democratic
   - Rural, agricultural economies vote Republican

2. **Growth Favors Republicans**
   - States with GDP growth, income growth, and job creation voted Republican
   - Likely reflects the "change" argument against incumbent administration
   - Economic momentum in Sunbelt/Southwest helps Republican candidates

3. **Cost of Living Predicicts Party**
   - High cost of living (RPP) → Democratic
   - Affordable living → Republican
   - Reflects different lifestyle preferences and economic models

4. **Employment is Nuanced**
   - Absolute job numbers don't predict outcomes well
   - Job GROWTH matters more than raw numbers
   - Regional economic structure overrides employment rates

5. **Population Growth ≠ Electoral Certainty**
   - Growing states lean slightly Republican but not strongly
   - Demographic change alone doesn't determine outcomes
   - Migration to Republican-leaning regions occurred (TX, FL, AZ)

### Limitations

⚠️ **Causation vs Correlation**
- This analysis shows correlations, not causal relationships
- Economic data doesn't directly cause voting behavior
- Cultural, political, and demographic factors also influence elections

⚠️ **Aggregation Effects**
- State-level analysis masks within-state variation
- Rural vs urban divisions within states not captured
- County-level analysis would provide more granularity

⚠️ **Time Lag**
- 2023 economic data analyzed for 2024 election
- Voters respond to recent economic conditions
- Quarterly GDP changes might predict better than annual

⚠️ **External Factors Not Captured**
- Candidate quality and charisma
- Campaign spending and messaging
- Major events (inflation, COVID recovery)
- Political scandals and controversies

## Visualizations & Results

### Maps Generated
1. **GDP by State (2020 & 2023)** - Shows concentration in large states
2. **Per Capita Income Maps** - Even distribution with Mississippi exception
3. **Employment Distribution** - Concentrated in central US
4. **Personal Consumption** - Coastal focus
5. **Regional Price Parities** - Coastal states higher
6. **% Change Maps** - Sunbelt GDP growth regions
7. **Election Results Map** - Red vs Blue state distribution

### Regression Plots
- **Scatter plots** with regression lines showing correlations
- **Correlation coefficients** labeled on each plot
- **Color coding**: Red = Republican states, Blue = Democratic states
- **Trend lines**: Show direction and strength of relationships

## Project Structure

```
Economic-Trends-Election-2024/
├── README.md                                    # This file
├── Economic_Trends_US_Election_Analysis.pdf     # Presentation slides
├── Economic_Trends_US_Election_Analysis.html    # Interactive report
├── data/
│   ├── economic_2020.csv                       # 2020 economic data
│   ├── economic_2023.csv                       # 2023 economic data
│   ├── election_2024.csv                       # 2024 election results
│   └── population_data.csv                     # Population statistics
├── code/
│   ├── data_cleaning.py                        # Data preprocessing
│   ├── eda_analysis.py                         # Exploratory analysis
│   ├── regression_analysis.py                  # Statistical models
│   └── visualization.py                        # Map generation
└── outputs/
    ├── summary_statistics.csv                  # Descriptive stats
    ├── correlation_matrix.csv                  # Correlation table
    └── regression_results.txt                  # Model outputs
```

## Technologies Used

### Programming
- **Python 3.x** - Primary analysis language
- **Pandas** - Data manipulation and cleaning
- **NumPy** - Numerical computations
- **Scikit-learn** - Regression analysis
- **Matplotlib/Seaborn** - Statistical visualizations

### Geospatial
- **Geopandas** - Geographic data handling
- **Folium** - Interactive maps
- **Plotly** - choropleth mapping

### Data Sources
- **Bureau of Economic Analysis (BEA)** - GDP, income, consumption
- **Bureau of Labor Statistics (BLS)** - Employment data
- **US Census Bureau** - Population and demographic data
- **Election official results** - State government sources

## How to Use This Project

### For Researchers
1. Clone the repository
2. Review the PDF presentation for overview
3. Study regression analysis for specific correlations
4. Check the data cleaning scripts for methodology
5. Adapt code for your own election analysis

### For Data Science Students
1. See data cleaning pipeline example (handling multiple data sources)
2. Learn EDA best practices (mapping and summary statistics)
3. Understand regression analysis workflow
4. Review geographic data visualization techniques

### For Political Analysts
1. Use correlation findings to predict future elections
2. Note regional patterns and exceptions
3. Consider which economic metrics are most predictive
4. Combine with polling data for better predictions

### For Policy Makers
1. Understand economic-electoral relationships
2. Recognize that growth matters more than absolute levels
3. Note regional differences in economic drivers
4. Consider economic policies' electoral implications

## Key Insights for Practitioners

### If you're a Political Campaign Manager
✅ Focus messaging on **economic growth narratives** in close races
✅ Emphasize **job creation** in states with high employment ratios
✅ Highlight **income growth** in Sunbelt/Southwest regions
✅ Address **cost of living** in urban, high-RPP states

### If you're an Economist
✅ Per capita metrics predict better than absolute numbers
✅ Regional economic structure matters more than simple growth
✅ States with different economic models behave differently
✅ Cost of living is key dividing line between party bases

### If you're a Data Analyst
✅ State-level aggregation misses important variation
✅ Temporal lag between economic data and elections matters
✅ Multiple variables are highly correlated (multicollinearity)
✅ Geographic visualization reveals patterns numbers don't

## Future Work & Extensions

- [ ] **County-level analysis** for finer granularity
- [ ] **Quarterly data** instead of annual (more responsive)
- [ ] **Logistic regression** to predict binary outcomes
- [ ] **Time series analysis** of economic trends
- [ ] **Voter demographic** analysis (income by district)
- [ ] **Swing state** focused deep-dive
- [ ] **Historical comparison** to 2016, 2012, 2008 elections
- [ ] **External variables**: Inflation, unemployment rate, interest rates
- [ ] **Social media sentiment** analysis by state
- [ ] **Validation** on previous elections (backtesting)

## References & Data Sources

### Economic Data
- BEA Regional Economic Accounts: https://www.bea.gov/
- BLS Labor Statistics: https://www.bls.gov/
- Census Bureau Data: https://census.gov/

### Electoral Data
- State election offices official results
- House Clerk election archives
- FEC campaign finance data

### Methodology
- Gujarati, D. N. (2003). Basic Econometrics, 4th Edition
- Tufte, E. R. (1983). The Visual Display of Quantitative Information
- King, G. (1990). Representation Through Data

## Contact & Attribution



**Institutional Support**
- Ca' Foscari University of Venice
- Department of Economics
- Course: Computer Programming and Data Management

## License

This project is licensed under the **MIT License** - see LICENSE file for details.

Students and researchers are encouraged to use this analysis for educational purposes, with proper attribution.

## Citation

```bibtex
@misc{dao2024election,
  author = {Dao, Van Duc and To, Trang Linh and Bernaus, Edoardo},
  title = {Economic Trends and US Election 2024: Regression Analysis},
  year = {2025},
  school = {Ca' Foscari University of Venice},
  course = {Computer Programming and Data Management}
}
```

---

**Last Updated**: January 2025  
**Version**: 1.0  
**Status**: Complete ✅  
**Data Freshness**: Latest available as of December 2024
