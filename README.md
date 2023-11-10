# Anomaly Detection Project Summary

## Introduction to the Problem
The project addresses an unsupervised Anomaly Detection problem, specifically identifying anomalies in a welding process within an FCA (Fiat Chrysler Automobiles) facility. Real-time data from the Weld Quality System (WQS) was collected, generating welding curves stored in a file system.

Two approaches were employed: a statistical approach and an unsupervised learning approach.

## Statistical Approach
### Structural Anomalies
Structural anomalies refer to abnormal peaks or drops compared to the overall trend of curves. Differential analysis of voltage values was chosen to identify structural anomalies.

### Construction of Control Bands
Two types of intervals were constructed for defining inliers and outliers:
1. μ ± 3σ (based on normal distribution)
2. 𝑄0.1 + 1.5𝐼𝑄𝑅, 𝑄3 + 1.5𝐼𝑄𝑅 (based on quantile distribution)

To ensure a wide safety margin for structural anomaly identification, outliers were defined beyond μ ± 4σ.

### Examples of Identified Anomalies
- Anomalous Drops: 19% of data
- Anomalous Peaks: 1% of data
- Concurrent Anomalies: 0.5% of data

### Voltage Anomaly Classification
Anomaly classification based on percentage of anomalies:
- Blue: Non-anomalous (anomaly percentage < 10%)
- Orange: Anomalous (10-40% anomaly percentage)
- Red: Highly anomalous (>40% anomaly percentage)

## Machine Learning
### Data Preparation
Values before the first change in curve slope were removed to avoid influencing algorithm behavior.

### Application of Algorithms
Two algorithms chosen for Outlier Detection: Isolation Forest and Local Outlier Factor.

- **Isolation Forest**: Identifies outliers based on their shorter paths in random partitioning.
- **Local Outlier Factor (LOF)**: Assigns a score based on the local density ratio, identifying isolated instances.

