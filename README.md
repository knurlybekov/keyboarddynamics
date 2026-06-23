# keyboarddynamics

Behavioral-biometric **bot detection from keystroke dynamics**, with a focus on rigorous, leakage-free evaluation and adversarial robustness.

## Overview

A complete keystroke-dynamics pipeline that classifies typing sessions (human vs. bot) using hold-time and flight-time rhythm. The emphasis is methodological: a participant-level 4-way split that prevents bot-calibration leakage and supports probability calibration.

## Key Concepts

- **VK** — virtual key code; **HT** — hold time (key dwell, ms); **FT** — flight time (inter-key gap, ms)
- **Feature group** — 7 burst-pause segmentation features per session
- **4-way participant split** — avoids leakage between model training, bot template generation, and calibration

## Pipeline

1. Exploratory data analysis (HT/FT distributions across five sub-datasets)
2. Participant-level data architecture & 4-way split
3. Burst-pause feature engineering
4. Model training + isotonic probability calibration
5. Adversarial / production-grade evaluation
6. Ensemble fusion (`ensamble_fusion.ipynb`)

## Tech Stack

Python · scikit-learn · pandas · NumPy · Jupyter

## Usage

```bash
pip install scikit-learn pandas numpy jupyter
jupyter notebook keystroke_dynamics_master.ipynb
```

A research proposal PDF accompanies the notebooks.
