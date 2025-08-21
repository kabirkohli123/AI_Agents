# Research Notes – Signal Discovery Agent

## Objective
The goal of this research was to design an agent that can automatically extract meaningful signals from resumes and transform unstructured PDF data into structured features.

---

## Problem Statement
Recruiters often deal with large numbers of resumes in varied formats. Manual parsing is slow and error-prone. An AI agent was needed to:
- Handle PDF resumes as input.
- Extract skills, education, and important keywords.
- Map these into structured categories for downstream applications.

---

## Research & Experiments

### 1. PDF Parsing Approaches
- **PyMuPDF (fitz)** was initially tested but caused version conflicts in Colab.
- **pdf2image + pytesseract OCR** was tested but required Poppler and slowed processing.
- **pdfplumber** was chosen for its reliability in extracting text from text-based PDFs.

### 2. Skills & Education Extraction
- A rule-based regex + keyword list approach was implemented.
- Example: `"Python"` → detected as skill; `"Bachelor of Technology"` → detected as education.
- Future enhancement: use **spaCy NER** for robust entity extraction.

### 3. Categories & Tokenization
- Extracted keywords were mapped into broader categories (e.g., Python → Tech).
- An **Integrity Token** (UUID) was added to ensure uniqueness per resume record.

---

## Key Insights
- Text-based resumes are straightforward to process with pdfplumber.
- Keyword-based extraction is fast but limited in coverage.
- Scanned resumes still require OCR as fallback.
- The agent forms a strong foundation for resume → job description matching in later stages.

---

## Next Steps
- Integrate **NER models** (spaCy, transformer-based) for better accuracy.
- Allow **job description input** and match resumes to JD requirements.
- Expand categories beyond tech into business, design, etc.
- Deploy agent as an API for HR pipelines.

---
