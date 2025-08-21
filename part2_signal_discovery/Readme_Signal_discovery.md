# Signal Discovery Agent

## Overview
The **Signal Discovery Agent** processes resumes and job descriptions to extract structured insights.  
It reads **PDF resumes** (or CSV datasets of resumes), detects **skills, education, and keywords**, maps them to categories, and outputs structured results.  
This agent demonstrates automated **resume parsing** and **job signal discovery**.  

---

## Features
- Parse resumes directly from PDFs.  
- Extract:
  - Skills  
  - Education  
  - Keywords  
  - Categories (mapped from skills/keywords)  
- Generate Integrity Tokens for traceability.  
- Save results into a CSV file.  

---

## Input
- **Resumes** (PDFs uploaded directly to the notebook).  
- **Optional**: Dataset CSV of resume file paths.  

---

## Output
- **processed_resumes.csv** with the following columns:  
  - `File`  
  - `Skills`  
  - `Education`  
  - `Keywords`  
  - `Categories`  
  - `Integrity_Token`  

---

## Example Output
| File                | Skills        | Education | Keywords           | Categories | Integrity_Token                           |
|---------------------|---------------|-----------|--------------------|------------|--------------------------------------------|
| Kabir_resume_3.0.pdf | [Python, SQL] | [B.Tech]  | [Machine Learning] | [AI, Tech] | 31da30d8-d6ea-4d6b-965f-f6bab64a25bf       |

---
