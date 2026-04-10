# ml-whodas-short-forms
Analysis code, scoring tool, and score-transformation scripts for the ML-WHODAS short forms (ML-WHODAS-10 and ML-WHODAS-16) in dementia disability assessment.

# ML-WHODAS Short Forms

Analysis code, scoring tool, and score-transformation scripts for the ML-WHODAS short forms (ML-WHODAS-10 and ML-WHODAS-16) in dementia disability assessment.

## 📂 Repository Contents

This repository contains all necessary files to replicate the analysis and implement the scoring system:

* **`ML-WHODAS scoring system.ipynb`**: The interactive Google Colab notebook containing the automated scoring tool.
* **`R1_analysis_orig_colab-version_R.ipynb`**: The primary analysis script used for the study.
* **`final_model_10_items_balanced_optimized.json`**: Pre-trained XGBoost model parameters for the 10-item version.
* **`final_model_16_items_balanced_optimized.json`**: Pre-trained XGBoost model parameters for the 16-item version.
* **`Data example_10-item.xlsx` & `Data example_16-item.xlsx`**: Data templates demonstrating the required formatting.

---

## 📖 How to Use the ML Score Converter

Welcome! This tool automatically converts your raw questionnaire scores into Machine Learning (ML) transformed scores. It is fully automated and requires no coding experience. Just follow these simple steps!

### Part 1: Prepare Your Data

Before running the converter, please ensure your dataset is saved as an Excel (`.xlsx`) or CSV (`.csv`) file and formatted correctly.

* **ID Column**: Your file must include an `id` column to identify each record.
* **Item Columns**: The tool supports either 10-item or 16-item versions.
* **Column Naming Rule**: The item column headers **must** start with their corresponding specific "D-code" format (e.g., `D1.1`, `D2.2`). The program relies on these codes to accurately match your data with the model's features. (For example: *D1.1 Concentration*, *D1.6 Conversation*).

💡 **Need a reference?** Please click the files below to view or download the exact data templates:
* [Data example_10-item.xlsx](./Data%20example_10-item.xlsx)
* [Data example_16-item.xlsx](./Data%20example_16-item.xlsx)

### Part 2: Run the Converter

Once your data is ready, follow these steps to get your transformed scores:

1.  **Open the Tool**: Open the `ML-WHODAS scoring system.ipynb` notebook in Google Colab.
2.  **Run the Code**: Click the **"Play"** button on the left side of the code block to execute it.
3.  **Upload Your File**: When the code runs, a **"Choose Files"** button will appear. Click it and select your prepared data file from your computer.
4.  **Automatic Processing**: Sit back and wait a few seconds! The script is smart enough to:
    * Automatically detect whether your file contains 10 or 16 items.
    * Load the corresponding pre-trained XGBoost ML model.
    * Map your columns and calculate the scores.
5.  **Download Results**: Upon completion, the tool will automatically download a new Excel file to your computer (e.g., `transformed_output_10items.xlsx`). Open this file, and you will find a brand new column at the very end called `final_score`!

---

## 🛠️ Requirements

If you are running the scripts locally instead of Google Colab, ensure you have the following installed:
* Python 3.x
* `xgboost`
* `pandas`
* `openpyxl` (for reading/writing Excel files)

## 📄 License

This project is licensed under the MIT License.
