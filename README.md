# ❤️ AI for Healthcare: Motion-Compensated Pulse Rate Estimation

### Healthcare AI • Signal Processing • Wearable Sensors • Physiological Monitoring • Uncertainty Estimation

![Python](https://img.shields.io/badge/Python-Signal_Processing-blue?style=for-the-badge\&logo=python\&logoColor=white)
![Healthcare](https://img.shields.io/badge/Healthcare-Wearable_AI-green?style=for-the-badge)
![DSP](https://img.shields.io/badge/DSP-Pulse_Rate_Analysis-purple?style=for-the-badge)
![NumPy](https://img.shields.io/badge/NumPy-Scientific_Computing-orange?style=for-the-badge)
![Physiology](https://img.shields.io/badge/Physiology-Heart_Rate-red?style=for-the-badge)

---

# Overview

This project investigates how wearable sensor data can be used to estimate pulse rate during physical activity.

The challenge is that movement introduces substantial noise into physiological measurements, making accurate pulse estimation difficult.

To address this problem, a signal processing pipeline was developed that combines:

* Photoplethysmography (PPG)
* Accelerometer measurements
* Frequency-domain analysis
* Motion artifact suppression
* Confidence estimation

The final system produces pulse-rate estimates together with an associated confidence score.

---

# Clinical Motivation

Wearable devices are increasingly used for:

* Fitness monitoring
* Remote patient monitoring
* Cardiac observation
* Telemedicine applications

However, motion introduces artifacts that can obscure the true pulse signal.

A robust pulse-rate estimation algorithm must therefore distinguish between:

```text
Heart Activity
```

and

```text
Motion Artifacts
```

while maintaining reliable performance.

---

# Project Objectives

Develop an algorithm capable of:

1. Extracting pulse rate from PPG signals.
2. Removing motion-induced noise.
3. Producing estimates every few seconds.
4. Quantifying confidence in predictions.
5. Maintaining acceptable accuracy during exercise.

---

# Dataset

The project uses the Troika dataset, a benchmark dataset commonly used for evaluating pulse-rate estimation algorithms.

The dataset contains synchronized measurements from wearable sensors including:

## Photoplethysmography (PPG)

Optical measurements used to estimate blood volume changes.

## Accelerometers

Three-axis motion measurements used to identify movement artifacts.

## Ground Truth Heart Rate

Reference measurements used for evaluation.

---

# Physiological Background

Each heartbeat generates a pulse wave that propagates through the vascular system.

PPG sensors estimate this activity by measuring changes in reflected light caused by blood flow.

Simplified process:

```text
Heartbeat
     │
     ▼
Blood Volume Change
     │
     ▼
Optical Signal Variation
     │
     ▼
PPG Measurement
```

The dominant frequency in the PPG signal is closely related to heart rate.

---

# Challenge: Motion Artifacts

Physical activity introduces noise that overlaps with cardiac frequencies.

Examples include:

* Running
* Walking
* Arm movement
* Device displacement

Without compensation, motion can easily dominate the measured signal.

---

# Signal Processing Pipeline

```text
Raw PPG Signal
        │
        ▼
Bandpass Filtering
        │
        ▼
Frequency Analysis
        │
        ▼
Motion Artifact Detection
        │
        ▼
Accelerometer Comparison
        │
        ▼
Pulse Frequency Selection
        │
        ▼
Heart Rate Estimate
        │
        ▼
Confidence Score
```

---

# Signal Preprocessing

## Bandpass Filtering

Both PPG and accelerometer signals were filtered to isolate physiologically relevant frequencies.

Benefits include:

* Noise reduction
* Improved peak detection
* Better frequency estimation

---

## Accelerometer Aggregation

Accelerometer channels were combined into a meaningful motion signal.

This allows the algorithm to identify frequencies caused by movement rather than cardiac activity.

---

# Pulse Rate Estimation

The algorithm analyzes the frequency content of the filtered signals.

Key steps include:

1. Transform signals into the frequency domain.
2. Identify candidate pulse frequencies.
3. Compare candidate peaks against motion frequencies.
4. Select the most likely cardiac frequency.
5. Convert frequency into beats per minute (BPM).

---

# Confidence Estimation

A confidence score accompanies each pulse-rate estimate.

Higher confidence generally occurs when:

* One dominant cardiac peak exists
* Motion contamination is low
* Frequency peaks remain stable over time

Lower confidence occurs when:

* Multiple competing peaks exist
* Motion frequencies overlap with cardiac frequencies
* Signal quality degrades

This confidence measure can be used to reject unreliable estimates.

---

# Performance Evaluation

Performance was measured using:

## Mean Absolute Error (MAE)

```text
Predicted BPM
        vs
Reference BPM
```

The project achieved:

* Mean Absolute Error below the required threshold
* Greater than 90% estimate availability

These results demonstrate reliable pulse-rate estimation during movement.

---

# Algorithm Validation

Evaluation included:

* Matching predictions to reference measurements
* Computing absolute error
* Estimating overall availability
* Assessing confidence calibration

Performance was analyzed across multiple subjects and activity levels.

---

# Clinical Interpretation

The project also explored broader physiological questions including:

* Differences in resting heart rate
* Variability across participants
* Sources of measurement uncertainty
* Limitations of wearable monitoring

These observations provide context for understanding how wearable devices perform in real-world settings.

---

# Limitations

Several limitations remain:

* Motion artifacts can overlap with cardiac frequencies.
* Performance may degrade during intense activity.
* Wearable placement affects signal quality.
* The dataset may not represent all populations.

Future work could incorporate:

* Deep learning approaches
* Sensor fusion with additional modalities
* Adaptive filtering techniques
* Larger validation datasets

---

# Skills Demonstrated

## Healthcare AI

* Physiological signal analysis
* Wearable health monitoring
* Clinical performance evaluation

## Signal Processing

* Bandpass filtering
* Frequency-domain analysis
* Noise suppression
* Spectral peak detection

## Machine Learning Foundations

* Confidence estimation
* Performance evaluation
* Error analysis

## Scientific Computing

* NumPy
* Signal processing pipelines
* Data visualization
* Reproducible analysis

---

# Key Deliverables

* Pulse-rate estimation algorithm
* Motion compensation pipeline
* Confidence scoring system
* Signal processing analysis
* Clinical interpretation report
* Algorithm performance evaluation

---

# Educational Context

This project was completed as part of the AI for Healthcare Nanodegree.

It demonstrates how signal processing techniques can be applied to physiological sensor data to produce reliable health measurements under realistic conditions involving human movement.

---

## Author

S. Palis

AI Systems • Healthcare AI • Biomedical Signal Processing • Wearable Health Technologies
