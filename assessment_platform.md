Project Title : AI powered candidate assessment platform 



**Template 1 — MCQ Questions**

SYSTEM:

You are an expert technical assessment question writer.

Return ONLY a valid JSON array. No explanations, no markdown, no extra text.



USER:

Generate {count} multiple choice questions for a {domain} role 

at {difficulty} difficulty level.



Job Description:

{job\_description}



Return exactly this JSON format:

\[

&#x20; {

&#x20;   "question": "Question text here",

&#x20;   "options": \["A. option one", "B. option two", "C. option three", "D. option four"],

&#x20;   "correct": "A",

&#x20;   "explanation": "Why this answer is correct"

&#x20; }

]

**Template 2 — Descriptive Questions**

SYSTEM:

You are an expert technical assessment question writer.

Return ONLY a valid JSON array. No explanations, no markdown, no extra text.



USER:

Generate {count} descriptive questions for a {domain} role 

at {difficulty} difficulty level.



Job Description:

{job\_description}



Return exactly this JSON format:

\[

&#x20; {

&#x20;   "question": "Question text here",

&#x20;   "rubric": "Award full marks for mentioning X, Y, Z. Partial marks for...",

&#x20;   "max\_score": 10,

&#x20;   "word\_limit": 200

&#x20; }

]

**Template 3 — Cognitive Questions**

SYSTEM:

You are an expert cognitive assessment question writer.

Return ONLY a valid JSON array. No explanations, no markdown, no extra text.



USER:

Generate {count} cognitive reasoning questions suitable for a {role} role.

Types should include logical, numerical, and verbal reasoning.



Return exactly this JSON format:

\[

&#x20; {

&#x20;   "question": "Question text here",

&#x20;   "type": "logical",

&#x20;   "options": \["A. option one", "B. option two", "C. option three", "D. option four"],

&#x20;   "correct": "B",

&#x20;   "explanation": "Why this answer is correct"

&#x20; }

]

**Template 4 — Answer Evaluation (for Day 4)**



Save this one too — you’ll need it later:



SYSTEM:

You are a strict but fair assessment evaluator.

Return ONLY a valid JSON object. No explanations, no markdown, no extra text.



USER:

Question: {question}

Rubric: {rubric}

Maximum score: {max\_score}

Candidate's answer: {candidate\_answer}



Return exactly this JSON format:

{

&#x20; "score": 7,

&#x20; "justification": "The candidate correctly identified X and Y but missed Z which was worth 3 marks."

}







Key things to remember



Write these down too:



Always use a system prompt that says “Return ONLY valid JSON” — this is the most important instruction

Tomorrow you’ll add retry logic — if the model returns invalid JSON, you re-call with “Your previous response was invalid JSON. Try again.”

Validate every response — check all required fields exist before saving to DB

