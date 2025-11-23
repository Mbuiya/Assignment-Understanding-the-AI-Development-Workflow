# Assignment-Understanding-the-AI-Development-Workflow
Assignment: Understanding the AI Development Workflow

Course: AI for Software Engineering
Total Points: 100
Submission: PDF + GitHub Repository

Part 1: Short Answer Questions (30 points)
1. Problem Definition (6 points)
Hypothetical Problem

Predicting Student Dropout Rates using historical academic, behavioral, and demographic data.

Objectives

Identify students at risk of dropping out early enough for intervention.

Improve retention rates through data-driven decision-making.

Provide actionable insights to academic advisors and administrators.

Stakeholders

Primary: University administration.

Secondary: Academic advisors; students indirectly affected.

KPI

Area Under the ROC Curve (AUC): Measures the model’s ability to distinguish between likely dropouts and non-dropouts.

2. Data Collection & Preprocessing (8 points)
Data Sources

Student Information System (SIS) — grades, attendance, course load.

Learning Management System (LMS) — login frequency, assignment submissions.

Potential Bias

Socioeconomic bias: Students from low-income backgrounds may be disproportionately represented as “high risk” due to limited access to learning resources.

Preprocessing Steps

Handle missing values using mean/median imputation for numeric fields.

Normalize continuous variables such as GPA and time spent on LMS.

Encode categorical variables (e.g., major, gender) using one-hot encoding.

3. Model Development (8 points)
Chosen Model

Random Forest Classifier

Justification: Handles non-linear patterns, robust to noise, interpretable via feature importance, works well with mixed data types.

Data Splitting Strategy

70% Training, 15% Validation, 15% Test
Validation used for hyperparameter tuning; test set used for final evaluation.

Hyperparameters to Tune

Number of trees (n_estimators): Affects performance and stability.

Maximum tree depth (max_depth): Prevents overfitting.

4. Evaluation & Deployment (8 points)
Evaluation Metrics

Precision: Important when false positives (incorrectly labeling a student at risk) lead to wasted intervention resources.

Recall: Critical to avoid missing students truly at risk.

Concept Drift

Changes in the statistical properties of input data over time (e.g., new learning platforms, curriculum changes).
Monitoring: Track model performance weekly and retrain whenever accuracy drops below a threshold.

Technical Deployment Challenge

Scalability: Integrating the model into a student portal may require real-time predictions, increasing computational load.

Part 2: Case Study Application (40 points)
Scenario:

A hospital needs an AI system to predict patient readmission risk within 30 days.

Problem Scope (5 points)
Problem Definition

Build a predictive system that identifies high-risk patients before discharge.

Objectives

Reduce hospital readmission penalties.

Assist clinicians in designing preventive care plans.

Allocate resources (follow-up calls, home visits) efficiently.

Stakeholders

Hospital administrators

Clinicians (doctors, nurses)

Patients

Data Strategy (10 points)
Data Sources

Electronic Health Records (EHRs) — diagnoses, vitals, lab results

Demographic data — age, gender, socioeconomic status

Previous hospitalization history

Medication and treatment plans

Ethical Concerns

Patient privacy: Sensitive medical data must be protected.

Bias in clinical data: Certain groups may have historically limited access to healthcare, influencing prediction outcomes.

Preprocessing + Feature Engineering Pipeline

Data cleaning:

Remove duplicate entries

Impute missing vitals and labs

Normalization:

Scale lab values to reduce model sensitivity

Feature Engineering:

Create features such as “number of hospital visits in the past year”

Aggregate lab trends (e.g., increasing or decreasing glucose levels)

Compute length of stay, a strong predictor of readmission

Encoding:

One-hot encode diagnosis codes

Train–test split:

Stratified sampling due to class imbalance

Model Development (10 points)
Selected Model

Gradient Boosted Trees (XGBoost)

Justification: Excellent performance on structured/tabular medical data; handles non-linear relationships; robust to missing data.

Hypothetical Confusion Matrix (Test Set)
	Predicted Readmit	Predicted No Readmit
Actual Readmit	80	20
Actual No Readmit	30	170
Precision & Recall

Precision = 80 / (80 + 30) = 0.727

Recall = 80 / (80 + 20) = 0.80

Interpretation:

The model correctly identifies 72.7% of predicted readmissions.

It captures 80% of all actual readmissions—useful for clinical intervention.

Deployment (10 points)
Integration Steps

Deploy model as a REST API within the hospital network.

Connect API to the EHR system so doctors see risk scores in real time.

Implement model versioning and monitoring dashboard.

Train staff on interpreting the risk outputs.

Compliance with Healthcare Regulations

Encrypt all patient data in transit (HTTPS, TLS).

Store data only on hospital-approved, HIPAA-compliant servers.

Use role-based access control (RBAC) to ensure only authorized clinicians view predictions.

Log all data access for audit trails.

Optimization (5 points)
Reducing Overfitting

Apply regularization techniques (e.g., XGBoost’s lambda and alpha) to penalize overly complex models.

Part 3: Critical Thinking (20 points)
Ethics & Bias (10 points)
Impact of Biased Training Data

If historically underserved patients have higher readmission due to external socioeconomic factors, the model may systematically label them as “high risk,” leading to:

Over-intervention or unnecessary monitoring

Misallocation of resources

Reinforcement of healthcare disparities

Bias Mitigation Strategy

Use reweighing: Assign higher weights to underrepresented groups during training to equalize influence on the model.

Trade-offs (10 points)
Interpretability vs Accuracy

High-accuracy models (e.g., XGBoost, deep learning) may lack transparency, making clinicians hesitant to trust them.

Interpretable models (logistic regression, decision trees) facilitate clinical accountability but may perform worse.

Impact of Limited Computational Resources

The hospital might choose simpler models like Logistic Regression to balance:

Low latency

Lower compute cost

Ease of on-premises deployment

Part 4: Reflection & Workflow Diagram (10 points)
Reflection (5 points)

The most challenging part of the workflow was data preprocessing, especially designing features that accurately represent patient health trends. Medical data is messy, sparse, and heterogeneous.
With more time, I would collaborate with clinicians to incorporate domain knowledge into feature engineering and experiment with more advanced interpretability tools like SHAP values.

Workflow Diagram (5 points)

(Describe as text; you can later convert into a flowchart.)

AI Development Workflow Diagram

Problem Definition 
        ↓
Data Collection → Data Understanding 
        ↓
Data Cleaning & Preprocessing 
        ↓
Feature Engineering 
        ↓
Model Development 
        ↓
Model Evaluation 
        ↓
Deployment 
        ↓
Monitoring & Maintenance (handles concept drift)

The PDF has been generated successfully. You can download it here:

[📄 Download AI_Development_Workflow_Assignment.pdf](sandbox:/mnt/data/AI_Development_Workflow_Assignment.pdf)
