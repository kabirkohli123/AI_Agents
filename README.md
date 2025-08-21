# AI Tools and Research Agents 🚀

This repository contains two AI-powered agents developed as part of the internship assignment:  

1. **GitHub Agent** → Fetches developer repositories from GitHub and analyzes activity trends.  
2. **Signal Discovery Agent** → Processes resumes to extract skills, education, keywords, and categories.  

Each agent is modular and can be run independently with its own design and documentation.  

---

## 📂 Repository Structure
├── part1_github_agent/
│ ├── AGENT_DESIGN.md # Design document for GitHub Agent
│ ├── github_agent.ipynb # Python implementation
│ ├── developers.csv # Input dataset of GitHub usernames
│ └── README.md # Usage guide for GitHub Agent
│
├── part2_signal_discovery/
│ ├── RESEARCH.md # Research notes
│ ├── AGENT.md # Design document for Signal Discovery Agent
│ ├── signal_discovery.ipynb # Python implementation
│ ├── requirements.txt # Dependencies
│ └── README.md # Usage guide for Signal Discovery Agent

---

## 🧑‍💻 Agents Overview

### 1️⃣ GitHub Agent
- **Goal**: Fetch developer repositories and analyze activity trends.  
- **Input**: `developers.csv` (list of GitHub usernames).  
- **Output**: CSV with repo count, top language, total stars, and integrity tokens.  
- **Docs**: [part1_github_agent/README.md](part1_github_agent/README.md)  

---

### 2️⃣ Signal Discovery Agent
- **Goal**: Extract skills, education, keywords, and categories from resumes.  
- **Input**: Resume PDFs or CSV dataset.  
- **Output**: `processed_resumes.csv` with structured fields.  
- **Docs**: [part2_signal_discovery/README.md](part2_signal_discovery/README.md)  

---

## ⚡ Setup & Installation
Clone the repo and navigate into it:
```bash
git clone https://github.com/kabirkohli123/AI_Agents.git
cd AI_Agents

```
Install dependencies for each agent:

## For Signal Discovery Agent
```bash
pip install -r part2_signal_discovery/requirements.txt
```

▶️ Running the Agents
## GitHub Agent
```bash
cd part1_github_agent
python Github_Agent.ipynb
```

## Signal Discovery Agent
```bash

cd part2_signal_discovery
python Pignal_Discovery_AI_Agent.ipynb
```
## 📌 Future Improvements
1.) GitHub Agent → Add commit activity & collaborator graphs.
2.) Signal Discovery Agent → Improve NLP for skills/education extraction and add resume-job matching.

✨ Author
Developed by Kabir Kohli as part of an AI Internship Assignment.
