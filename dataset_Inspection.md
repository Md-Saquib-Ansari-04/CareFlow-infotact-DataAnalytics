# CareFlow Week 1 — Dataset Inspection

**Prepared by:** Md Saquib  
**Role:** Process Discovery

## 1. Main event log

- **File:** `event_log_core_review.csv`
- **Number of rows:** 2,222 data rows
- **Number of columns:** 10
- **Column names:**
  1. `SOURCE_EXCEL_ROW`
  2. `ID`
  3. `Timestamp start`
  4. `Timestamp end`
  5. `Activity_MACRO`
  6. `START_VALID`
  7. `END_VALID`
  8. `END_BEFORE_START`
  9. `CASE_ID_VALID`
  10. `ACTIVITY_VALID`
- **Possible case ID column:** `ID`
- **Possible activity column:** `Activity_MACRO`
- **Possible timestamp column:** `Timestamp start`
- **Additional timestamp column:** `Timestamp end`

## 2. Other datasets

The following files have not yet been inspected because their contents have not been provided for this check.

- `activity_frequency.csv`: Not yet inspected.
- `activity_transitions.csv`: Not yet inspected.
- `case_pathways.csv`: Not yet inspected.
- `case_summary.csv`: Not yet inspected.

## 3. Initial data-quality checks

- **Missing values:** 577 missing cells, all in the `Timestamp end` column. The other nine columns have no missing cells.
- **Timestamp format:** Sample values appear in `DD-MM-YYYY HH:MM` format, for example `12-11-2015 07:35`. The exact date convention should be confirmed.
- **Duplicate records:** No exact duplicate rows were found in the main event log.
- **Distinct cases:** 328 unique values in the `ID` column.
- **Distinct activities:** 36 unique values in the `Activity_MACRO` column.
- **Case ID validation:** All 2,222 rows have `CASE_ID_VALID` marked as `True`.
- **Activity validation:** All 2,222 rows have `ACTIVITY_VALID` marked as `True`.
- **Other concerns:** The missing end timestamps require investigation. Their absence does not automatically mean the records are incorrect. The meanings of the validation columns and the intended treatment of missing end times should be confirmed.

## 4. Limitations

These are preliminary observations from the main event log only. The other four datasets have not yet been inspected. The meaning of the columns, timestamp convention, event ordering and missing end timestamps require validation before drawing conclusions about the process.