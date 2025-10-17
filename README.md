# An Evaluation of Motor Activity Time Segmentation Approaches for Depression Classification Using Machine Learning

This repository contains the scripts used for all processes and experiments developed for the manuscript: An Evaluation of Motor Activity Time Segmentation Approaches for Depression Classification Using Machine Learning

## Overview

Depression is a prevalent mental health condition that significantly impacts daily functioning. This project investigates the use of motor activity patterns, captured through actigraphy data, to classify depression episodes in patients with unipolar and bipolar disorders. We compare multiple time segmentation approaches to identify which temporal granularity provides the most informative features for machine learning models.

## Dataset

This project uses the **Depresjon Dataset**, a publicly available motor activity database of depression episodes in unipolar and bipolar patients.

**Dataset URL:** https://datasets.simula.no/depresjon/

### Citation

If you use this dataset or code, please cite the original dataset paper:

```bibtex
@inproceedings{Garcia:2018:NBP:3083187.3083216,
    title = {Depresjon: A Motor Activity Database of Depression Episodes in Unipolar and Bipolar Patients},
    author = {
        Enrique Garcia-Ceja and Michael Riegler and Petter Jakobsen and
        Jim T\o rresen and Tine Nordgreen and Ketil J. Oedegaard and
        Ole Bernt Fasmer
    },
    booktitle = {Proceedings of the 9th ACM on Multimedia Systems Conference},
    series = {MMSys'18},
    year = {2018},
    location = {Amsterdam, The Netherlands},
    url = {http://doi.acm.org/10.1145/3204949.3208125},
    doi = {10.1145/3204949.3208125},
    acmid = {3208125},
    publisher = {ACM},
    address = {New York, NY, USA}
}
```

### Dataset Description

The dataset includes:
- Motor activity measurements from actigraphy sensors
- Clinical scores (MADRS - Montgomery-Åsberg Depression Rating Scale)
- Patient demographic and clinical information
- Data from both unipolar and bipolar depression patients

## Repository Structure

```
├── adjustment/             # Data preprocessing and adjustment procedures
├── new_joint/              # Joint analysis combining multiple segmentation approaches
├── finalExperiments/       # Final experimental results and model evaluations

```

## Segmentation Approaches

This project explores different temporal segmentation strategies:

1. **Full Day Segmentation**: Aggregates motor activity features across the entire 24-hour period
   - Provides overall daily activity patterns
   - Single feature set per day

2. **Double Segmentation**: Splits the day into 2 distinct time periods
   - Captures day/night or morning/evening patterns
   - Enables modeling of circadian rhythm variations

3. **Triple Segmentation**: Divides the day into 3 time periods
   - Finer temporal granularity (e.g., morning/afternoon/evening)
   - More detailed circadian pattern representation

## Features

Each segmentation approach extracts the following activity metrics:
- **Total activity**: Sum of activity counts
- **Mean activity**: Average activity level
- **Standard deviation**: Activity variability
- **Max/Min activity**: Activity range
- **Median activity**: Central tendency measure
- **Inactivity percentage**: Proportion of inactive periods
- **Non-zero count**: Number of active measurement periods

## Requirements

```
Python >= 3.7
pandas
numpy
scikit-learn
matplotlib
seaborn
```

## Usage

### Data Preprocessing
```bash
cd adjustment/
cd new_joint/
# Run preprocessing scripts
```

### Running Experiments
```bash
cd finalExperiments/
# Run experimental scripts for each segmentation approach
```

## Methodology

1. **Data Collection**: Motor activity data collected via actigraphy sensors
2. **Segmentation**: Time-based segmentation into full-day, 2-segment, and 3-segment approaches
3. **Feature Extraction**: Statistical features computed for each segment
4. **Classification**: Machine learning models trained to predict depression status
5. **Evaluation**: Comparative analysis of segmentation approaches

## Results

Detailed experimental results and model performance comparisons can be found in the `finalExperiments/` directory.

## Acknowledgments

We gratefully acknowledge the contributors of the Depresjon dataset for making this research possible. The original data collection and curation was conducted by researchers at the University of Oslo, Diakonhjemmet Hospital, and Simula Research Laboratory.

## License

Please refer to the original dataset license at https://datasets.simula.no/depresjon/ for data usage terms and conditions.

## Contact

For questions or collaborations, please open an issue in this repository.
