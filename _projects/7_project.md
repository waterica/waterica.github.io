---
layout: page
title: Predicting Finger Flexion from Electrocorticography (ECoG) Using Gradient Boosted Regression
description: Final project for BE 5210 Brain Computer Interfaces (Penn, Spring 2023)
img: assets/img/Dynamic_Grab_Location.PNG
importance: 10
category: School
related_publications:
---

**Description:** This project explored the development of a machine learning pipeline to decode continuous finger flexion from ECoG signals recorded from epilepsy patients with implanted subdural electrode arrays. I worked with a team of 2 other students to implement a feature-rich preprocessing strategy—including time-domain metrics and frequency band power estimates—within sliding windows of filtered ECoG data. Inspired by Warland et al., we constructed a temporally embedded feature matrix and replaced their linear decoding method with gradient boosting regression. While our final model achieved moderate correlation (maximum 0.43) with glove-measured ground truth, this work provided hands-on experience in neural signal preprocessing, feature engineering, and time-series regression modeling for BCI applications.

**Role:** Designed preprocessing and feature extraction pipeline, implemented regression model, and evaluated decoding performance


**Language:** Python (numpy, scipy, scikit-learn)

**Key Competencies:** Neural signal preprocessing, feature extraction, gradient boosting regression, ECoG decoding, time series interpolation

**Project Images:**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/finger_flexion.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Predicted finger flexion for all five fingers of participant 1.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/PSD_30.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example power spectral density analysis of participants for two 0.3s windows starting at 0s and 2s from a single ECoG channel. Frequency bands are marked in gray.
</div>