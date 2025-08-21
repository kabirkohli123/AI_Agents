# GitHub Agent

## Overview
The **GitHub Agent** fetches repositories from developer profiles and analyzes their activity trends.  
It uses the **GitHub API** to pull repository metadata and summarizes developer insights such as top language, repo count, and total stars.  
This agent is designed as part of the internship assignment to demonstrate agent-based automation for developer activity analysis.  

---

## Features
- Fetch developer repositories from GitHub API.
- Analyze activity trends (top language, total stars, repo count).
- Generate Integrity Tokens for each developer entry.
- Save insights in a structured CSV file.

---

## Input
- **developers.csv** file containing GitHub usernames.  
  Example:
  ```csv
  username
  torvalds
  guido
  octocat
  ```

- **GitHub Token (optional)**: Helps bypass rate limits when fetching repos.  
  Generate a token from [GitHub Developer Settings](https://github.com/settings/tokens).

---

## Output
- **github_results.csv** file with insights for each developer:
  - `Repos_Fetched`
  - `Top_Language`
  - `Total_Stars`
  - `Repo_Count`
  - `Integrity_Token`

---

## Example Output
| Developer      | Repos_Fetched | Top_Language      | Total_Stars | Repo_Count | Integrity_Token                           |
|----------------|---------------|-------------------|-------------|------------|--------------------------------------------|
| torvalds       | 6             | C                 | 125000      | 6          | 8b8a0d30-6e8b-4b4e-b5a7-732a3b5c222d       |
| guido          | 3             | Python            | 28000       | 3          | 213bc839-7a9b-4aa4-982d-9946c1ab09d2       |

---

## How to Run
```bash
pip install -r requirements.txt
python github_agent.py
```

Or run inside Jupyter/Colab with the provided notebook.

---

## Future Extensions
- Repo-level commit activity analysis.
- Collaborator network graphs.
- Private repo support with OAuth.
