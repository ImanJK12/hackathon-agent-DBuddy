 ---

name: medical-research
description: Use when the user asks for diabetes-related advice, exercise guidance, food recommendations, medication information, lifestyle support, or explanations that require trusted medical evidence from the web.
metadata:
difficulty: intermediate
------------------------

# Medical Research

Use trusted online health sources to support DBuddy’s answers with evidence-based information.

## When to use this

Use this skill when the user asks questions that require medical, lifestyle, nutrition, exercise, or diabetes-related evidence.

Use this skill when the user asks things like:

* "Should I exercise today?"
* "What food should I eat?"
* "Why is my glucose high?"
* "How does sleep affect diabetes?"
* "Is walking good for glucose control?"
* "What should I do if my oxygen level is low?"
* "What does my heart rate mean?"
* "What diabetes advice is recommended?"
* "Can you explain this health risk?"
* "What routine would help me manage diabetes?"

Also use this skill when DBuddy has already collected patient data and needs evidence to support a personalised response.

For example, if the Data Collector finds:

* high glucose
* low sleep score
* low daily steps
* high temperature
* poor air quality
* high exercise risk score

then Medical Research should search trusted sources to explain how these factors may relate to diabetes management.

Do not use this skill for simple dataset lookups such as:

* "What is my heart rate?"
* "What is today’s temperature?"
* "What is my oxygen level?"

Those questions should use the Data Collector skill first.

## Trusted sources

Prioritise:

1. NHS
2. Diabetes UK
3. NICE
4. CDC
5. WHO
6. PubMed
7. Peer-reviewed medical journals

Avoid:

* social media posts
* forums
* random blogs
* influencer health advice
* unsupported claims
* sources selling unverified treatments

## Procedure

1. Identify the health topic in the user’s question.

   Examples:

   * exercise and diabetes
   * glucose control
   * food and nutrition
   * sleep and glucose
   * heart rate
   * oxygen saturation
   * environmental factors
   * medication safety

2. Search trusted medical sources on the web.

3. Prioritise sources that are relevant, reputable, and easy for the user to understand.

4. Extract only the key evidence needed to answer the user’s question.

5. Connect the evidence back to the user’s situation.

   For example:

   * If the user has low sleep, explain how sleep may affect glucose control.
   * If the user has low activity, explain how gentle movement may support glucose management.
   * If the user asks about food, provide general diabetes-friendly nutrition principles.
   * If the user asks about exercise risk, support the explanation with trusted exercise guidance.

6. Do not diagnose the user.

7. Do not prescribe medication.

8. Do not recommend changing medication dosage.

9. Do not claim certainty when the evidence is limited.

10. Tell the user what you did.

## Output format

Use this structure:

```markdown
## Medical Research Summary

**Topic researched:**  
<short topic>

**Trusted sources checked:**  
<list sources used>

**Key evidence:**  
- <finding 1>
- <finding 2>
- <finding 3>

**How this relates to your data:**  
<connect evidence to the user’s glucose, sleep, exercise, nutrition, heart rate, oxygen level, or environment>

**Safety note:**  
This is educational support only and does not replace advice from a healthcare professional.
```

## Example

```markdown
## Medical Research Summary

**Topic researched:**  
Exercise and glucose management in diabetes.

**Trusted sources checked:**  
NHS, Diabetes UK, NICE.

**Key evidence:**  
- Regular physical activity can help support blood glucose management.
- Gentle activity such as walking may be suitable for many people, depending on individual health status.
- People with diabetes should take care when exercising if they feel unwell or have unusual glucose readings.

**How this relates to your data:**  
Your recent daily steps are lower than usual and your exercise risk score is elevated. This suggests that gentle, low-intensity movement may be more appropriate than intense exercise today.

**Safety note:**  
This is educational support only and does not replace advice from a healthcare professional.
```

