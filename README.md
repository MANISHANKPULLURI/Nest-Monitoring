# Nest-Monitoring

---

# **Bird Nest Monitoring System**

A classical computer vision pipeline for automated monitoring of bird nest activity from forest-recorded surveillance videos.

---

## **Overview**

This project implements a fully automated system for analyzing bird visitation patterns at nest sites using lightweight, motion-based computer vision techniques. The system processes raw forest surveillance footage to detect arrival/departure events and extract key behavioral metrics such as visit frequency, visit duration, inter-visit intervals, lighting-condition trends, and nest activity rankings—supporting habitat quality assessment and conservation research.

---

## **Key Features**

* Automated video processing tailored for forest-recorded nest footage
* ROI-based frame extraction and motion-driven event detection
* Classical CV pipeline (bilateral filtering, CLAHE, Canny edges, frame differencing)
* Temporal smoothing to suppress wind-induced vegetation motion
* Extraction of detailed behavioral and temporal activity metrics
* Ground-truth validation study with documented methodology
* 18+ publication-quality visualizations and interactive dashboards
* Cross-nest comparative analysis for ecological insight

---

## **Technical Implementation**

### **1. Preprocessing Pipeline**

The system uses a multi-step classical CV workflow designed for efficient, low-compute operation in field environments:

* **Bilateral Filtering:** Noise reduction while preserving structural edges
* **CLAHE:** Lighting normalization across varying forest conditions (shadow, sunlight, overcast)
* **Canny Edge Detection:** Structural feature extraction using dual thresholds (30, 100)
* **Frame Differencing:** Pixel-level temporal motion detection
* **Temporal Smoothing:** 5-frame rolling window to reduce environmental noise

---

### **2. Motion-Based Event Detection**

* A motion threshold of **0.08** was determined experimentally.
* Consecutive frames exceeding the threshold form a **visit event**.
* Arrival and departure times are inferred from the start and end of high-motion segments.
* Event grouping prevents double-counting during prolonged movement.

---

## **Behavioral Metrics Extracted**

* Visit frequency per nest
* Visit duration (mean, median, range)
* Inter-visit intervals
* Lighting condition classification (DARK / DIM / BRIGHT)
* Hourly and daily activity patterns
* Motion intensity profiles during visits
* Ranked nest activity for comparative analysis

---

## **Dataset Summary**

* Nest surveillance videos recorded directly in the forest
* Multiple lighting and weather conditions
* 17,724 frames processed across all recordings
* Consistent frame structure supporting cross-video comparison

---

## **Validation Study**

A manual ground-truth evaluation was conducted:

* 50 randomly sampled high-motion frames inspected by hand
* Transparent breakdown provided (true/false positives, uncertain cases)
* A correction-factor methodology was developed to adjust estimated visit counts
* Relative comparisons across nests remain statistically meaningful

---

## **Ecological Insights**

* Top active nests identified based on visit frequency
* Mean visit duration: **2.5 minutes** (median 1.8 minutes)
* Mean inter-visit interval: **15.3 minutes**
* Peak visitation hours visualized
* Lighting–behavior correlations observed
* Nest quality ranking for habitat assessment

---

## **Visualizations & Outputs**

The system generates over **18 publication-quality visualizations**, including:

* Visit duration distributions
* Inter-nest comparisons
* Lighting condition boxplots
* Motion score timelines
* Brightness–behavior scatter plots
* Visit timeline (Gantt-style) charts
* Full analytical dashboard

---

## **Video Results**

Video comparisons (original footage, edge detection, motion scores, lighting analysis, and event overlays) are available in the following folder:

[Video Results and Analysis](https://drive.google.com/drive/folders/16huNhyP5sGi6GXbrDW5xMpv7_ZzZECEH?usp=drive_link)

---

## ** Tech stack Used**

* OpenCV
* NumPy / pandas
* matplotlib / seaborn
* pillow
* scipy



