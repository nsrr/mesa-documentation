# Polysomnography introduction

In-home polysomnography (PSG) was conducted using the Compumedics Somte System (Compumedics Ltd., Abbotsford, Australia). The sensors and recording montage consisted of cortical electroencephalograms (central C4-M1, occipital Oz-Cz, and frontal Fz-Czleads), bilateral electrooculograms, chin EMG, thoracic and abdominal respiratory inductance plethysmography (by auto-calibrating inductance bands); airflow (by nasal-oral thermocouple and pressure recording from a nasal cannula); ECG; leg movements, and finger pulse oximetry. In addition to connection of sensors and electrodes, trained staff members completed signal calibrations and checked impedance.  Nocturnal recordings were transmitted to the centralized reading center at Brigham and Women's Hospital and data were scored by trained technicians using current guidelines.

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

**Note:** Events using the `Unsure` tag are hypopneas with a >50% decrease in flow (AASM alternative definition).

## History / changelog

*May 2016*
- Polysomnography data uploaded to sleepdata.org after exports from Compumedics Profusion

## Questions?

Please reach out to us at support@sleepdata.org or in the [Forum](https://sleepdata.org/forum) if you have questions.
