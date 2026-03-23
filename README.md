# End-to-End Data Pipeline for Mixed-Signal Processing and Correction

An end-to-end data pipeline for transforming fragmented spectrometer outputs into standardized, analysis-ready datasets, with reconstruction, cross-environment transfer, signal extraction, correction logic, and before/after validation integrated into a single workflow.

Although the project was developed using spectrometer-based multi-signal data, its main technical contribution lies in structured data processing, workflow standardization, and reusable analysis pipeline design.

## Technical Challenges

Raw signal-processing workflows often produce fragmented, environment-dependent outputs that are difficult to standardize, compare, and interpret consistently.

This project addresses those issues by building a connected workflow that:

- standardizes fragmented raw outputs into continuous session-level datasets
- transfers structured MATLAB outputs into a Python-compatible analysis format
- extracts comparable signals from predefined wavelength ranges
- identifies and validates cross-range signal contamination
- applies a structured correction model to reduce mixed-signal interference
- compares system outputs before and after correction
- reuses the same workflow on a different sensor pair

## Pipeline Architecture

### 01. Acquisition architecture
Designed a synchronized acquisition layer for spectral recording, event logging, and structured raw-data output.

### 02. Raw reconstruction and standardization
Reconstructed fragmented acquisition outputs into continuous session-level datasets.

### 03. MATLAB-to-Python interface
Built a reusable transfer layer between MATLAB-generated datasets and Python-based analysis.

### 04. Dual-color measurement risk analysis
Analyzed spectral overlap and excitation-dependent instability before simultaneous interpretation.

### 05. Signal quantification strategy
Defined range-based signal extraction from full-spectrum recordings.

### 06. Signal independence validation
Validated asymmetric cross-range contamination between green and red measurement ranges.

### 07. Real-time correction algorithm
Defined and validated the `fixpeaksegment` spectral template used for correction.

### 08. Uncorrected dual-injection analysis
Established the uncorrected baseline in the mixed recording condition.

### 09. Corrected dual-injection analysis
Evaluated corrected output relative to the uncorrected baseline.

### 10. Workflow extension to a second sensor pair
Applied the same workflow to a different neurotransmitter-sensor pair to test reusability.

## Core technical contributions

- Designed a multi-stage processing pipeline from raw acquisition output to corrected analytical output
- Standardized fragmented and environment-dependent data into reusable session-level datasets
- Connected MATLAB-based preprocessing with Python-based downstream analysis
- Built a consistent signal-extraction strategy from full-spectrum measurements
- Defined and validated a correction model for mixed-signal contamination
- Evaluated algorithm impact through direct before/after comparison
- Demonstrated workflow transferability beyond the original validation dataset

## Validation & Results

Using a representative green/red sensor pair, the workflow identified directionally biased contamination between measurement ranges, defined a reproducible spectral correction template, and evaluated the effect of correction in mixed recordings. A final extension to a second sensor pair showed that the same pipeline could be reused without redesigning the overall analysis structure.

## Technical Significance & Impact

This project frames mixed spectral data as a processing, standardization, and correction problem rather than as a simple measurement task. The main value lies in:

- converting complex raw outputs into structured datasets
- reducing dependence on manual interpretation
- building reusable logic across analysis environments
- defining correction steps from validated signal behavior
- supporting consistent comparison across recording conditions

## Recommended reading order

For the full workflow, read the notebooks in numerical order.

For the shortest path to the main technical contribution, start with:

- `06_signal_independence_validation`
- `07_real_time_correction_algorithm`
- `08_uncorrected_dual_injection_analysis`
- `09_corrected_dual_injection_analysis`
