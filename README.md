HSN/SAC Code Validator

Project Description
The HSN/SAC Code Validator is a web-based application built using Streamlit to validate Harmonized System Nomenclature (HSN) codes and Service Accounting Codes (SAC) against master datasets provided in Excel format. The application allows users to upload master data files, validate individual or multiple codes, check hierarchical relationships, and analyze dataset statistics. It is designed to ensure accurate classification of traded products (HSN) and services (SAC) for taxation and compliance purposes.
Features

Data Loading:

Upload HSN and SAC master data files in Excel format (.xlsx, .xls).
Use sample data for demonstration purposes if master files are unavailable.
Display loaded data with total code counts.


Individual Code Validation:

Validate single HSN or SAC codes for format and existence in the master dataset.
Display detailed validation results, including code descriptions and hierarchical parent code validation.


Batch Validation:

Validate multiple HSN or SAC codes entered via text input or uploaded text/CSV files.
Provide downloadable CSV results with validation status, reasons, and descriptions.


Dataset Analytics:

Display statistics such as total code count and code length distribution.
Visualize code length distribution with bar charts.


Hierarchical Validation:

Check the existence of parent codes for a given HSN or SAC code (e.g., for an 8-digit HSN code, validate parent codes like 6-digit, 4-digit, etc.).
Display hierarchical validation results in a tabular format.


User-Friendly Interface:

Streamlit-based web interface with tabs for data loading, code validation, batch validation, and analytics.
Sidebar with project information and usage instructions.



Specifications

Programming Language: Python 3.8+
Dependencies (as specified in requirements.txt):
streamlit>=1.30.0: For the web interface.
pandas>=2.0.0: For data manipulation and Excel file handling.
numpy>=1.24.0: For numerical operations.
openpyxl>=3.1.0: For reading Excel files.


Input Data Format:
HSN Master File: Excel file with columns HSNCode (string) and Description (string).
SAC Master File: Excel file with columns SAC_CD (string) and SAC_Description (string).
Batch Input: Comma-separated or newline-separated codes in text/CSV files or text area input.


Validation Rules:
Format Validation:
HSN codes: Numeric, 1-8 digits.
SAC codes: Numeric, 1-6 digits.


Existence Validation: Check if the code exists in the master dataset.
Hierarchical Validation: Verify parent codes (e.g., for HSN: 2, 4, 6 digits; for SAC: 2, 4, 5 digits).


Output:
Individual validation: Success/error messages, code description, and hierarchical validation table.
Batch validation: Dataframe with code, status, reason, and description; downloadable CSV.
Analytics: Total codes, code length distribution (table and chart).



How to Run

Prerequisites:

Ensure Python 3.8 or higher is installed.
Install required dependencies by running:pip install -r requirements.txt




Setup:

Clone or download the project repository containing the following files:
hsn_code_validator.py: Main application script.
requirements.txt: Dependency list.


Ensure you have HSN and SAC master data files in Excel format (.xlsx or .xls), or use the sample data provided within the application.


Run the Application:

Navigate to the project directory in your terminal.
Execute the following command to start the Streamlit application:streamlit run hsn_code_validator.py


The application will open in your default web browser (typically at http://localhost:8501).


Using the Application:

Data Loading:
Go to the "Data Loading" tab.
Upload HSN and/or SAC master Excel files, or click "Load Sample Data" for demonstration.


Code Validation:
Use the "Code Validation" tab to validate individual HSN or SAC codes.
Enter a code and click the respective validation button to see results.


Batch Validation:
In the "Batch Validation" tab, enter codes in the text area (comma or newline separated) or upload a text/CSV file.
Click the validation button to view results and download the CSV output.


Dataset Analytics:
Visit the "Dataset Analytics" tab to view statistics and code length distribution for loaded datasets.




Notes:

Ensure Excel files have the required columns (HSNCode and Description for HSN; SAC_CD and SAC_Description for SAC). The application automatically renames columns containing "hsn"/"code" or "desc" to the required names if needed.
For large datasets, the application loads data into session state for efficient processing.
Debug information can be enabled via the sidebar checkbox for troubleshooting.



