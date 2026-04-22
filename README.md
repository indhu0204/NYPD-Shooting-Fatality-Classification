

***

# NYPD Shooting Fatality Classification
### **A Systematic Comparative Analysis of Spatial-Temporal Machine Learning Approaches**





## 1. Project Overview
This project develops a machine learning framework to classify the lethality of shooting incidents in New York City. While NYC records thousands of shootings annually, only ~19% result in fatalities. This tool serves as a **Risk-Scoring Triage Tool** to assist law enforcement and emergency medical services (EMS) in prioritizing high-risk incidents during the critical "Golden Hour" of medical response.

Using 17 years of official NYPD administrative records, I conducted a systematic comparison of 13 model configurations to identify the optimal balance between predictive accuracy and model parsimony.

###  Research Question
> *"To what extent can machine learning models accurately classify NYPD shooting incidents as fatal versus non-fatal, and which spatial and temporal factors are most strongly associated with these outcomes?"*

***

## 2. Key Findings
*   **Optimal Model:** Random Forest with cost-sensitive class weighting.
*   **Performance:** Achieved **0.68 AUC-ROC** and **80.15% accuracy**, representing a **21.6% improvement** over the baseline.
*   **Geographic Dominance:** Location is the primary driver of fatality, accounting for **75.1% of predictive power**.
*   **The Parsimony Advantage:** A minimal 4-feature set (Lat, Lon, Hour, Month) outperformed complex 13-feature sets by reducing demographic noise.
*   **Redundancy:** Ablation studies proved that administrative boundaries (Precincts) are redundant when precise GPS coordinates are available.

***

## 3. Repository Structure
The repository is organized for easy access to the data, code, and final documentation:

```text
├── NYPD_Shooting_Incident_Data_Historic_.csv # Dataset used for analysis
├── NYPD_Fatality_Analysis_Final.ipynb        # Complete Python Notebook (EDA & Modeling)
├── Project_Presentation.pdf                # Project Presentation Slides
├── Final_Project_Report.pdf                 # Comprehensive Academic Report
├── All_experiment_results.csv                # results of all models in csv
├── requirements.txt                         # List of Python dependencies
└── README.md                                # Project documentation
```

***

## 4. Installation & Setup
To reproduce this analysis locally, follow these steps:

1. **Clone the repository:**
```bash
git clone https://github.com/indhu0204/NYPD-Shooting-Fatality-Classification.git
cd NYPD-Shooting-Fatality-Classification
```

2. **Install dependencies:**
```bash
pip install -r requirements.txt
```

***

## 5. Usage
1.  Open the `NYPD_Fatality_Analysis_Final.ipynb` in a Jupyter environment or Google Colab.
2.  Ensure the `.csv` file and `.pkl` model files are in the same directory as the notebook.
3.  The notebook is organized into 29 sections covering everything from initial data cleaning to the interactive **Gradio deployment** at the end.
4.  Run the final Gradio cell to launch the web interface for real-time risk scoring.

***

## 6. Experimental Framework
I executed 5 systematic experiments testing 13 configurations:
1.  **Exp 1:** Full Features (13) + SMOTE
2.  **Exp 2:** Simple_02 Set (5) + SMOTE
3.  **Exp 3:** Full Features (13) + Class Weights
4.  **Exp 4:** Simple_02 Set (5) + Class Weights
5.  **Exp 5:** Simple_03 Set (4) - Ablation Study (Best Model)

***

## 7. Author
**Indhu Reddy Kottalam Raveendra Reddy**
MSc Data Science Student
University of Hertfordshire

*Module: 7PAM2002-0206-2025 Data Science Project*

***

## 8. License
This project is licensed under the MIT License.

***

## 9. Acknowledgments
*   **Data Source:** NYPD and the City of New York via NYC Open Data.
*   **Theory:** Weisburd’s (2015) Law of Crime Concentration.

***

**Note:** This model is designed as a decision-support tool. It detects ~31% of fatalities with a very low false-alarm rate (8.2%), making it suitable for risk scoring but not autonomous decision-making.
