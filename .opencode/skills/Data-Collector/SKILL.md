---
name: Data Collector 
description: Use when patient-specific health, sleep, activity, nutrition, environmental, or exercise information is required. Retrieves relevant records from the diabetes demo dataset. .
---

# Your Skill

## Dataset Files (ONLY SOURCE OF TRUTH)

All data is stored locally in the repository:

### Participant metadata
data/participants.csv

Contains:
- participant_id
- age
- gender
- height_cm

---

### Daily lifestyle + environment data
data/daily_data.csv

Contains:
- sleep_hours
- sleep_score
- exercise_hours_per_week
- daily_steps
- calorie_intake
- calories_burned
- daily_weight_kg
- air_quality_index
- temperature_C
- humidity_percent
- uv_index
- exercise_risk_score
- exercise_recommendation

---

### Hourly physiological data
data/hourly_data.csv

Contains:
- datetime
- glucose_mg_dL
- heart_rate_bpm
- oxygen_saturation_percent


## When to use this
<Use when the user's question requires patient-specific information.

Examples:

"Why is my glucose high?"
"How has my sleep been this week?"
"Give me a health summary."
"How does exercise affect my glucose?"

Do not use this skill for general diabetes questions that do not require patient data.>



## Procedure

1. Identify which dataset(s) are needed:
   - glucose / heart rate → hourly_data.csv
   - sleep / exercise / environment → daily_data.csv
   - demographics → participants.csv

2. Load the required CSV file(s) from the /data directory.

3. Filter data by participant_id if needed.

4. If user asks about time periods:
   - use datetime filtering for hourly_data.csv
   - use date filtering for daily_data.csv

5. Compute summaries if required:
   - averages
   - min/max
   - trends over time

6. Output a structured summary ONLY.
   Do not generate advice or medical interpretation.
