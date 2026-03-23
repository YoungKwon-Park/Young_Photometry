# Real-Time Spectral Unmixing Workflow for Dual-Color Fiber Photometry

A spectrometer-based workflow for dual-color photometry that covers acquisition design, raw-data reconstruction, MATLAB-to-Python transfer, spectral risk analysis, range-based signal quantification, contamination validation, real-time correction-algorithm design, before/after correction evaluation, and extension to dopamine/serotonin sensors.

## What this project does

Simultaneous measurement of multiple neural signals is difficult when fluorescence signals overlap across wavelength ranges. This project addresses that problem by building a full workflow for spectrometer-based dual-color photometry, from synchronized acquisition to corrected signal interpretation.

Instead of assuming that green and red channels are automatically separated, the workflow:

- preserves full-spectrum measurements in real time
- reconstructs fragmented acquisition outputs into standardized datasets
- quantifies signals from predefined wavelength ranges
- validates asymmetric contamination between sensor ranges
- defines a spectrally structured correction template for real-time use
- compares mixed recordings before and after correction
- extends the same workflow to dopamine/serotonin sensor data

## Workflow structure

### 01. Acquisition architecture
Design of the synchronized acquisition layer for spectral recording, event logging, and structured raw-data output.

### 02. Raw reconstruction and standardization
Reconstruction of fragmented acquisition outputs into continuous session-level datasets.

### 03. MATLAB-to-Python interface
Conversion of standardized MATLAB outputs into a Python-compatible analysis structure.

### 04. Dual-color measurement risk analysis
Evaluation of spectral overlap and excitation-dependent signal instability before simultaneous interpretation.

### 05. Signal quantification strategy
Definition of range-based fluorescence quantification from full-spectrum recordings.

### 06. Signal independence validation
Single-sensor validation showing asymmetric contamination between green and red measurement ranges.

### 07. Real-time correction algorithm
Definition and validation of the `fixpeaksegment` spectral template used for correction.

### 08. Uncorrected dual-injection analysis
Establishment of the uncorrected baseline in the mixed dual-injection condition.

### 09. Corrected dual-injection analysis
Evaluation of corrected output relative to the uncorrected baseline.

### 10. Extension to dopamine/serotonin
Application of the same workflow to a different neurotransmitter-sensor pair.

## Core technical message

The workflow shows that dual-color photometry should not be treated as a simple two-channel recording problem. Reliable interpretation requires:

- full-spectrum measurement rather than fixed-channel assumption
- structured reconstruction and standardization of raw outputs
- range-based quantification instead of single-point extraction
- validation of contamination directionality
- a correction model that preserves local spectral structure
- evaluation of mixed signals before and after correction

## Main result

Using GCaMP6f and jRGECO1a as a validation pair, the workflow identifies directionally biased contamination from the green sensor into the red measurement range, defines a reproducible spectral correction template, and evaluates the effect of correction in dual-injection recordings. The final extension to dopamine/serotonin data supports the reuse of the same workflow beyond the original validation pair.

## Recommended reading order

For the full workflow, read the notebooks in numerical order.

For the shortest path to the main technical contribution, start with:

- `06_signal_independence_validation`
- `07_real_time_correction_algorithm`
- `08_uncorrected_dual_injection_analysis`
- `09_corrected_dual_injection_analysis`
