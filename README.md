# 🌊 Coastal Erosion Detection with Satellite Imagery

This project detects and quantifies shoreline erosion and accretion over time using **Sentinel-2 satellite imagery**, the **Normalized Difference Water Index (NDWI)**, and **Google Earth Engine (GEE)**. It focuses on identifying changes along coastal zones—e.g., Lagos, Nigeria—between 2016 and 2024.

---

## 📌 Objectives

- Detect shoreline position changes using NDWI.
- Identify areas of **erosion** and **accretion**.
- Estimate and export affected areas (in hectares) to CSV.
- Visualize changes on an interactive map using `geemap`.

---

## 📊 Methodology

1. **Data Source**:  
   - Sentinel-2 Surface Reflectance (`COPERNICUS/S2_SR`)

2. **Area of Interest (AOI)**:  
   - Lagos coastline (modifiable)

3. **Index Used**:  
   - NDWI = (Green - NIR) / (Green + NIR)

4. **Processing Steps**:
   - Compute NDWI for years 2016 and 2024
   - Extract water masks using a threshold (NDWI > 0.3)
   - Compare binary water masks to detect:
     - `-1` → **Erosion**
     - `+1` → **Accretion**
   - Calculate area in hectares using `ee.Image.pixelArea()`
   - Export results to CSV

---

## 🖥️ Installation

### Python Requirements

```bash
pip install earthengine-api geemap pandas

Earth Engine Authentication

import ee
ee.Authenticate()
ee.Initialize()

📁 Files in Repository
File	Description
coastal_erosion_detection.py	Main script for shoreline change detection
coastal_erosion_accretion_area.csv	Output CSV with area (ha) of erosion/accretion
README.md	Project overview and setup guide
🗺️ Visualization Example

    Blue: Water in 2016

    Green: Water in 2024

    Red: Erosion (water encroached land)

    Green (in change map): Accretion (land gain)

Interactive map is built using geemap.
📤 Output Example

Change_Type,Area_ha
Erosion,128.74
Accretion,53.21

🧠 Future Improvements

    Integrate Landsat time series for long-term shoreline dynamics.

    Classify shoreline types (sandy, rocky, mangroves).

    Validate results with UAV or field data.

    Extend to global coastlines using batch AOI loops.

👨‍💻 Author

Akajiku
Geospatial Analyst & Earth Observation Specialist
📜 License

This project is licensed under the MIT License.


---

Would you like me to bundle this into a GitHub repository structure with folders like `/notebooks`, `/data`, and `/scripts`?

