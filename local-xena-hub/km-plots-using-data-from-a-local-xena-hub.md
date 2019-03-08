# KM plots using data from a Local Xena Hub

To visualize and perform a KM analysis, we use two columns/rows of data, time to event and event. These data must be loaded in a phenotype file. The phenotype file can contain other data as well.

Note that you will need to name the headers in your phenotype file EXACTLY what we recognize. See the list of recognized headers for each type of survival/interval below.

This data can be in days, months, years, etc.

## **Time to Event and Event**

**Time to Event** is a duration variable for each subject having a beginning and an end anywhere along the timeline of the complete study. It begins when the subject is enrolled into a study or when treatment begins, and ends when the end-point \(event of interest, for example, death or metastasis\) is reached or the subject is censored from the study.

Censoring means the total survival time for that subject cannot be accurately determined. This can happen when something negative for the study occurs, such as the subject drops out, is lost to follow-up, or the required data is not available or, conversely, something good happens, such as the study ends before the subject had the event of interest occur, i.e., they survived at least until the end of the study, but there is no knowledge of what happened thereafter.

**Event** indicates what the 'event' was for a patient, 1 for the event, for example, death or metastasis, and 0 for censored.

Help text was partially taken from [A PRACTICAL GUIDE TO UNDERSTANDING KAPLAN-MEIER CURVES](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3932959/).

## **Recognized header names for different types of survival**

Below is a table of the column/row header names we recognize for each type. Note that these header names are case sensitive.

| Survival Type | 'Time to Event' Header name | 'Event' Header name |
| :--- | :--- | :--- |
| Overall Survival | OS.time | OS |
| Disease free interval | DFI.time | DFI |
| Disease specific survival | DSS.time | DSS |
| Progression free interval | PFI.time | PFI |
| Local recurrence interval | LRI.time | LRI |
| Distant metastasis interval | DMI.time | DMI |
| Distant disease free survival | DDFS.time | DDFS |
| Invasive disease free survival | IDFS.time | IDFS |
| Regional recurrence | RR.time | RR |
| Relapse | Relapse.time | Relapse |
| Metastasis | Metastasis.time | Metastasis |
| Distant recurrence interval | DRI.time | DRI |
| Distant metastasis free survival | DMFS.time | DMFS |

## **Example Overall Survival**

| **sample** | OS | OS.time |
| :--- | :--- | :--- |
| **TCGA-AB-1234-01** | **0** | **100** |
| **TCGA-AB-6789-01** | **1** | **200** |
| **TCGA-CD-1234-01** | **0** | **300** |
| **TCGA-CD-5678-01** | **1** | **400** |

