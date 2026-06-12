---
name: Data Collector 
description: Use when patient-specific health, sleep, activity, nutrition, environmental, or exercise information is required. Retrieves relevant records from the diabetes demo dataset. .
---

# Your Skill

## When to use this
<Use when the user's question requires patient-specific information.

Examples:

"Why is my glucose high?"
"How has my sleep been this week?"
"Give me a health summary."
"How does exercise affect my glucose?"

Do not use this skill for general diabetes questions that do not require patient data.>

## Available Data

<Patient Information

- participant_id
- age
- gender
- height_cm

Activity

- exercise_hours_per_week
- daily_steps
- calories_burned

Nutrition

- calorie_intake

Sleep

- sleep_score
- sleep_hours
- rem_hours
- awake_hours

Weight

- daily_weight_kg

Environment

- air_quality_index
- temperature_C
- humidity_percent
- uv_index

Risk Assessment

- exercise_risk_score
- exercise_recommendation>

## Procedure
1. <Identify which patient metrics are relevant to the user's question>
2. <Retrieve the relevant records from the demo dataset>
3. <Focus on the most recent data unless the user asks for historical analysis>
4. <Calculate simple summaries where useful: averages, minimums, maximums, recent changes>
5. <Organise findings into: Patient context, recent health metrics, environmental context>
6. <Pass the summary to the next skill>
7. <Do not generate recommendations or medical advice.>
8. Tell the user what you did.
