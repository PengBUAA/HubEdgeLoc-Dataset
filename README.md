# HubEdgeLoc-Dataset
Official dataset for "HubEdgeLoc" . A large-scale, longitudinal Wi-Fi RSS indoor localization dataset spanning 5 months in an airport and 2 months on a university campus, designed for evaluating Edge AI robustness.

# HubEdgeLoc Dataset 📍📶

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Paper](https://img.shields.io/badge/Paper-IMWUT-blue.svg)](#) 

This repository contains the official dataset for the IMWUT paper: **"[Your Paper Title Here]"**. 

HubEdgeLoc provides a large-scale, **longitudinal Wi-Fi Received Signal Strength (RSS)** dataset specifically collected to evaluate the long-term robustness and generalization of lightweight indoor localization models on edge devices.

## 🌟 Dataset Highlights

Unlike traditional static datasets, HubEdgeLoc focuses on the temporal dynamics of indoor environments (Concept Drift caused by environmental changes, human traffic, and AP fluctuations). 

* **Longitudinal Span:** Features continuous data collection spanning **5 months** in a large-scale transportation hub and **2 months** in an academic building.
* **Dual Scenarios:** * ✈️ **Airport Terminal:** Highly complex, dynamic environment covering over 10,000 square meters (Guiyang Longdongpu International Airport).
  * 🏫 **University Campus:** Structured, moderately dynamic indoor space (BUAA Campus).
* **Edge-Oriented:** Focused on lightweight RSS fingerprints, ideal for deploying state-space models (e.g., Mamba) and TinyML algorithms on resource-constrained microcontrollers.

## 📂 Directory Structure

The dataset is organized by scenario and then by data collection month to facilitate temporal evaluation.

```text
HubEdgeLoc-Dataset/
├── README.md
├── data/
│   ├── Airport/
│   │   ├── Month_1/
│   │   │   ├── rss_data.csv       # Wi-Fi RSS fingerprints
│   │   │   └── labels.csv         # Ground truth coordinates (x, y)
│   │   ├── Month_2/
│   │   ├── ...
│   │   └── Month_5/
│   └── Campus/
│       ├── Month_1/
│       └── Month_2/
├── scripts/
│   ├── temporal_dataloader.py     # Script to load data across time windows
│   └── evaluate_drift.py          # Example script for testing model robustness over time
└── AP_mac_mapping.json            # Anonymized MAC address to index mapping
