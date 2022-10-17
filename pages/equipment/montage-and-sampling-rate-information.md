## Montage and sampling rate information

The settings below represent the standards set at the beginning of the project. There may be a small proportion of studies and signals that do not match these standards exactly. Please review the settings at the individual sleep study level as you proceed with any analyses.

| Channel                     | EDF Label | Input 1  | Input 2 | Sampling rate (Hz) | Hardware filters (Hz) | Sensor type                              |
|:---------------------------:|:---------:|:--------:|:-------:|:------------------:|:---------------------:|:----------------------------------------:|
| ECG                         | EKG       | ECG      | -       | 256                | -                     | Ag/AgCl patch                            |
| Left EOG                    | E1        | EOG-L    | Fpz     | 256                | Low Pass 100          | Gold cup electrode                       |
| Right EOG                   | E2        | EOG-R    | Fpz     | 256                | Low Pass 100          | Gold cup electrode                       |
| EMG                         | EMG       | EMG      | -       | 256                | Low Pass 100          | Gold cup electrode                       |
| Linked EEG                  | EEG1      | Fz       | Cz      | 256                | Low Pass 100          | Gold cup electrode                       |
| Linked EEG                  | EEG2      | Cz       | Oz      | 256                | Low Pass 100          | Gold cup electrode                       |
| Linked EEG                  | EEG3      | C4       | M1      | 256                | Low Pass 100          | Gold cup electrode                       |
| Nasal Pressure              | Flow      | Flow     | -       | 32                 | Low Pass 10           | Nasal Cannula                            |
| Snore                       | Snore     | Snore    | -       | 32                 | -                     | Nasal Cannula (vibratory)                |
| Thorax                      | Thor      | Thor     | -       | 32                 | Low Pass 10           | Compumedics Inductive Respiratory Band   |
| Abdomen                     | Abdo      | Abdo     | -       | 32                 | Low Pass 10           | Compumedics Inductive Respiratory Band   |
| Linked Left & Right Leg EMG | Leg       | Lleg     | Rleg    | 32                 | Low Pass 10           | Compumedics Limb Movement Sensor (Piezo) |
| Thermistor                  | Aux_AC    | Aux_AC   | -       | 32                 | -                     | Salter ThermiSense 5700B                 |
| Thermistor                  | Therm     | Therm    | -       | 32                 | -                     | Salter ThermiSense 5700B                 |
| Position                    | Pos       | Pos      | -       | 32                 | Low Pass 10           | Built-in Device Sensor                   |
| Plethysmography             | Pleth     | Pleth    | -       | 256                | -                     | Nonin 8000 sensor                        |
| Oximetry Status             | OxStatus  | OxStatus | -       | 1                  | -                     | Nonin 8000 sensor                        |
| SpO2                        | SpO2      | SpO2     | -       | 1                  | -                     | Nonin 8000 sensor                        |
| Heart Rate                  | HR        | HR       | -       | 1                  | -                     | Nonin 8000 sensor                        |
| Derived Heart Rate          | DHR       | DHR      | -       | -                  | -                     | Derived from EKG                         |
| REF                         | -         | Fpz      | -       | -                  | -                     | -                                        |

### Notes

- The meaning of the position signal values are as follows:
  - 0, Right
  - 1, Back
  - 2, Left
  - 3, Prone
  - 4, Upright
