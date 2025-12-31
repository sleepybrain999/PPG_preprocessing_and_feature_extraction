# PPG Morphological Feature Extraction

This project implements a pipeline to preprocess raw **Photoplethysmogram (PPG)** signals and extract segment morphological features. These features are commonly used in cardiovascular monitoring and blood pressure estimation research.

## 📋 Features Extracted

The pipeline segments the PPG signal into 8s segment and calculates the following features for each:

| Feature | Description |
| --- | --- |
| **IBI (mean)** | Inter-Beat Interval (Time between successive onsets) |
| **AMP (mean)** | Pulse Amplitude (Foot-to-systolic-peak height) |
| **ST (mean)** | Systolic Time (Rise time from onset to peak) |
| **DT (mean)** | Diastolic Time (Fall time from peak to end of beat) |
| **Width50 (mean)** | Pulse width measured at 50% of the amplitude |
| **Width66 (mean)** | Pulse width measured at 66% of the amplitude |


## 🛠️ Data Pipeline

1. **Preprocessing:** Basic filtering (Bandpass 0.5 - 8.0 Hz) and baseline wandering removal.
2. **Segmentation:** Segment data into 8-second segments.
3. **Detection:** Detection of pulse onsets (feet) and systolic peaks.
4. **Feature Extraction:** Calculation of timing and width-based morphological markers per beat. Then, the **mean** is calculated at the segment level.
5. **Data Structuring:** Organization of features into a subject-level list of segment-level lists of dictionaries and conversion to Pandas DataFrames for analysis.

### Prerequisites

Install the required packages:

```bash
pip install -r requirements.txt

