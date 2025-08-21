#  Cyclone Intensity Prediction with Multi-Channel Satellite Images  

This repository contains experiments on predicting tropical cyclone characteristics using multi-channel satellite imagery (VIS, IR, WV, PMW).  
The models aim to estimate three key indicators:  

- **Maximum sustained wind (knots)**  
- **Minimum sea-level pressure (hPa)**  
- **Cyclone size (km)**  

##  Models Implemented
- **MultiOutputCNN (baseline)** – Simple CNN trained from scratch.  
- **ResNet+CNN (best performer)** – ResNet backbone for spatial features + CNN branch for additional channel fusion.  
- **ViT+CNN** – Vision Transformer with CNN branch for channel fusion.  

##  Results Summary
- ResNet+CNN achieves the **best performance**, with R² above 0.90 for wind and pressure.  
- ViT shows potential but requires more data and domain-specific pretraining.  
- Fusion of the additional satellite channels (beyond VIS) significantly improves performance.  

##  Dataset
Filtered version of **TCIR (Tropical Cyclone for Image-to-Intensity Regression)** dataset:  
- Original dataset: 21,076 images.  
- In this notebook, we use a **subset of 5,000 observations** for faster experimentation.  
- 4 channels: **Visible, Infrared, Water Vapour, Passive Microwave**.  
- Labels include wind, pressure, size, and other metadata.  

More details: [TCIR dataset GitHub](https://github.com/BoyoChen/TCIR).  

##  Usage
Clone the repository and open the notebook:  
```bash
git clone https://github.com/your-username/cyclone-intensity-prediction.git
cd cyclone-intensity-prediction
jupyter notebook Cyclone_Intensity_Prediction_MultiChannel.ipynb
```
