Table of Contents

- [About the Project](#-about-the-project)
- [Problem Statement](#-problem-statement)
- [Data Source](#-data-source)
- [Project Structure](#-project-structure)
- [Methodology](#-methodology)
  - [1. Data Loading and Subsetting](#1-data-loading-and-subsetting)
  - [2. Variable Selection and Cleaning](#2-variable-selection-and-cleaning)
  - [3. Missing Value Handling](#3-missing-value-handling)
  - [4. Feature Engineering](#4-feature-engineering)
  - [5. Exploratory Data Analysis](#5-exploratory-data-analysis)
- [Key Findings](#-key-findings)
- [Visualizations](#-visualizations)
- [Technical Specifications](#-technical-specifications)
- [How to Run](#-how-to-run)
  [Author](#-author)


About the Project
The **Railway Delay & Punctuality Analyzer** is a data analytics project designed to understand railway delay patterns across different trains, stations, dates, weather conditions, congestion levels, and operational conditions.

The project processes a railway dataset containing **50,000 records** and performs data loading, filtering, extraction, validation, cleaning, aggregation, analysis, visualization, and interpretation.

The analysis covers:

- Train-wise delay patterns
- Station-wise delay patterns
- Monthly delay trends
- Delayed train records
- Special train delays
- Weather-wise delays
- Congestion-wise delays
- Operational disruption patterns
- Delay categories
- High-delay records

  Problem Statement
  Railway delays can be influenced by multiple factors such as train operations, station conditions, weather, congestion, and operational disruptions.

The objective of this project is to analyze railway data systematically and identify:

- How frequently trains are delayed
- The average and maximum delay
- Which trains have higher average delays
- Which stations experience higher delays
- How delays change over time
- How weather conditions relate to delays
- How congestion levels relate to delays
- How special trains perform
- The proportion of records with significant delays

The analysis provides a structured view of railway punctuality and delay patterns.


Data Source
The project uses a railway delay dataset containing **50,000 railway records**.

### Dataset Information

| Property | Details |
|---|---|
| Number of Records | 50,000 |
| Initial Columns | 35 |
| Final Columns | 40 |
| Unique Trains | 21 |
| Unique Stations | 29 |
| Start Date | 2025-02-08 |
| End Date | 2026-02-07 |

The dataset contains information related to:

- Train details
- Station details
- Date and time
- Delay
- Arrival and departure information
- Weather conditions
- Temperature
- Rainfall
- Congestion
- Operational disruptions
- Route and distance information

The dataset used for the analysis is included within the project files.


Project Structure
RailwayDelay_AND_PunctualityAnalyzer/
│
├── stage1-DataLoading and reading/
│   ├── Dataloading_Reading.ipynb
│   └── railway_delay_analyzer_finaldataset
│
├── stage2-Data acquisition and filtering/
│   └── Dataacquisition_Filtering.ipynb
│
├── stage3-Data Extraction/
│   └── Dataextraction.ipynb
│
├── stage4-DataValidation and Cleaning/
│   └── Datavalidation_Cleaning.ipynb
│
├── stage5-Dataaggregation and Representation/
│   ├── Dataaggregation_Represntation.ipynb
│   └── stage4_cleaned_data.csv
│
├── stage6-Data Analysis/
│   └── Data_Analysis.ipynb
│
├── stage7-Data Visualization/
│   ├── Datavisualization.ipynb
│   └── stage7_graphs.zip
│
└── stage8-Results and Interpretation/
    └── Results_Interpretation.ipynb



Methodology
The project follows a structured data analytics workflow.

1. Data Loading and Subsetting:

The first stage focuses on loading and understanding the railway dataset.

Operations performed:
Dataset upload
CSV reading using Pandas
Checking dataset dimensions
Displaying column names
Viewing first and last records
Inspecting dataset information
Understanding data types

The dataset initially contains 50,000 rows and 35 columns.

2. Variable Selection and Cleaning:

Important variables were identified based on the project objectives.

Key variables include:

date
train_no
train_name
type_code
station_no
station_name
delay
weather_condition
temperature_c
rainfall_mm
congestion_index
congestion_level
operational_disruption

Data types were standardized for important fields such as dates and train/station identifiers.

Duplicate records were also checked during the cleaning process


3. Missing Value Handling:

Missing values were identified using column-wise missing-value analysis.

The initial dataset contained missing values in fields such as:

Scheduled arrival minutes
Arrival time
Departure time
Distance from origin
Arrival day
Departure day
Missing-value treatment

For numerical variables:
df[column] = df[column].fillna(df[column].median())
Median imputation was used for selected numerical columns.

For time-related columns:
df[column] = df[column].fillna("UNKNOWN")
After treatment:

Remaining missing values: 0
Duplicate records: 0


4. Feature Engineering:

Several new variables were created to support deeper analysis.

Date-based features

The date information was used to derive:

Year
Month
Day
Day of Week
Delay categories

Delay records were categorized into:

On Time
Delay 1–15 Minutes
Delay >15 Minutes
Train-level features

Train average delay and deviation from train average were calculated.

Station-level features

Station average delay and deviation from station average were calculated.

Additional analysis features

The project also used:

Monthly delay measures
Delayed record counts
Delayed percentage
Maximum delay
Total delay
Weather categories
Congestion categories
Special train identification


5. Exploratory Data Analysis:

Exploratory analysis was performed to understand delay patterns from multiple perspectives.

Time-based analysis

Monthly average, minimum, maximum, and total delays were calculated.

Train-wise analysis

Trains were compared using:

Average delay
Maximum delay
Total delay
Delayed records
Delayed percentage
Station-wise analysis

Stations were analyzed using:

Average delay
Maximum delay
Total delay
Delayed records
Weather-wise analysis

Average delay was compared across different weather conditions.

Congestion-wise analysis

Delay patterns were analyzed across:

Low congestion
Moderate congestion
High congestion
Severe congestion
Special train analysis

Special trains were identified using train type and train-name information and analyzed separately.



Key Findings:

Based on the final project analysis:

Overall Results
Metric	Result
Total Records	: 50,000
On-Time Records	: 5,119
Delayed Records	: 44,444
Delay > 15 Minutes	: 35,619
Delayed Percentage	: 88.89%
Delay > 15 Percentage	:
71.24%
Average Delay	: 87.45 minutes
Maximum Recorded Delay	: 3,335 minutes
Special Train Records	: 34,751


Train Analysis:

The analysis identified trains with higher average delay values and compared their:

Total records
Average delay
Maximum delay
Total delay

Station Analysis:
Station-wise analysis identified stations with higher recorded average delays.
Station-level results should be interpreted together with the number of records available for each station, because some stations have relatively small sample sizes.

Weather Analysis:
Average delay varied across weather conditions.
The recorded average delays ranged from approximately 77.89 minutes for Humid/Cloudy conditions to 103.13 minutes for Fog/Mist conditions.


Congestion Analysis:
The analysis showed different average delays across congestion levels:

Congestion Level	Average Delay
Low	3.16 min
Moderate	23.99 min
High	93.97 min
Severe	257.64 min

This analysis shows a strong difference in observed delay levels across the congestion categories in the project dataset.


Visualizations:

The project contains visualizations for:

1. Monthly Railway Delay

Shows how average railway delay changes over time.

2. Station-wise Delay

Shows the top stations based on average delay.

3. Train-wise Delay

Shows trains with higher average delay.

4. Special Train Delay

Shows delay patterns for identified special trains.

5. Weather-wise Delay

Compares average railway delay across weather conditions.

6. Congestion-wise Delay

Compares average railway delay across congestion levels.

Visualization files are generated in Stage 7 and stored with the project.


Technical Specifications:
Programming Language:
Python
Development Environment:
Google Colab
Jupyter Notebook
Libraries Used:
pandas
numpy
matplotlib

Data Processing:
Pandas DataFrames
CSV files
GroupBy operations
Filtering
Aggregation
Pivot tables
Resampling
Date/time processing
Missing-value handling
IQR-based outlier detection
Visualization:
Matplotlib
Data Format:
CSV
Jupyter Notebook (.ipynb)


How to Run:
Step 1: Clone the Repository
git clone https://github.com/hasiniarimanda182-code/Railwaydelay_Punctualityanalyzer.git

Step 2: Open the Project
cd Railwaydelay_Punctualityanalyzer

Step 3: Open the Notebooks

The project is organized into eight stages.

Run the notebooks in the following order:
Stage 1 → Data Loading & Reading
Stage 2 → Data Acquisition & Filtering
Stage 3 → Data Extraction
Stage 4 → Data Validation & Cleaning
Stage 5 → Data Aggregation & Representation
Stage 6 → Data Analysis
Stage 7 → Data Visualization
Stage 8 → Results & Interpretation


Step 4: Run in Google Colab

Upload the required dataset when prompted by each notebook.

The notebooks use:
from google.colab import files
to upload datasets


Step 5: Execute the Cells

Run the notebook cells sequentially.

Each stage generates the required intermediate datasets, analysis outputs, or visualizations for the following stage.


Author:
## 👩‍💻 Team Members

- Hasini Reddy Arimanda — Repository Maintainer
- M.Bhuvan Manikanta
- G.Lakshmi Priya
- E.Venkat

GitHub:
https://github.com/hasiniarimanda182-code

GitHub Repository:
https://github.com/hasiniarimanda182-code/Railwaydelay_Punctualityanalyzer


Project Summary:

This project demonstrates an end-to-end data analytics workflow for railway delay and punctuality analysis.

The complete pipeline covers:

Data Loading → Data Acquisition → Data Extraction → Data Cleaning → Data Aggregation → Data Analysis → Data Visualization → Results & Interpretation

The project provides insights into railway delay behavior across trains, stations, time periods, weather conditions, congestion levels, and operational factors.
