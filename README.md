# Notebook Introduction: Federal Drug Offenses Analysis (2025)

## Context & Objectives
The purpose of this notebook is to execute a targeted analysis of federal sentencing data obtained from the United States Sentencing Commission (USSC). Large government repositories offer incredibly rich insight, but they often present significant data engineering hurdles due to their sheer width and footprint. 

This notebook documents a step-by-step pipeline designed to extract specific domain knowledge from an otherwise unmanageable file.

### Executive Summary of the Workflow:
1. **Identify the Data Constraints:** Acknowledge that the raw USSC records span an overwhelming 22,000+ columns, rendering manual applications like Excel entirely unusable.
2. **Streamed Extraction:** Implement a memory-safe execution script in Python using `pandas` chunk sizes of 10,000 rows to avoid memory overhead or system crashes.
3. **Data Transformation & Filter:** Drop irrelevant rows, and filter exclusively for individuals tied to one or more active drug charges (`NODRUG >= 1`).
4. **Reshape & Aggregate:** Flatten the wide `DRUGTYP` attributes into a long vertical series to establish a master value count for the top 10 federal drug offenses of 2025.
5. **Downstream Visualization Preparation:** Format a lean dataset for direct use in matplotlib and for export into Tableau to build out a dashboard.
