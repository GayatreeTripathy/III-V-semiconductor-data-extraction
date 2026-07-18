# III-V Compound Semiconductor Data Extraction & Cleaning

## 📌 Project Overview
This project contains an automated data extraction and target cleaning pipeline for III-V compound semiconductors. Using the official Materials Project API, the pipeline queries solid-state materials properties to create a curated summary dataset optimized for downstream exploratory data analysis and semiconductor screening.

## 🛠️ Data Extraction & Cleaning Process
- **Data Source:** Extracted programmatically from the [Materials Project](https://materialsproject.org/) database.
- **Initial Dataset:** 199 unique III-V materials extracted based on structural elements.
- **Domain Filtering & Methodology Note (Data Cleaning):** Eliminated all rows where the calculated **band gap was less than 0 eV**. 
  * *Methodology Note:* The band gap values obtained from the Materials Project are derived via **theoretical computational methods** (such as Density Functional Theory). Real-world **experimental** band gaps will be more or less different depending on synthesis methods, defects, and process conditions. 
  * *Cleaning Logic:* Because the objective is semiconductor screening, negative theoretical values (which indicate unphysical states or metallic character under calculation constraints) were dropped to maintain a clean, high-fidelity candidate dataset.

## 📂 File Directory
- `III_V_Semiconductors_Datasetall.csv`: The final, filtered 12 KB summary dataset containing 199 rows.
- `iii_v_data_extraction.ipynb`: The Jupyter Notebook documenting the step-by-step extraction code, API authentication, and filtering logic.

## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.
