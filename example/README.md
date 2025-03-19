# Tutorial for Breast Cancer NACT Response Predictor

The online predictor can be accessed at: http://www.wang-lab-hkust.com:8050.
Please follow these steps to use the web application:
1. Upload all data, wait until uploading finish.
2. Click "GET PREDICTION", and you will get prediction in a CSV (comma-separated values) file.
3. Adjust the cutoff to find a best binary prediction.

Reminders:
1. Please use **CSV (comma-separated values)** file for all tables.
2. Please make sure the IDs used in different datasets are consistent.

## Clinical dataset

Please include HER2, ER, T, N, KI67 and G3 in columns of the clinical table. If you don't have the information, please leave blank in the cell.

HER2: HER2 status, please enter 0 for negative or 1 for positive.

ER: ER status, please enter 0 for negative or 1 for positive.

T: Primary tumor grade, please fill 0 for T1 and T2, and 1 for T3 and T4.

N: whether nearby lymph nodes have cancer or not. 0 for no and 1 for yes.

KI67: KI67 index, please enter values ranged from 0 to 1.

G3: Primary tumor grade, please enter 0 for tumor grade T1/T2/T4 or 1 for tumor grade T3.

If you have survival data (e.g., disease-free survival), you can also include them in the table:

STATUS: 0 for Disease-Free/Living, 1 for Recurred/Progressed/Decreased.

MONTHS: time to event, float.

Example:

| Patient | HER2 | ER | T | N | KI67 | G3 | STATUS | MONTHS |... |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| PS1 | 0 | 0 | 1 | 0 | 0.5 | 0 | 0 | 70.5 | ... |
| PS2 | 1 | 0 | 0 | 1 |  | 1 | 1 | 60 | ... |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |


## Methylation Dataset

Please enter the methylation levels for global and each gene, range:[0,1].

Example:

| Patient | MAP4K1 | KIT | CDKN2A | ... |
| --- | --- | --- | --- | --- |
| PS1 | 0.2 | 0.3 | 0.5 | ... |
| PS2 | 0.1 | 1 | 0.75 | ... |
| ... | ... | ... | ... | ... |

## RNA Dataset

Please make sure unit is **TPM (transcripts per million)**.

Example:

| Patient | AR | MKI67 | STAT1 | ... |
| --- | --- | --- | --- | --- |
| PS1 | 15 | 2 | 50 | ... |
| PS2 | 5 | 1 | 75 | ... |
| ... | ... | ... | ... | ... |

## Protein Dataset and Phosphoprotein Dataset

Please **normalize and log-transform** the proteomic data before uploading.

Example:

| Patient | TOP2A | ERBB2 | MKI67 | ... |
| --- | --- | --- | --- | --- |
| PS1 | 15 | 30 | 25 | ... |
| PS2 | 20 | 10 | 15 | ... |
| ... | ... | ... | ... | ... |
