# Polysomnography introduction

In-home polysomnography (PSG) was conducted using the Compumedics Somte System (Compumedics Ltd., Abbotsford, Australia). The sensors and recording montage consisted of cortical electroencephalograms (central C4-M1, occipital Oz-Cz, and frontal Fz-Cz leads), bilateral electrooculograms, chin EMG, thoracic and abdominal respiratory inductance plethysmography (by auto-calibrating inductance bands); airflow (by nasal-oral thermocouple and pressure recording from a nasal cannula); ECG; leg movements, and finger pulse oximetry. In addition to connection of sensors and electrodes, trained staff members completed signal calibrations and checked impedance.  Nocturnal recordings were transmitted to the centralized reading center at Brigham and Women's Hospital and data were scored by trained technicians using current guidelines.

Notes:

- [Montage and Sampling Rate Information](:pages_path:/equipment/montage-and-sampling-rate-information.md)
- [Polysomnography Manual of Procedures](:files_path:/documentation/MESA_Sleep_Polysomnography_Manual_of_Procedures.pdf)
- [Polysomnography Scoring Manual](:files_path:/documentation/MESA_Sleep_Polysomnography_Scoring_Manual.pdf)

## Signal and annotation files

[Raw polysomnography data](:files_path:/polysomnography) are available for 2,056 MESA Sleep participants. Each recording has a signal file (.EDF) and two versions of the event scoring and epoch staging annotations (.XML).

1. **[EDF](:files_path:/polysomnography/edfs)** - Signal files in the [European Data Format](http://www.edfplus.info/) exported from Compumedics Profusion.
2. **[XML (Profusion)](:files_path:/polysomnography/annotations-events-profusion)** - Annotation files exported from Compumedics Profusion. ([Learn more...](https://github.com/nsrr/edf-editor-translator/wiki/Compumedics-Annotation-Format))
3. **[XML (NSRR)](:files_path:/polysomnography/annotations-events-nsrr)** - Annotation files processed in the [EDF Editor and Translator](https://www.sleepdata.org/community/tools/12) tool.

NSRR XML files can be overlaid onto EDF signal files using the [EDF Viewer tool](https://sleepdata.org/community/tools/nsrr-edf-viewer). For more information about the XML translation (mapping) process, review the files available on the [EDF Editor and Translator Releases page](https://github.com/nsrr/edf-editor-translator/releases).

## Hypopnea event tags

Hypopnea events are represented by two different tags in the XML annotation files. Events with the `Hypopnea` tag are hypopneas with a reduction in airflow between 30% and 50% from baseline levels. Events with the `Unsure` tag are hypopneas with a reduction in airflow greater than 50% from baseline levels.

If interested in all hypopneas that have a 30% or more reduction in airflow, both event types should be included. If interested in events with greater reduction in airflow (>50%), use those that were labeled with the `Unsure` tag.

The `Unsure` tag **does not represent uncertainty about the event**, but rather was the only custom tag available in the original polysomnography scoring program.

Additional criteria can be applied to limit events based on associated desaturation and/or arousal.

## Known issues

- In the initial months of data collection, the Sleep Reading Center recognized that the thermistor signal was not reliable, so an equipment change was made to the ThermiSense (Salter) unit. The old configuration contained a "Therm" channel, while the new configuration contained an "Aux_AC" channel instead.
- Two subjects (1738, 6476) have mismatched total sleep times when comparing the [**slpprdp5** variable](https://sleepdata.org/datasets/mesa/variables/slpprdp5) to the total amount of sleep time in the XML annotation files. The NSRR team found data loss or corruption when reviewing the original scored data for these subjects. ([Forum reference](https://sleepdata.org/forum/total-sleep-time-dismatch-issue))

## History / changelog

*October 2020*
- EDF replaced for subject 0718. The original file had signals that cut-off partway into the recording.

*June 2018*
- EDF and XML files reexported for subjects 1013 and 2934. The original files were missing event and staging annotations.

*October 2017*
- EDF and XML files reexported for subjects 2852 and 3003. An issue was found with files inadvertantly being duplicated.

*May 2016*
- Polysomnography data uploaded to sleepdata.org after exports from Compumedics Profusion

## Questions?

Please reach out to us at support@sleepdata.org or in the [Forum](https://sleepdata.org/forum) if you have questions.
