# GitHubStarMover

**GitHubStarMover** is a Python tool for migrating Star repositories from one GitHub account to another. Using the GitHub API, the tool automates the process of synchronizing all Star repositories from the source account to the target account without having to do it manually, simplifying the migration process.

## Function

- Get a list of Star repositories for the source account.
- Synchronizes the Star repository from the source account to the target account.
- Support loading multiple Star repositories in pages.

## Environmental requirements

- Python 3.x
- The `requests` library: it can be installed via `pip install requests`.

## Installation and use

### 1. Cloning of warehouses

First, clone the project locally:

```bash
git clone https://github.com/CrazyCodingConclave/GitHubStarMover.git
cd GitHubStarMover
```
### 2. Install dependencies

Install the dependencies required by the project:

```bash
pip install requests
```

### 3. Configuring GitHub Tokens

You'll need to create GitHub Personal Access Tokens for both the source and target accounts, and make sure the tokens have `repo` and `user` permissions.

In the `GitHubStarMover.py` file, edit the following configuration:

```python
source_token = 'YOUR_SOURCE_TOKEN' # GitHub token for source account
source_username = 'YOUR_SOURCE_USERNAME' # Username of the source account
target_token = 'YOUR_TARGET_TOKEN' # GitHub token for target account
```

### 4. Run the script

Run the script to synchronize the Star repository from the source account to the target account:

```bash
python GitHubStarMover.py
```

This script will list all Star repositories in the source account and re-Star them in the target account.

### 5. Completion

After the migration is complete, you will see the same repositories in the Star list of the target account as in the source account.

## Notes

- Make sure that the Personal Access Token you generate for both GitHub accounts has sufficient permissions, especially the permissions needed to Star the repository.
- If you have a large number of repositories, you may request the GitHub API multiple times, so it is recommended to keep an eye on the API request limits.
