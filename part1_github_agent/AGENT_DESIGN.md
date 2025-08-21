# AGENT_DESIGN.md

## Agent Name
**GitHub Agent**

## Role
Analyze developer activity on GitHub by fetching repository data and extracting insights.

## Goal
- Fetch developer repositories (via GitHub API).
- Analyze activity trends (languages used, stars, forks, repo counts, last update times).
- Generate structured outputs with integrity tokens for traceability.

## Backstory
This agent is designed as part of an internship assignment. Its purpose is to simulate an intelligent assistant that helps organizations quickly assess developer activity and skill areas by leveraging open GitHub data. By combining data fetching, trend analysis, and structured reporting, the GitHub Agent acts like a research analyst specialized in GitHub ecosystem insights.

## Inputs
- **developers.csv**: A CSV file containing GitHub usernames (column: `username`).
- **GitHub Personal Access Token** *(optional)*: To authenticate requests and avoid API rate limits.

## Outputs
- **KPIs per developer**:
  - `Repos_Fetched` → Number of repos successfully fetched
  - `Top_Language` → Most used programming language
  - `Total_Stars` → Sum of stars across repos
  - `Repo_Count` → Number of repositories
  - `Integrity_Token` → UUID for traceability

- **CSV Export**:
  - `github_results.csv` containing structured insights

## Tasks
1. **Fetch GitHub Repositories**
   - Input: `username`, `token` (optional)
   - Fetches all public repos via GitHub API.

2. **Analyze Activity Trends**
   - Input: Repository metadata
   - Output: Top language, total stars, repo count

3. **Generate Integrity Token**
   - Assigns a UUID to each record for reproducibility and validation.

## Example Output
| Developer      | Repos_Fetched | Top_Language      | Total_Stars | Repo_Count | Integrity_Token                           |
|----------------|---------------|-------------------|-------------|------------|--------------------------------------------|
| torvalds       | 6             | C                 | 125000      | 6          | 8b8a0d30-6e8b-4b4e-b5a7-732a3b5c222d       |
| guido          | 3             | Python            | 28000       | 3          | 213bc839-7a9b-4aa4-982d-9946c1ab09d2       |

## Future Extensions
- Support for private repos with OAuth tokens.
- Network graph analysis of collaborators.
- Repo-level time series of commits.
- Integration with other agents (e.g., resume analysis).
