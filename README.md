<h1 align="center">🧠 Machine Learning for Stroke Risk Prediction</h1>

<p align="center">
  <img src="https://img.shields.io/badge/R-Data%20Science-blue?logo=r&style=for-the-badge" />
  <img src="https://img.shields.io/badge/Shiny-App%20Deployed-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Machine%20Learning-HealthTech-orange?style=for-the-badge" />
</p>

<p align="center">
  <em>A complete machine learning pipeline with real-time deployment using Shiny.<br/>
  Built to assist in early stroke detection and personalized prevention strategies.</em>
</p>

---

## 🚀 Project Summary

> 🧑‍⚕️ **Goal**: Predict the likelihood of stroke occurrence using individual health and demographic data.

This project:
- Implements multiple **ML models in R** with the `caret` and `Boruta` packages
- Uses **feature selection**, **cross-validation**, and **resampling**
- Deploys an **interactive Shiny app** to assess individual stroke risk

---

## 🗂️ Table of Contents

- [📁 Project Structure](#-project-structure)
- [📊 Data Overview](#-data-overview)
- [🧹 Preprocessing](#-data-preprocessing)
- [📈 Feature Selection](#-feature-selection)
- [🧪 Model Development](#-model-training--evaluation)
- [🌐 Shiny App](#-shiny-app)
- [🛠️ Installation](#-installation--usage)
- [👤 Author](#-author)
- [📄 License](#-license)

---

## 📁 Project Structure

```bash
Machine-Learning-for-Stroke/
│
├── data/               # Raw stroke dataset (CSV)
├── models/             # Model training & evaluation scripts
├── shiny_app/          # Shiny app code
├── reports/            # EDA results & visualizations
└── README.md           # This file
