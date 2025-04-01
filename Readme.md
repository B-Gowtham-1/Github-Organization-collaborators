# GitHub Repository Read Access Checker

This script lists all users with read access to a given GitHub repository.

## Prerequisites

- A **GitHub personal access token (PAT)** with the necessary permissions to access repository collaborators.
- **`jq`** installed on your system (used for JSON parsing).
- **cURL** installed (used for API requests).

## Installation

1. Clone this repository or download the script.
2. Ensure the script has execution permissions:
   ```bash
   chmod +x script.sh
   ```

## Usage

Run the script with the following command:

```bash
./script.sh <REPO_OWNER> <REPO_NAME>
```

### Example Usage

```bash
export username="your-github-username"
export token="your-personal-access-token"
./script.sh octocat Hello-World
```

### Explanation
- `REPO_OWNER`: The owner of the repository (e.g., `octocat`).
- `REPO_NAME`: The name of the repository (e.g., `Hello-World`).

## Expected Output
If users with read access are found, the output will be:

```
Listing users with read access to octocat/Hello-World...
Users with read access to octocat/Hello-World:
user1
user2
```

If no users with read access are found, it will display:

```
No users with read access found for octocat/Hello-World.
```

## Notes
- Ensure that your GitHub personal access token has the `repo` scope for private repositories or `public_repo` scope for public repositories.
- The script uses basic authentication (`USERNAME:TOKEN`), which is deprecated for API requests. Consider using a token in the `Authorization` header for better security.

## Troubleshooting
- If you get an authentication error, ensure your GitHub credentials (username and token) are correct.
- If `jq` is not installed, install it using:
  - Ubuntu/Debian: `sudo apt install jq`
  - macOS: `brew install jq`
  - Windows: Download from [https://stedolan.github.io/jq/download/](https://stedolan.github.io/jq/download/)



