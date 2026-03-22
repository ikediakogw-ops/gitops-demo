# GitOps CI Pipeline with Trello Integration

## Project Overview

This project demonstrates a simple **GitOps-based Continuous Integration (CI) workflow** using GitHub Actions integrated with Trello.

The goal is to improve:

- Code quality
- Automation
- Visibility of development progress

Whenever code is pushed to the `main` branch, the pipeline automatically runs checks and updates a Trello card.

---

## Objectives

- Automate code validation using CI
- Prevent broken code from being merged
- Track build status using Trello
- Simulate a real DevOps workflow

---

## Tools & Technologies

| Tool | Purpose |
| --- | --- |
| Node.js | Application runtime |
| GitHub Actions | CI pipeline automation |
| Trello API | Task tracking automation |
| Git | Version control |

---

## Project Structure

```
.
├── .github/workflows/ci.yml
├── app.js
├── app.test.js
├── package.json
├── .gitignore
└── README.md
```

---

## Workflow Explanation

The CI pipeline is triggered on every push to the `main` branch.

### Pipeline Steps

1. Checkout code
2. Setup Node.js environment
3. Install dependencies
4. Run lint checks
5. Run tests
6. Update Trello on success

---

## Trello Integration Setup

### Step 1: Get API Credentials

Visit:

```
https://trello.com/app-key
```

- Copy your API Key
- Generate your Token

---

### Step 2: Get Trello Card ID

From your Trello card URL:

```
https://trello.com/c/ZP108mAz/1-build-status
```

Card ID:

```
ZP108mAz
```

---

### Step 3: Configure GitHub Secrets

In GitHub:

**Settings → Secrets and variables → Actions**

Add:

| Name | Value |
| --- | --- |
| TRELLO_KEY | Your API key |
| TRELLO_TOKEN | Your token |
| TRELLO_CARD_ID | Your card ID |

---

## Running the Project Locally

Install dependencies:

```
npm install
```

Run lint:

```
npm run lint
```

Run tests:

```
npm test
```

---

## Triggering the CI Pipeline

Make a commit and push:

```
git add .
git commit -m "trigger CI"
git push
```

---

## Expected Output

- GitHub Actions workflow runs successfully
- Trello card is updated to:

```
CI Passed - [timestamp]
```

---

## Challenges Encountered

- Google blocking automation during scraping
- Git tracking unwanted files (`node_modules`)
- Trello API requiring correct card ID format

---

## Solutions Implemented

- Switched to direct API integration instead of scraping
- Used `.gitignore` to manage dependencies
- Configured GitHub Secrets for secure API usage

---

## Future Improvements

- Update Trello on build failure
- Move card to “Done” automatically
- Add comments instead of renaming card
- Improve test coverage

---

## Author

**Akogwu Emmanuel Ikedi**

---

## Conclusion

This project demonstrates how CI/CD and task management tools can be integrated to improve development workflow, ensuring better code quality and visibility in a team environment.

