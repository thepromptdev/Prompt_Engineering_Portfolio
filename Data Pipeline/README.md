**The Problem:** Unstructured legacy data (like raw customer emails or medical notes) is difficult to parse into traditional databases.

**The Solution:** Designed a Few-Shot processing pipeline that ingests chaotic text and flawlessly outputs clean, predictable JSON objects.

**Techniques Used:** 
* Few-Shot Learning
* Strict Output Formatting
* Syntax Standardization

**Lazy Prompt:** "Read the following doctor's transcript and extract the important information. I need to know the patient's name, what their main issue was, and how the doctor resolved it. Please output this in a JSON format so I can save it."
**TRANSCRIPT:** "Saw patient John Doe today, born 14th of March, 1985. He came in complaining of a nasty cough and a fever that started two days ago. Checked his vitals: blood pressure was 120/80, which is fine, but his temperature is up at 101.5 Fahrenheit. I'm prescribing him Amoxicillin, 500mg, to be taken three times a day for a week. Oh, and he mentions he's highly allergic to Penicillin, so wait, scratch that—do NOT give him Amoxicillin. Prescribe Azithromycin instead, 250mg once daily for 5 days."

**Output:** "{
  "patient_name": "John Doe",
  "main_issue": "Persistent cough and a fever of 101.5°F",
  "resolution": "Prescribed Azithromycin, 250mg once daily for 5 days, due to a known penicillin allergy."
}"

**Master Prompt Output:** "{"patient_name":"John Doe",
"patient_age":null,
"date_of_birth":"1985-03-14",
"symptoms":["cough","fever"],
"vitals":{"blood_pressure":"120/80",
  "temperature_f":101.5},
"allergies":["Penicillin","Amoxicillin canceled due to Penicillin allergy"],
"prescription":{"medication":"Azithromycin",
  "dosage":"250mg",
  "frequency":"once daily",
  "duration_days":5}
}"


## Observations:
Patient age was added on purpose to check if GenAIs would move towards their helping bias and calculate the age on their own. Most AIs left it null when they ran on higher parameters but some AIs like the copilot on Edge web browser immediately leaned on their helping bias and filled in the age. I observed this on other smaller GenAIs as well and realised that they have a certain memory limitations.
