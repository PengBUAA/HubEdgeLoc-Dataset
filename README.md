# HubEdgeLoc Dataset 📍📶

[![Paper](https://img.shields.io/badge/Paper-IMWUT-blue.svg)](#) 

This repository contains the official dataset for the IMWUT paper: **"[Your Paper Title Here]"**. 

HubEdgeLoc provides a large-scale, **longitudinal Wi-Fi Received Signal Strength (RSS)** dataset specifically collected to evaluate the long-term robustness and generalization of lightweight indoor localization models on edge devices.

## 🌟 Dataset Highlights

Unlike traditional static datasets, HubEdgeLoc focuses on the temporal dynamics of indoor environments (Concept Drift caused by environmental changes, human traffic, and AP fluctuations). 

* **Longitudinal Span:** Features continuous data collection spanning **5 months** in a large-scale transportation hub and **2 months** in an academic building.
* **Dual Scenarios:**
  * ✈️ **Airport Terminal:** Highly complex, dynamic environment covering over 10,000 square meters. First open-source airport WIFI dataset (Guiyang Longdongpu International Airport).
  * 🏫 **University Campus:** Structured, moderately dynamic indoor space .
* **Edge-Oriented:** Focused on lightweight RSS fingerprints, ideal for deploying TinyML algorithms on resource-constrained microcontrollers.

## 📂 Dataset Structure & Description

The dataset is organized into two primary scenarios: **Airport** (Large-scale, dynamic) and **Campus** (Structured, moderate). Each scenario folder contains a reference Fingerprint Database and multiple Evaluation Sets collected over time.

### 📁 `Airport/` and 📁 `Campus/`
Inside each scenario directory, the data hierarchy is categorized as follows:

#### 1. `Fingerprint_Database/` (Reference Data)
This directory contains the training data used to construct the radio map. We provide three versions of the data to facilitate benchmarking of different preprocessing techniques:

* 📄 **`OriginData/`**: The raw, unprocessed Wi-Fi RSS fingerprints as captured by the edge devices.
* 📄 **`After_Traditional_Process/`**: RSS data processed using standard filtering methods (e.g., Gaussian filtering or Mean filtering) to mitigate multipath effects and noise.
* 📄 **`After_Score_Process/`**: Data processed via our proposed **Score Mechanism**. This version optimizes the fingerprints by evaluating signal stability and AP importance, specifically designed to improve localization robustness in dynamic environments.

#### 2. Temporal Evaluation Sets (Test Data)
These directories are used to evaluate the model's performance and its ability to handle temporal drift:

* 📄 **`Init/`**: Data collected immediately after the completion of the Fingerprint Database. Represents the "best-case" scenario with minimal environmental change.
* 📄 **`Month_1/` to `Month_X/`**: Longitudinal data collected periodically. 
    * The **Airport** scenario includes 5 months of data (`Month_1` to `Month_5`).
    * The **Campus** scenario includes 2 months of data (`Month_1` to `Month_2`).
    * *Purpose:* These sets allow researchers to test how localization accuracy degrades over time and how well models (like our HubEdgeLoc) adapt to long-term signal fluctuations.
