# Urban Heat Island Detection 

This project analyzes **Urban Heat Island (UHI)** patterns using **Landsat 9 satellite imagery** of **Lucknow, India**, captured on **9 June 2025**.  
The notebook processes satellite spectral bands to calculate vegetation indices and land surface temperature, helping identify areas with higher urban heat risk.

The project combines **remote sensing techniques** with **unsupervised machine learning** to analyze temperature and vegetation patterns across the study area.

---

## Project Workflow

The notebook performs the following steps:

1. Upload and load Landsat spectral band files
2. Calculate **NDVI (Normalized Difference Vegetation Index)** using Red and Near-Infrared bands
3. Estimate **Land Surface Temperature (LST)** using the thermal band
4. Detect Urban Heat Island regions using a **threshold-based method**
5. Apply **K-Means clustering** to analyze heat risk using an AI-based approach
6. Visualize the resulting heat risk maps

---

## Dataset

The project uses **Landsat 9 imagery of Lucknow, Uttar Pradesh, India**.

Required spectral bands:

| Band | Description | File Name |
|-----|-------------|-----------|
| Band 4 | Red band (vegetation absorption) | `LC09_L1TP_144041_20250609_20250609_02_T1_B4.TIF` |
| Band 5 | Near Infrared band | `LC09_L1TP_144041_20250609_20250609_02_T1_B5.TIF` |
| Band 10 | Thermal Infrared band | `LC09_L1TP_144041_20250609_20250609_02_T1_B10.TIF` |

Due to GitHub file size limits, the band files are provided via Google Drive.

Download them here: https://drive.google.com/drive/folders/1DETofjSMO0hw0y2PY6iOnWZyP4xZJ7dv?usp=drive_link

After downloading, upload these files to the notebook runtime before running the analysis.

---

## Methods Used

### 1. NDVI Calculation

NDVI is used to identify vegetation density using the formula: 

NDVI = (NIR - Red) / (NIR + Red)

Higher NDVI values represent dense vegetation, while lower values indicate built-up or barren land.

---

### 2. Land Surface Temperature Estimation

The thermal band (Band 10) is used to estimate surface temperature by converting:

1. Digital Numbers → Spectral Radiance  
2. Radiance → Brightness Temperature  
3. Temperature from Kelvin → Celsius

---

### 3. Urban Heat Island Detection

Two approaches are used to identify UHI regions.

#### Threshold-Based Method
Pixels with:
- **High surface temperature**
- **Low NDVI**

are classified as Urban Heat Island zones.

#### AI-Based Method
An **unsupervised machine learning algorithm (K-Means clustering)** groups pixels based on:

- NDVI values  
- Land Surface Temperature

The clusters represent different **urban heat risk levels**.

---

## Technologies Used

- Python  
- NumPy  
- Rasterio  
- Matplotlib  
- Scikit-learn  

---

## How to Run the Project

1. Clone the repository
2. Download the Landsat band files from the Google Drive link
3. Open the notebook in **Google Colab or Jupyter Notebook**
4. Upload the `.TIF` files when prompted
5. Run the notebook cells sequentially

---

## Study Area

The analysis focuses on **Lucknow, Uttar Pradesh, India**, using Landsat 9 imagery captured on **9 June 2025**.

---

## Results

The notebook generates:

- NDVI vegetation maps  
- Land Surface Temperature maps  
- Urban Heat Island risk maps  

These outputs help visualize how **urban areas experience higher surface temperatures compared to vegetated regions**.

---

## Project Purpose

This project demonstrates how **satellite remote sensing and machine learning techniques** can be used to analyze environmental patterns such as urban heat islands.

---
