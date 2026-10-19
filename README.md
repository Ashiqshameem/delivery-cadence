# Delivery Cadence: How to Use

Delivery Cadence finds the real schedule of a dataset. A dataset can deliver at several times a day, and some of those deliveries are one-off corrections. The tool shows which hours (UTC) repeat day after day, so you know what time to schedule a job.

## What you need

- The delivery tracking page, with results for a date range of at least 14 days. A longer range gives a more reliable pattern.
- The file `delivery-cadence-v2.html`. Open it in any browser. No login or install is needed.

## Steps

1. Open `delivery-cadence-v2.html` in your browser.
2. Pick the client at the top: **ENI** or **BKW**.
3. On the delivery tracking page, select a date range of at least two weeks.
4. Copy the results table:
   - **ENI:** copy from the first dataset name down to the last **model count** column.
   - **BKW:** copy from the first dataset name down to the last **file name** column.
   Copy all rows in the range, including corrections. The tool separates them itself.
5. Paste the copied rows into the box, replacing the sample text.
6. Choose the **Include** option:
   - **Both:** every delivery, scheduled and corrections. Available for ENI. For BKW, the corrections column is not used.
   - **Scheduled only:** ignores correction rows and finds the pattern of scheduled deliveries alone.
   - **Corrections only:** ignores scheduled rows and shows only correction deliveries.
7. Click **Analyze**.

## Reading the results

Each dataset gets its own card. Each row is one UTC hour:

- **Hour:** the UTC hour the dataset was delivered, for example `11:00 UTC`.
- **Seen on:** how many days out of the total days in your paste that hour appeared, for example `12/12 days`.
- **Status:** **Recurring** if the hour appears on at least half the days. **Occasional** if it appears less often.
- **Corrections** (ENI, Both mode only): how many of those days also had a correction at that hour.
- **Model counts seen** and **Typical** (ENI only): the model count usually delivered at that hour, with the latest value and its date.
- **Time seen** (BKW only): the earliest and latest arrival time within that hour, so you can see the usual window.

Recurring hours are the real schedule candidates. Occasional hours are one-off runs.

## Confirming the schedule

1. Note the Recurring hours for the dataset, for example 11 UTC and 19 UTC.
2. Go back to the delivery tracking page and check the same dataset over the last two dates you want to confirm.
3. Confirm that deliveries land at those hours on both dates. If they do, the schedule is correct.

## Tips

- If a dataset shows an hour as Recurring but its counts vary a lot, check the **Model counts seen** column before you trust the typical value.
- Unrecognized lines appear under **unrecognized lines** at the bottom. If many lines are skipped, the copy probably missed a column. Copy the table again, from the first dataset name to the last column.
- Paste one client at a time. Switching the client keeps each client's pasted text separate.
