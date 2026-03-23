# Spectral Data Pipeline for Multi-Signal Recording and Real-Time Correction

A full signal-processing workflow for converting raw spectrometer recordings into analysis-ready multi-signal datasets, with reconstruction, MATLAB-to-Python transfer, contamination validation, spectral correction, and before/after evaluation built into a single pipeline.

Originally developed in the context of neural recording data, the main technical focus of this project is structured data reconstruction, range-based signal extraction, correction of mixed spectral signals, and reusable workflow design across multiple recording conditions.

## What this project does

Multi-signal recording data is difficult to interpret when signals overlap across wavelength ranges, raw outputs are fragmented, and downstream analysis depends on environment-specific formats. This project addresses that problem by building an end-to-end workflow that transforms raw spectrometer outputs into standardized datasets and applies a validated correction strategy to improve mixed-signal interpretation.

The workflow:

- Preserves full-spectrum measurements during acquisition
- Reconstructs fragmented raw outputs into continuous session-level datasets
- Transfers structured MATLAB outputs into a Python-compatible analysis format
- Extracts signals from predefined wavelength ranges rather than single-point values
- Validates asymmetric crosstalk between channels
- Defines a spectrally structured correction template for real-time use
- Compares mixed recordings before and after correction
- Tests workflow reuse on a different neurotransmitter-sensor pair

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

This project treats mixed spectral recording as a data-processing and signal-isolation problem rather than as a simple two-channel measurement task. Reliable interpretation required:

- Full-spectrum acquisition instead of fixed-channel assumption
- Reconstruction and standardization of fragmented raw outputs
- Reusable transfer between MATLAB and Python environments
- Range-based signal quantification from defined wavelength intervals
- Empirical validation of contamination directionality
- A correction model that preserves local spectral structure
- Before/after evaluation of algorithmic impact in mixed recordings

## Main result

Using GCaMP6f and jRGECO1a as a validation pair, the workflow identifies directionally biased contamination from the green-associated signal into the red measurement range, defines a reproducible spectral correction template, and evaluates the effect of correction in mixed dual-injection recordings. The final application to dopamine/serotonin data supports reuse of the same workflow beyond the original validation pair.

## Recommended reading order

For the full workflow, read the notebooks in numerical order.

For the shortest path to the main technical contribution, start with:

- `06_signal_independence_validation`
- `07_real_time_correction_algorithm`
- `08_uncorrected_dual_injection_analysis`
- `09_corrected_dual_injection_analysis`
