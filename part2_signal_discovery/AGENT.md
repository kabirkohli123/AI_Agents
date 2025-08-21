# Signal Discovery Agent

## Overview
The **Signal Discovery Agent** processes resumes (in PDF format) and extracts structured signals such as **skills, education, keywords, and mapped categories**. It is designed to automate candidate profiling by transforming unstructured resume data into structured datasets for downstream tasks like matching against job descriptions.

---

## Workflow
1. **Input**
   - User uploads one or more resumes in PDF format into the Colab environment.
   - Agent scans the `/content/` folder for `.pdf` files.

2. **Processing**
   - Extracts text from resumes using `pdfplumber` (reliable for text-based PDFs).
   - Applies custom NLP functions:
     - **Skills Extraction** – matches against a predefined skill set.
     - **Education Extraction** – identifies degree names and education references.
     - **Keyword Extraction** – extracts key terms using regex/keyword lists.
     - **Category Mapping** – maps extracted skills/keywords into higher-level categories.

3. **Output**
   - Returns a structured DataFrame with columns:
     - `File` (resume name)
     - `Skills`
     - `Education`
     - `Keywords`
     - `Categories`
     - `Integrity_Token` (unique ID per record)
   - Saves results into a CSV file (`processed_resumes.csv`).

---

## Tools & Libraries
- **pdfplumber** → for reliable PDF text extraction.
- **pandas** → for structured storage of extracted signals.
- **uuid** → for generating unique integrity tokens.
- **custom regex + keyword lists** → for skills, education, and categories.

---

## Example Output

| File                | Skills            | Education         | Keywords          | Categories       | Integrity_Token |
|---------------------|------------------|------------------|------------------|-----------------|-----------------|
| Kabir_resume_3.0.pdf | [Python, ML]     | [B.Tech]         | [AI, Data]       | [Tech, AI]      | 123e4567-e89b   |
| Kabir_resume_AI.pdf  | [SQL, NLP]       | [M.Sc AI]        | [Analytics]      | [Data Science]  | 987f6543-c21b   |

---

## Limitations
- Scanned resumes (image-based) may fail unless OCR is added.
- Current extraction is rule-based (regex/keywords) and may miss contextual info.
- Does not yet compare resumes against job descriptions (future enhancement).
