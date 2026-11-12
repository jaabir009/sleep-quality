# Sleep Quality After Night Shifts Versus Days Off

Mohamed Askar · DATA 211 Data Science and Visualization · Metropolitan State University · Fall 2026

## Research question

Is my sleep quality score different after night shifts than on days off?

## Data

- `sleep_quality_project/sleep_data.xlsx` has one row per day for 22 consecutive days, October 19 to November 9, 2026.
- Columns used in the analysis: `date`, `day type` (Night shift or Day off), `sleep score` and `sleep (hrs)`.
- Sleep scores come from [YOUR DEVICE OR APP]. Excel stores them as proportions (0.62 means 62), and the report converts them to a 0-100 scale.
- November 2 and November 6 have no measurements. They are left blank, not estimated, so 20 nights are analyzed: 9 after night shifts and 11 on days off.

## Files

| File | What it is |
| --- | --- |
| `final_project.Rmd` | R Markdown source: data import, four ggplot2 graphs and the t-test |
| `final_project.pdf` | Knitted report |
| `Sleep_Quality_Poster.pdf` | Poster for the Fall 2026 Student Research Conference |
| `sleep_quality_project/sleep_data.xlsx` | The data |

## How to reproduce

1. Download the repository and open `final_project.Rmd` in RStudio.
2. Install the packages once if needed: `install.packages(c("readxl", "dplyr", "ggplot2"))`.
3. Click Knit. The Rmd reads `sleep_quality_project/sleep_data.xlsx`, so keep that folder beside the Rmd.

## Result

- Mean score after night shifts: 74.67 (n = 9). Mean score on days off: 83.36 (n = 11).
- Difference (night shift minus day off): -8.70 points, 95% confidence interval -19.29 to 1.89.
- Welch two-sample t-test: t = -1.73, df = 17.45, p = 0.101.

At alpha = 0.05 the test does not show a difference in mean scores. With only 20 nights the result is inconclusive; it is not evidence that the means are equal.

## Limitations

The data come from one person over 20 recorded nights, consecutive nights are not independent, and sleep after night shifts was also shorter, so day type and sleep length cannot be separated.
