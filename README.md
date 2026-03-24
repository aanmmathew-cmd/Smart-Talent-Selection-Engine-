# Smart Talent Selection Engine

## Project Title
Smart Talent Selection Engine

## The Problem
Recruiters spend a lot of time manually checking resumes. It is slow and inefficient.

## The Solution
This project automatically evaluates candidates based on skills and experience and gives a score.

## Tech Stack
 Python

## Setup Instructions

### Step 1: Install Python
Make sure Python is installed.

### Step 2: Run the program
```bash
python main.py

##Code for Python
job_skills = ["python", "ai", "machine learning", "data"]

candidates = [
    {"name": "Ann", "skills": ["python", "ai"]},
    {"name": "John", "skills": ["java", "backend"]},
    {"name": "Priya", "skills": ["python", "data"]},
    {"name": "Rahul", "skills": ["ai", "machine learning"]}
]

print("\n=== Smart Talent Selection Results ===\n")

results = []

for c in candidates:
    match_count = 0

    for skill in job_skills:
        if skill in c["skills"]:
            match_count += 1

    score = (match_count / len(job_skills)) * 100

    if score >= 75:
        level = "Highly Suitable"
    elif score >= 50:
        level = "Moderately Suitable"
    else:
        level = "Less Suitable"

    results.append((c["name"], score, level))

# Sorting
results.sort(key=lambda x: x[1], reverse=True)

# Display
for i, (name, score, level) in enumerate(results, start=1):
    print(f"{i}. {name} - Score: {score:.2f}% - {level}")

# Safe check
if results:
    print("\nTop Candidate:", results[0][0])
else:
    print("No candidates found.")

##Team Member
Ann Mariya Mathew
