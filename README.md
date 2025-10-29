# Remote Sensing & Image Analysis   

This repository contains **lab sessions** in **Computer Vision** and **Remote Sensing**.  

- **Lab 1 — Land Cover Classification from Hyperspectral Data**: pixel-wise classification of urban land cover types using spectral and spatial features. 
- **Lab 2 — Multi-Modal Segmentation & Recomposition (YOLO)**: object detection and instance segmentation on visible and infrared images, with creative recomposition tasks.  

## Land Cover Classification from Hyperspectral Data  

### Objective  
Perform pixel-wise **land cover classification** on a hyperspectral image of Washington DC Mall, using spectral and spatial information to distinguish between classes (roof, road, grass, trees, water, shadow).  

### Skills Developed  
- **Remote Sensing & Hyperspectral Imaging**: preprocessing, visualization, and spectral analysis.  
- **Exploratory Data Analysis**: histograms, correlation analysis, variance inspection.  
- **Dimensionality Reduction**: Principal Component Analysis (PCA) for feature extraction.  
- **Supervised Learning**: Support Vector Machine (SVM) classifier applied on spectral and spatial features.  
- **Spatial-Spectral Features**: Extended Morphological Profiles (EMP) for improved classification accuracy.  

### Results  
- Identified the most informative spectral bands for classification.  
- Achieved solid results with SVM on selected bands (~80–85% accuracy).  
- Combining spectral and spatial features with EMP led to **near-perfect classification**, with clear improvements in separating vegetation, buildings, and water.  


## Multi-Modal Segmentation & Recomposition (YOLO)

### Objective
Build an end-to-end pipeline that detects and segments people, bicycles/motorcycles, vehicles, and traffic lights from **visible + infrared** images, then **recomposes** instances onto new backgrounds (Mars, Parking, Moon) with simple fusion and perspective effects.

### Skills Developed
- **Instance Segmentation (YOLO11-seg)**: object masks, boxes, class filtering, confidence thresholds.  
- **Multi-modal Fusion**: RGB↔︎LAB conversions, grayscale IR coloring, channel-wise blending.  
- **Image Composition**: mask extraction, contour ops, background overlay, transparency handling.  
- **Geometric Transforms**: scaling by depth bands, affine warps, placement via centers/boxes.  
- **Utility Engineering**: batching, visualization, saving outputs, reusable helpers.

### Results
- Robust extraction of target classes across both modalities with YOLO11-seg.  
- Two simple fusion methods (RGB/IR averaging & LAB-L channel fusion) yielding cleaner inputs.  
- Realistic recompositions:  
  - **Mars** populated with people/cyclists (hue tweak + depth-aware scaling),  
  - **Parking** arranged vehicles (orientation/placement),  
  - **Moon** scene monitored by traffic lights.  
- Reproducible outputs saved to `outputs/` (e.g., `mars_populated.png`).
