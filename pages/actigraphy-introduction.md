# Actigraphy introduction

MESA Sleep recruited 2,237 participants to wear wrist-worn actigraphy devices ([Actiwatch Spectrum, Philips Respironics](http://www.usa.philips.com/healthcare/product/HC1046964/actiwatch-spectrum-activity-monitor)) between 2010 and 2013. Participants were instructed to wear the watch for a week. Records were scored by a trained technician at the Boston Sleep Reading Center.

The [documentation folder](:files_path:/documentation) contains manuals and in-depth descriptions of the actigraphy devices and scoring process used in MESA Sleep. Further, the [MESA Sleep dataset](:files_path:/datasets) contains summary phenotype data from the actigraphy data collection.

## Epoch-by-epoch files

[Epoch-by-epoch (EBE) data files (CSV)](:files_path:/actigraphy) have been created for 2,159 participants with actigraphy data. Each row in these files represents 30 seconds worth of summary data from the actigraphy device.

Notes:

- Dates have been removed. Each epoch contains a clock time.
- Epochs without activity counts and/or light readings typically indicate offwrist time and/or the watch's failure to provide a valid measurement for that epoch.
- Be cognizant of excluded/invalid epochs when analyzing these data.

## Variable descriptions

Each epoch-by-epoch file contains 15 columns/variables. The meanings of these variables are as follows:

| Name                | Label                               | Units / Categories / Notes                  |
| ------------------- | ----------------------------------- | ------------------------------------------- |
| `mesaid`            | Random BioLINCC ID                  |                                             |
| `line`              | Epoch line number                   |                                             |
| `linetime`          | Clock time                          | HH:MM:SS                                    |
| `offwrist`          | Off wrist indicator                 | 0 = On wrist / 1 = Off wrist                |
| `activity`          | Activity count                      |                                             |
| `marker`            | Event marker indicator              | 0 = Marker not pressed / 1 = Marker pressed |
| `whitelight`        | White light                         | Lux                                         |
| `redlight`          | Red light                           | Microwatts per square centimeter            |
| `greenlight`        | Green light                         | Microwatts per square centimeter            |
| `bluelight`         | Blue light                          | Microwatts per square centimeter            |
| `wake`              | Awake indicator<sup>*</sup>         | 0 = Asleep / 1 = Awake                      |
| `interval`          | Interval type<sup>*</sup>           |                                             |
| `dayofweek`         | Day of the week                     | 1 = Sunday / 2 = Monday / etc.              |
| `daybymidnight`     | Incrementing day number (midnight)  | Counter turns over at midnight              |
| `daybynoon`         | Incrementing day number (noon)      | Counter turns over at noon                  |

<sup>* The wake/sleep detection algorithm runs across the entire recording, though sleep in ACTIVE intervals is never counted toward overall sleep totals. Actual sleep is tallied within REST intervals only. REST-S intervals indicate the period between sleep onset and offset.</sup>

## Actigraphy and polysomnography overlap

Many researchers have asked about overlapping polysomnography (PSG) and actigraphy (ACT) data in the MESA dataset. All dates were removed from the data as part of the de-identification process. The NSRR team went back to the raw data to align the dates of the PSG and ACT data. [This dataset](:files_path:/overlap) provides a reference to individual rows in the ACT epoch-by-epoch CSV files that align with the concurrent start time of the subject's PSG recording.

[The dataset](:files_path:/overlap) contains 4 variables.

1. mesaid - MESA Subject Identifier (BioLINCC/NSRR)
2. line - Epoch line number
3. linetime - Epoch line time (hh:mm:ss)
4. starttime_psg - Actual PSG study start time (source: [STSTARTP5](https://sleepdata.org/datasets/mesa/variables/ststartp5))

The PSG start times were rounded to the nearest 30 seconds in order to match the ACT epoch line times.

**How to Use:** Import and merge the [PSG XML annotations](:pages_path:/polysomnography-introduction.md) with the ACT epoch-by-epoch data, starting at the actigraphy epoch identified in [the dataset](:files_path:/overlap).

## History / changelog

*June 2018*
- Add information about how to look at overlapping PSG and ACT data

*March 2017*
- Change `day` variable to `daybymidnight` and add new `daybynoon` variable
- Replace EBE data for six subjects: 0628, 1420, 1842, 2551, 2887, 5263
  - Subjects had data from multiple actigraphy recordings combined inadvertently. Files were modified to only keep one of the recordings.

*October 2016*
- Upload actigraphy epoch-by-epoch data to sleepdata.org

## Questions?

Please reach out to us at support@sleepdata.org or in the [Forum](https://sleepdata.org/forum) if you have questions.
