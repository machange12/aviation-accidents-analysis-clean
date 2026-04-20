# aviation-accidents-analysis
Analysis of aviation accident data to identify safest aircraft makes and models
# Aviation Accidents Analysis

## Project Overview
This project analyzes aviation accident data from 1983-2023 to identify 
the safest aircraft makes and models for an airline insurance client. 
The analysis focuses on two key safety metrics: the rate of fatal/serious 
passenger injuries and the rate of aircraft destruction in the event of an accident.

## Business Problem
An airline/airplane insurer wants to know:
- Which aircraft makes and models have the lowest rates of passenger injury
- Which aircraft are least likely to be destroyed in an accident
- What conditions/factors contribute to accident severity
- Separate recommendations for small aircraft (≤20 passengers) and 
  large aircraft (>20 passengers)

## Data
- Source: NTSB Aviation Accident Database (1948-2023)
- Filtered to: 1983 onwards (40-year max aircraft lifetime)
- Records after cleaning: ~17,000 accidents
- Key columns used: make, model, total passengers, injury counts, 
  aircraft damage, weather condition, number of engines

## Repository Structure
├── AviationData.csv                        # Raw data
├── AviationData_Cleaned.csv                # Cleaned data
├── Aviation_Accidents_Cleaning.ipynb       # Data cleaning notebook
├── Aviation_Accidents_Data_Analysis.ipynb  # Analysis notebook
└── README.md
## Key Findings
## Key Findings

### Large Aircraft Recommendations
- **Boeing 777** (injury fraction: 0.0006) and **Boeing 787** (0.003) 
  are the safest large aircraft models
- **Bombardier CL-600-2B19** (0.004) and **Embraer EMB145** (0.009) 
  also perform exceptionally well
- **Beechcraft 1900** is the worst performer with a 43% injury fraction
- At the make level, **Dehavilland** and **Grumman** show near-zero 
  injury fractions for large aircraft

### Small Aircraft Recommendations
- **Maule M-5-210C** and **Diamond Aircraft DA 20 C1** are the safest 
  small models with a mean injury fraction of 0.0
- **Stinson 108-1** also performs well at 8.3% injury fraction
- At the make level, **Bombardier** and **Maule** are the top 
  small aircraft manufacturers

### Contributing Factors
1. **Weather Condition** — IMC (poor weather) results in an injury 
   fraction of 0.63 vs VMC at 0.24 — nearly 3x higher. Destruction 
   rate under IMC is 0.35 vs 0.07 under VMC — 5x higher
2. **Number of Engines** — Single engine aircraft have significantly 
   higher injury and destruction rates due to lack of engine redundancy. 
   Multi-engine aircraft benefit from both redundancy and stricter 
   airworthiness regulations

## How to Run
1. Clone this repository
2. Install dependencies: `pip install pandas numpy matplotlib seaborn`
3. Run `Aviation_Accidents_Cleaning.ipynb` first to generate cleaned data
4. Run `Aviation_Accidents_Data_Analysis.ipynb` for the full analysis

## Limitations
- High accident count does not imply an unsafe aircraft — popular models 
  like the Cessna 172 (769 accidents) appear more often simply because 
  they are widely used
- Missing values in injury and weather columns may affect some analyses
- Small sample sizes for some makes/models may affect reliability of 
  mean injury fractions despite the 50 accident threshold
