# ENDO-TWIN
A Personalized Digital Twin for Longitudinal Endocrine-Rhythm Monitoring

ENDO-TWIN is an AI-assisted research prototype exploring how wearable-derived physiological signals and personalized baselines can be used to identify persistent changes in an individual's physiological patterns over time, with a focus on women's endocrine health and PCOS-related research.

> Disclaimer: ENDO-TWIN is an experimental research prototype, not a clinically validated screening or diagnostic tool. It does not directly measure hormone concentrations or establish a PCOS diagnosis.

## Problem Statement

Physiological patterns vary between individuals and change over time. Analysing isolated measurements may not fully capture these changes. ENDO-TWIN explores a personalized approach that compares an individual's physiological signals with their own baseline and monitors whether deviations persist over time.

## Our Solution

ENDO-TWIN establishes a personal physiological baseline, calculates deviation scores, and applies a persistence-based monitoring mechanism to identify sustained changes.

The prototype categorizes observations into three states:

- Stable: Physiological signals remain broadly consistent with the model's baseline.
- Monitoring: A deviation warrants continued observation.
- Persistent Deviation: Deviations satisfy the model's persistence criteria.

These are computational states, not medical diagnoses.

## Key Features

- Personalized physiological baseline calculation
- Longitudinal deviation scoring
- Persistence-based monitoring
- Synthetic-data generation and testing
- Exploratory analysis of real menstrual-cycle research data
- Interactive dashboard for viewing individual physiological trends
- Comparison of personalized and population-based baselines
- Visualization of physiological signals over time

## Signals Explored

The prototype uses or explores the following variables:

- Resting heart rate
- Heart rate variability (HRV)
- Sleep duration and sleep-related measures
- Wrist temperature
- Physical activity

The real-data exploration also examines available menstrual-cycle and hormone measurements. Hormone measurements are used for exploratory analysis rather than as inputs to the physiological deviation-monitoring model.

## How It Works

1. Data preparation: Load and organize longitudinal physiological observations.
2. Baseline construction: Estimate each simulated individual's usual physiological patterns.
3. Deviation calculation: Compare observations against personal baseline values.
4. Persistence analysis: Examine deviations over rolling time windows.
5. State assignment: Categorize observations using predefined model thresholds.
6. Visualization: Explore individual trends and model-generated states in an interactive dashboard.

## Dataset and Testing

### Synthetic Dataset

The prototype was tested using a synthetic dataset containing:

- 400 simulated users
- 180 simulated days per user
- 72,000 total observations
- Four simulated groups: normal, PCOS-like, temporary disturbance, and variable

The dataset was deliberately constructed to represent different physiological patterns. It demonstrates the system's intended behaviour under simulated conditions but does not establish real-world diagnostic accuracy.

### Real-Data Exploration

The project also explores the mcPHASES menstrual-cycle dataset from PhysioNet.

The available data used for exploratory analysis included 42 participants and 5,659 participant-day records in the hormone and self-report dataset. Coverage varied across physiological signals, with HRV and wrist-temperature observations particularly limited.

This analysis investigated associations between selected physiological measurements, menstrual-cycle phases, and hormone measurements. These findings are exploratory and do not validate PCOS detection.

Data access note: The real dataset is subject to its own access and usage conditions. Raw restricted-access files are not included in this repository. Users must obtain authorized access through the original source.

## Results and Interpretation

The synthetic-data experiment demonstrated that the persistence-based state engine could distinguish sustained simulated changes from short-lived disturbances under the conditions encoded in the data.

The comparison between personalized and population-based baselines produced a mean deviation score of 3.143 versus 2.720 for the simulated PCOS-like group. Both approaches achieved an ROC-AUC of 1.00 in the constructed synthetic classification experiment.

These results must be interpreted cautiously: the synthetic patterns were deliberately designed, and the results do not demonstrate clinical performance or establish that personalized baselines improve classification accuracy.

The real-data analysis provides exploratory physiological context only. Clinical validation using appropriately characterized data is still required.

## Technology Stack

- Python — core programming language
- Google Colab — development and execution environment
- Pandas — data processing and analysis
- NumPy — numerical operations
- Matplotlib — visualization
- scikit-learn — used where applicable for model evaluation

## Getting Started

### Option 1: Open in Google Colab

Open the project notebook:

https://colab.research.google.com/drive/1BYpTJIU40UVbUMhkpITPyGbWACbjKcwr

Ensure you have access to the notebook and any required datasets before running the cells.

### Option 2: Run Locally

Clone the repository:

    git clone YOUR_GITHUB_REPOSITORY_URL
    cd ENDO-TWIN

Install the commonly used libraries:

    pip install pandas numpy matplotlib scikit-learn

Open the .ipynb notebook in Jupyter Notebook, JupyterLab, or VS Code.

Note: Replace YOUR_GITHUB_REPOSITORY_URL with your actual repository URL before running the commands. Additional libraries may be required depending on the notebook's imports. Dataset files must be provided separately when they are not included in the repository.

## Future Scope

- Validate the approach using larger datasets with clinically confirmed outcomes.
- Evaluate performance on participants not used during model development.
- Compare personalized and population-based baselines using appropriate validation methods.
- Improve missing-data handling and robustness across individuals.
- Evaluate sensitivity, specificity, false-positive rates, and generalizability.
- Develop a more accessible dashboard for longitudinal research and monitoring.

## Vision

ENDO-TWIN explores how personalized, longitudinal physiological monitoring could contribute to future women's health research. Our aim is to investigate changes in individual patterns over time while recognizing that wearable-derived signals are indirect indicators and cannot replace clinical assessment.

## Project Information

- Project: ENDO-TWIN
- Domain: Biotechnology, Artificial Intelligence, Digital Health, Women's Health
- Project type: Research prototype / hackathon project

## Medical Disclaimer

ENDO-TWIN is intended for research and educational demonstration. It is not intended to diagnose, screen for, or treat PCOS or any other medical condition. Its model-generated states do not establish hormone levels or clinical abnormalities. Clinical validation and appropriate professional oversight would be required before any healthcare application.
