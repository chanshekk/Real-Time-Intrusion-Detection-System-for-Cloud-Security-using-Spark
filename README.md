Real-Time-Intrusion-Detection-System-for-Cloud-Security-using-Spark
This project implements a Real-Time Intrusion Detection System (IDS) using the UNSW-NB15 dataset and Apache Spark. It compares Spark and non-Spark approaches, with and without feature selection, using Decision Tree classifiers. Results include accuracy, F1-score, confusion matrix, and execution time analysis.


Real-Time Intrusion Detection System for Cloud Security using Spark

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YourUserName/YourRepoName/blob/main/IDS_Project.ipynb)

📌 Overview
This project implements a Real-Time Intrusion Detection System (IDS) for cloud security using Apache Spark and the UNSW-NB15 dataset.  
The IDS is designed to classify network traffic into normal and attack categories in real-time, leveraging distributed computing with Spark for scalability.  

The model compares performance with and without feature selection techniques to evaluate improvements in execution time and accuracy.  

📂 Dataset
The project uses the UNSW-NB15 Dataset, created by the Australian Centre for Cyber Security (ACCS).  
🔗 Official Dataset Link: [UNSW-NB15 Dataset](https://research.unsw.edu.au/projects/unsw-nb15-dataset)  
It contains 100 GB of network traffic data, processed into 2,540,044 records with 49 features representing both normal and malicious traffic.  

⚙️ Methodology
The project was implemented in four main parts:

Part 0: Preprocessing
- Combined training and testing CSVs into one dataset (`UNSW_NB15_full.csv`).  
- Label encoding for categorical values.  
- Missing value handling using mean imputation.  
- Feature standardization using StandardScaler and MinMaxScaler.  

Output:  

Part 1: Execution without Feature Selection (Sklearn + Spark setup)
- Used Decision Tree Classifier on preprocessed features.  
Key Results:  
- Accuracy: 0.7989 
- F1-score: 0.7731  
- Execution Time: 5.49 sec  

Part 2: Execution without Feature Selection (Spark MLlib)
- Built a Spark DataFrame with `VectorAssembler`.  
- Trained Spark MLlib Decision Tree Classifier.  
Key Results:  
- Accuracy: 0.7997 
- F1-score: 0.7699  
- Execution Time: 156.06 sec  

Part 3: Execution with Feature Selection (Sklearn + Spark setup)
- Applied Chi-Square Feature Selection (Top 20 features).  
- Trained Decision Tree Classifier on reduced features.  
Key Results:  
- Accuracy: 0.8039  
- F1-score: 0.7719  
- Execution Time: 2.32 sec  

Part 4: Execution with Feature Selection (Spark MLlib)
- Used Spark’s VectorSlicer to apply same selected features.  
- Trained Spark MLlib Decision Tree Classifier.  
Key Results:  
- Accuracy: 0.8001  
- F1-score: 0.7710  
- Execution Time: 65.86 sec  

Summary of Results
| Experiment                | Accuracy | F1-score | Execution Time |
|---------------------------|----------|---------------------------|
| Part 1 – No FS (Sklearn)  | 0.7989   | 0.7731   | 5.49 sec       |
| Part 2 – No FS (Spark)    | 0.7997   | 0.7699   | 156.06 sec     |
| Part 3 – With FS (Sklearn)| 0.8039   | 0.7719   | 2.32 sec       |
| Part 4 – With FS (Spark)  | 0.8001   | 0.7710   | 65.86 sec      |

✅ Best Accuracy: 80.39% (Part 3 – With Feature Selection on Sklearn)  
✅ Fastest Execution: 2.32 sec (Part 3 – With Feature Selection on Sklearn)  

🚀 How to Run

Run in Google Colab
Click the badge below to open the notebook directly in Colab:  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YourUserName/YourRepoName/blob/main/IDS_Project.ipynb)


