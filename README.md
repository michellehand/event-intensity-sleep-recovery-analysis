# 🎧 Rave Health Analytics: Modeling Sleep, Recovery, and Experience

## Overview

This project explores how different aspects of rave experiences—such as intensity, substance use, and environment—impact next-day sleep, recovery time, and overall experience quality.

Using a self-collected dataset of events and wearable health metrics, the goal is to answer:

> **What are the tradeoffs between how hard I go and how I feel after?**

---

## Dataset

The dataset combines:

**Event-level inputs**
- Event type (festival, venue, warehouse)
- Crowd size and density
- Visual intensity
- Substance use and dosage
- Embodiment (subjective presence)
- Energy before the event
- Outfit expression level

**Health and recovery metrics**
- Sleep score (baseline and post-event)
- HRV status (converted to numeric score)
- Recovery time (days to return to baseline)

**Derived features**
- `intensity_score`
- `rave_sleep_drop_from_baseline`
- `days_to_recover_sleep`
- `high_value_night`

---

## Key Metrics

### Intensity Score
A weighted composite of:
- visual intensity  
- substance intensity  
- embodiment  
- energy before  
- crowd size  
- density  
- outfit expression  

This captures overall experience intensity in a single variable.

---

### Sleep Metrics
- `sleep_baseline` → sleep before event  
- `sleep_plus1` → sleep after event  
- `rave_sleep_drop_from_baseline` → change due to event  

---

### Recovery
- `days_to_recover_sleep` → days until sleep returns to baseline  

---

### Experience Quality
- `high_value_night` defined as:
  - embodiment ≥ 9  
  - recovery ≤ 1 day  

---

## Methodology

### Validation Strategy

Because the dataset is small (~12–16 observations),  
**leave-one-out cross-validation (LOOCV)** was used.

This:
- maximizes training data  
- evaluates every observation out-of-sample  
- avoids unreliable train/test splits  

---

### Models

**Regression**
- Linear Regression (interpretable baseline)
- Random Forest (nonlinear comparison)

**Classification**
- Logistic Regression
- Random Forest Classifier

---

### Metrics

- Regression → Mean Absolute Error (MAE)  
- Classification → Accuracy  

---

## Results

### Sleep After Rave

| Model | MAE |
|------|-----|
| Linear Regression | 11.31 |
| Random Forest | 11.02 |

---

### Sleep Impact (Drop from Baseline)

| Model | MAE |
|------|-----|
| Linear Regression | 11.31 |
| Random Forest | 11.04 |

---

### Recovery Time

| Model | MAE |
|------|-----|
| Linear Regression | 0.73 |
| Random Forest | 0.77 |

---

## Key Findings

### 1. Intensity drives sleep disruption

Higher intensity events are strongly associated with worse next-day sleep.

- R² ≈ 0.76  
- ~0.87 drop in sleep score per intensity point  

---

### 2. Substance use drives recovery

Higher substance intensity is associated with longer recovery time.

- ~0.12 additional recovery days per unit  

---

### 3. Sleep and recovery follow a chain
