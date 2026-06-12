---

name: daily-summary
description: Use when the user asks for a daily health overview, diabetes status update, wellness summary, or quick snapshot of their glucose, heart rate, oxygen levels, sleep, activity, nutrition, and environment.
metadata:
difficulty: beginner
--------------------

# Daily Summary

Generate a clear daily health summary for DBuddy using the demo patient dataset.

## When to use this

Use this skill when the user starts a new chat and wants a quick overview of their current health status.

Use this skill when the user asks things like:

* "How am I doing today?"
* "Give me my daily summary."
* "What is my health status today?"
* "Can you show my diabetes summary?"
* "Give me a quick overview."
* "What should I pay attention to today?"
* "Is today a good day to exercise?"
* "Summarise my glucose, sleep and activity."
* "What does my data look like today?"

Also use this skill when the user asks for a general check-in that requires multiple types of data, including:

* glucose
* heart rate
* oxygen saturation
* sleep
* activity
* calorie intake
* calories burned
* weight
* environmental conditions
* exercise risk score
* exercise recommendation

Do not use this skill for deep analysis of one specific issue.

For example:

* "Why did my glucose spike at 2am?" should use Time-Series Analyzer.
* "Why has my glucose been higher this week?" should use Trend Analyzer.
* "What food should I eat for diabetes?" should use Medical Research and Advice Generator.
* "What is my heart rate right now?" should use Data Collector.

## Data to include

The daily summary should combine both daily and hourly demo data.

### Daily data

Use:

* participant_id
* date
* age
* height_cm
* gender
* exercise_hours_per_week
* daily_weight_kg
* sleep_score
* sleep_hours
* rem_hours
* awake_hours
* calorie_intake
* calories_burned
* daily_steps
* air_quality_index
* temperature_C
* humidity_percent
* uv_index
* exercise_risk_score
* exercise_recommendation

### Hourly physiological data

Use the most recent available readings for:

* heart_rate_bpm
* glucose_mg_dL
* oxygen_saturation_percent
* datetime

If useful, also calculate simple daily summaries such as:

* average glucose
* highest glucose
* lowest glucose
* average heart rate
* latest oxygen saturation

## Procedure

1. Retrieve the latest daily record for the selected participant.

2. Retrieve the latest available hourly physiological readings for the same participant.

3. Summarise the current status across these categories:

   * glucose
   * heart rate
   * oxygen saturation
   * sleep
   * activity
   * nutrition
   * weight
   * environment
   * exercise risk

4. Identify one key insight from the data.

   Examples:

   * glucose is higher than usual
   * sleep score is low
   * activity is below target
   * temperature or air quality may affect exercise suitability
   * exercise risk score is elevated
   * oxygen saturation appears lower than expected

5. Provide one simple suggested action.

   Examples:

   * take a gentle walk
   * prioritise hydration
   * choose a balanced meal
   * rest and monitor symptoms
   * avoid intense exercise if risk is high
   * speak to a healthcare professional if readings are concerning

6. Keep the response short, friendly, and easy to understand.

7. Do not diagnose the user.

8. Do not prescribe medication.

9. Do not recommend changing medication dosage.

10. Tell the user what you did.

## Output format

Use this structure:

```markdown
## Daily Health Summary

**Date:**  
<date>

**Glucose:**  
<latest glucose and/or daily glucose summary>

**Heart rate:**  
<latest heart rate and/or average heart rate>

**Oxygen saturation:**  
<latest oxygen saturation>

**Sleep:**  
<sleep score, sleep hours, REM hours, awake hours>

**Activity:**  
<daily steps, exercise hours per week, calories burned>

**Nutrition:**  
<calorie intake>

**Weight:**  
<daily weight>

**Environment:**  
<air quality index, temperature, humidity, UV index>

**Exercise risk:**  
<exercise_risk_score and exercise_recommendation>

**Key insight:**  
<one important observation>

**Suggested action:**  
<one practical, safe suggestion>

**What I did:**  
I checked your latest daily health record and most recent hourly physiological readings, then summarised the main points for today.

**Safety note:**  
This summary is educational support only and does not replace medical advice from a healthcare professional.
```

## Example

```markdown
## Daily Health Summary

**Date:**  
2026-06-12

**Glucose:**  
Your latest glucose reading is 168 mg/dL. Your readings today appear slightly elevated.

**Heart rate:**  
Your latest heart rate is 86 bpm.

**Oxygen saturation:**  
Your latest oxygen saturation is 97%.

**Sleep:**  
You slept 5.8 hours, with 1.1 hours of REM sleep and 0.9 hours awake. Your sleep score is lower than ideal.

**Activity:**  
You have taken 5,400 steps today. Your weekly exercise level is moderate.

**Nutrition:**  
Your calorie intake today is 2,150 kcal.

**Weight:**  
Your recorded weight today is 74.2 kg.

**Environment:**  
The air quality index is moderate, temperature is 27°C, humidity is 68%, and UV index is 6.

**Exercise risk:**  
Your exercise risk score is slightly elevated. The recommendation is to choose light to moderate activity.

**Key insight:**  
Your glucose is slightly high and your sleep was lower than usual, which may affect your energy and glucose stability today.

**Suggested action:**  
Consider gentle movement such as a short walk, stay hydrated, and avoid intense exercise if you feel tired or unwell.

**What I did:**  
I checked your latest daily health record and most recent hourly physiological readings, then summarised the main points for today.

**Safety note:**  
This summary is educational support only and does not replace medical advice from a healthcare professional.
```
