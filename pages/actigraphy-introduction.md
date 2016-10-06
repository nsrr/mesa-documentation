# Actigraphy introduction

MESA Sleep recruited 2,237 participants to wear wrist-worn actigraphy devices ([Actiwatch Spectrum, Philips Respironics](http://www.usa.philips.com/healthcare/product/HC1046964/actiwatch-spectrum-activity-monitor)) between 2010 and 2013. Participants were instructed to wear the watch for a week. Records were scored by a trained technician at the Boston Sleep Reading Center.

The [documentation folder](:files_path:/documentation) contains manuals and in-depth descriptions of the actigraphy devices and scoring process used in MESA Sleep. Further, the [`mesa-sleep` dataset](:files_path:/datasets) contains summary phenotype data from the actigraphy data collection.

## Epoch-by-epoch files

[Epoch-by-epoch (EBE) data files (CSV)](:files_path:/actigraphy) have been created for 2,159 participants with actigraphy data. Each row in these files represents 30 seconds worth of summary data from the actigraphy device.

Notes:

- Dates have been removed. Each epoch contains a clock time.

## Variable descriptions

Each epoch-by-epoch file contains 14 columns/variables. The meanings of these variables are as follows:

| Name          | Label                       | Units / Categories / Notes                  |
| ------------- | --------------------------- | ------------------------------------------- |
| `mesaid`      | Random BioLINCC ID          |                                             |
| `line`        | Epoch line number           |                                             |
| `linetime`    | Clock time                  | HH:MM:SS                                    |
| `offwrist`    | Off wrist indicator         | 0 = On wrist / 1 = Off wrist                |
| `activity`    | Activity count              |                                             |
| `marker`      | Event marker indicator      | 0 = Marker not pressed / 1 = Marker pressed |
| `whitelight`  | White light                 | Lux                                         |
| `redlight`    | Red light                   | Microwatts per square centimeter            |
| `greenlight`  | Green light                 | Microwatts per square centimeter            |
| `bluelight`   | Blue light                  | Microwatts per square centimeter            |
| `wake`        | Awake indicator<sup>*</sup> | 0 = Asleep / 1 = Awake                      |
| `interval`    | Interval type<sup>*</sup>   |                                             |
| `dayofweek`   | Day of the week             | 1 = Sunday / 2 = Monday / etc.              |
| `day`         | Incrementing day number     | Counter turns over at midnight              |

<sup>* The wake/sleep detection algorithm runs across the entire recording, though sleep in ACTIVE intervals is never counted toward overall sleep totals. Actual sleep is tallied within REST intervals only. REST-S intervals indicate the period between sleep onset and offset.</sup>

## Questions?

Please reach out to us at support@sleepdata.org or in the [Forum](https://sleepdata.org/forum) if you have questions.
