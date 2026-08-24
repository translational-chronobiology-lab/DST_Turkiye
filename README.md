
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Permanent Daylight Saving Time in Türkiye: Personal Light Exposure, Sleep, and Daily Experience

------------------------------------------------------------------------

## About the Repository

This repository contains the R scripts, data files, and supporting
documentation used for the analysis of personal light exposure, sleep,
sleepiness, and mood in this study. It is provided to support
reproducibility, transparency, and further examination of the analyses
and findings reported in the manuscript.

------------------------------------------------------------------------

### Dataset Overview

The dataset comprises two main parts:

**1. First part — MeLiDos data**

The analyses use secondary data from the **MeLiDos dataset** collected
in İzmir, Türkiye (38.3°N, 26.6°E), available at
<https://github.com/MeLiDosProject/DidikogluEtAl_Dataset_2025>. The
dataset includes data from 17 participants who wore Condor ActLumus
light loggers, which recorded melanopic equivalent daylight illuminance
(melanopic EDI) at 10-second intervals. Participants also completed
morning sleep diaries and repeated momentary assessments of sleepiness
and mood throughout the day. These data can be accessed through the
`melidosData` R package at
<https://melidosproject.github.io/melidosData/>.

**2. Second part — New data**

A second dataset (collected by **Sena Gulsum Akgun**) included 40 newly
recruited participants from the same location, using the same wearable
light-monitoring protocol together with daily sleep diaries.

**Light exposure data:**

Raw melanopic equivalent daylight illuminance (melanopic EDI) data were
cleaned prior to calculation of light-exposure metrics. Values ≥120,000
lx were considered implausible and recoded as missing. Data were then
grouped into hourly intervals, and hourly segments with more than 50%
missing melanopic EDI observations were excluded. Recordings were
subsequently organised by calendar day, and gaps in the time series were
regularised to represent complete 24-h periods. Days with more than 20%
missing melanopic EDI data were excluded from further analysis.

> Participants were classified into seasonal groups based on the dates
> of their available recordings. The April–October group included only
> participants whose data were collected entirely between 1 April and 25
> October, whereas the November–March group included only participants
> whose data were collected entirely between 1 November and 25 March.
> Participants with recordings during the DST transition windows (26–31
> March or 26–31 October), or whose recordings spanned both seasonal
> periods, were excluded to ensure unambiguous group assignment. After
> applying these criteria, **52 participants** were retained for the
> seasonal-group analyses.

------------------------------------------------------------------------

## Analysis Workflow

All data cleaning, statistical analyses, and generation of `figures` and
`tables` were performed using the `DST_Turkiye.Rmd` file provided in
this repository.

------------------------------------------------------------------------

## About the Data

`demographics_iztech.RData` contains participant demographic
information, including age and sex, together with baseline
health-screening variables. `sleep_diary_iztech.RData` contains daily
sleep-diary measures, including sleep delay, number of awakenings, awake
duration, sleep duration, bedtime, wake time, and subjective sleep
quality. `light_wrist_iztech.RData` contains cleaned wrist-level
light-monitoring time-series data collected using Condor ActLumus
devices at 10-s intervals, including melanopic equivalent daylight
illuminance (melanopic EDI). `light_all.RData` contains the combined
wrist-level melanopic EDI time-series data from the MeLiDos dataset and
the newly collected İzmir dataset. `light_glasses.RData` contains
cleaned near-corneal light-monitoring time-series data from the MeLiDos
participants who wore glasses-mounted Condor ActLumus devices.
`light_metrics.RData` contains derived personal light-exposure metrics
calculated from all available wrist-level measurements, including
measures of light level, cumulative exposure, duration, timing, and
related light-exposure characteristics. `light_metrics_glasses.RData`
contains the corresponding derived light-exposure metrics calculated
from the near-corneal MeLiDos measurements.
