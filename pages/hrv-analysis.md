# HRV Analysis Overview

*Note:* For inquiries, please visit the [NSRR Forum](https://sleepdata.org/forum).

## Methods

QRS complexes (R-points) were detected using Compumedics (Abbotsford, VIC, Australia) Somte software Version 2.10 (Builds 99 to 101). The R-points were classified as normal sinus, supraventricular premature complex or ventricular premature complex. The automated annotations were reviewed by a trained technician, who made appropriate corrections.

In this analysis, we follow the Task Force of The European Society of Cardiology and The North American Society of Pacing and Electrophysiology, Heart rate variability (HRV) standards of measurement, physiological interpretation, and clinical use (European Heart Journal, 1996;17:354–81).

Traditional heart rate variability (HRV) measures are commonly divided into two broad categories: time domain measures and frequency domain measures.

Other analysis notes:

- Individuals with less than 1,000 normal-to-normal (NN) intervals and/or less than two hours of combined sleep stages REM, N1, N2, N3 and N4 were excluded.
- Sleep onset was defined as the start time of the first non-awake period longer than 90-seconds. Similarly, sleep termination was defined as the end time of the last non-awake period longer than 90-second.
- NN intervals < 0.35 sec or > 2.5 were excluded.
- 5-min windows with less than 180 NN intervals were excluded.
- Two sets of HRV analyses were performed: 1) the full night was analyzed as a single period; 2) the analysis was performed in non-overlapping 5-minute windows and the resulting values were averaged.

The time domain HRV statistics include the following measures:

- **NN_RR** (ratio of consecutive normal sinus beats (NN) over all cardiac inter-beat (RR) intervals)
- **AVNN** (average of all NN intervals)
- **IHR** (average instantaneous heart rate. For a given NN interval, the IHR is calculated as 60/NN. IHR is usually expressed as beats per minute but strictly speaking it is unitless.)
- **SDNN** (the standard deviation of all NN intervals)
- **SDANN** (the standard deviation of the averages of NN intervals in all 5-minute segments)
- **SDNNINDX** (the mean of the standard deviations of NN intervals in all 5-minute segments)
- **rMSSD** (the square root of the mean of the squares of difference between adjacent NN intervals), and
- **pNNx** (the percentage of differences between adjacent NN intervals that are > x ms). We used x = 10, 20, 30, 40 and 50 ms.

The frequency domain measures include:

- **TOTPWR** (total NN interval spectral power up to 0.4 Hz)
- **ULF** (ultra-low frequency power: the NN interval spectral power between 0 and 0.003 Hz of a 24-hour recording)
- **VLF** (very low frequency power: the NN interval spectral power between 0.003 and 0.04 Hz)
- **LF** (low frequency power: the NN interval spectral power between 0.04 and 0.15 Hz)
- **HF** (high frequency power: the NN interval spectral power between 0.15 and 0.4 Hz)
- **LF/HF ratio** (the ratio of low to high frequency power)
- **HFn** (normalized HF, ratio HF/(HF+LF))
- **LFn** (normalized LF, ratio LF/(HF+LF))

Traditionally frequency domain measures are calculated by resampling the original NN interval series and then applying the fast Fourier transform. This resampling, however, can cause an attenuation in the high frequency components. To eliminate the need for evenly sampled data required by the standard Fourier Transform, frequency domain spectra can be calculated using the Lomb periodogram for unevenly sampled data.

Although the long term (24-hour) statistics of SDANN, SDNNIDX and ULF power can be calculated for shorter data lengths they will become increasingly unreliable. For short term data (less than 15 minutes in length) only the time domain measures of AVNN, SDNN, rMSSD and pNN10, pNN20, pNN30, pNN40 and pNN50, and the frequency domain measures of total power, VLF power, LF power, HF power and LF/HF ratio are computed.

## Dataset structure

Results have been posted for HRV analysis in the [primary MESA Sleep dataset](:files_path:/datasets). Datasets are keyed on `mesaid`.

## R-point annotations

[Individual CSV files are available with R-points](:files_path:/polysomnography/annotations-rpoints) for each heartbeat. These annotations were reviewed by a trained technician after exporting from the Compumedics Somte software. ECG was sampled at 256 Hz.

| Name                                | Label (with Units / Notes)                                                                                                                                                            |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `epoch`                             | Epoch (30 second) number                                                                                                                                                              |
| `RPoint`                            | Sample Number indicating R Point (peak of QRS)                                                                                                                                        |
| `Start`                             | Sample Number indicating start of beat                                                                                                                                                |
| `End`                               | Sample Number indicating end of beat                                                                                                                                                  |
| `STLevel1`                          | Level of ECG 1 in Raw data ( 65536 peak to peak rawdata = 10mV peak to peak)                                                                                                          |
| `STSlope1`                          | Slope of ECG 1 stored as and int to convert to a double divide raw value by 1000.0                                                                                                    |
| `STLevel2`                          | Level of ECG 2 in Raw data ( 65536 peak to peak rawdata = 10mV peak to peak)                                                                                                          |
| `STSlope2`                          | Slope of ECG 2 stored as and int to convert to a double divide raw value by 1000.0                                                                                                    |
| `Manual`                            | (True / False) True if record was manually inserted                                                                                                                                   |
| `Type`                              | Type of beat (0 = Artifact / 1 = Normal Sinus Beat / 2 = VE / 3 = SVE)                                                                                                                |
| `Class`                             | This Field is no longer used                                                                                                                                                          |
| `PPoint`                            | Sample Number indicating peak of the P wave (-1 if no P wave detected)                                                                                                                |
| `PStart`                            | Sample Number indicating start of the P wave                                                                                                                                          |
| `PEnd`                              | Sample Number indicating end of the P wave                                                                                                                                            |
| `TPoint`                            | Sample Number indicating peak of the T wave (-1 if no T wave detected)                                                                                                                |
| `TStart`                            | Sample Number indicating start of the T wave                                                                                                                                          |
| `TEnd`                              | Sample Number indicating end of the T wave                                                                                                                                            |
| `TemplateID`                        | The ID of the template to which this beat has been assigned (-1 if not assigned to a template)                                                                                        |
| `seconds`                           | Number of seconds from beginning of recording to R-point (Rpoint / sampling rate (256))                                                                                               |
| `stage`                             | Sleep stage merged from [polysomnography XML staging annotations](:pages_path:/polysomnography-introduction.md) (0 = Wake / 1 = Stage 1 / 2 = Stage 2 / 3 or 4 = Stage 3/4 / 5 = REM) |

## References

The open source code used for this analysis along with a tutorial on its use is available at the NIH-sponsored Research Resource for Complex Physiologic Signals: http://physionet.org/tutorials/hrv-toolkit/
