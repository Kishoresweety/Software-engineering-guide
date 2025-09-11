# ⚙️ Continuous Integration & Continuous Delivery (CI/CD)

🔹 Concept

CI/CD is about automating the process of:

1. Building your code


2. Testing it automatically


3. Deploying it to production




👉 Goal: Every change you make should go from code → tested → production smoothly and quickly.


---

🔹 Continuous Integration (CI)

Developers push code frequently (daily or multiple times a day).

Every push triggers:

Build the application

Run automated tests (unit, integration)

Static code checks (linters, security scans)


If something fails → the build is red 🚨 and must be fixed before merging.


✅ CI ensures the main branch is always stable.


---

🔹 Continuous Delivery (CD)

Extends CI → after tests pass, the code is packaged & deployed automatically.

Deployment may be:

Staging environment (for QA/testing)

Production environment (real users)



👉 Continuous Delivery = manual approval before production.
👉 Continuous Deployment = fully automatic to production.


---

🔹 CI/CD Workflow Example

1. Developer commits code → pushes to GitHub.


2. CI/CD tool (GitHub Actions, Jenkins, GitLab CI, CircleCI, Azure DevOps, etc.) runs pipeline:

Step 1: Install dependencies

Step 2: Run unit tests

Step 3: Run integration tests

Step 4: Build Docker image / package

Step 5: Deploy to server or cloud (AWS, Azure, GCP, DigitalOcean, etc.)





---

🔹 Example: GitHub Actions CI/CD

File: .github/workflows/ci.yml

name: CI/CD Pipeline

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.10'

    - name: Install dependencies
      run: |
        pip install -r requirements.txt

    - name: Run Tests
      run: |
        pytest

    - name: Deploy to Server
      if: github.ref == 'refs/heads/main'
      run: |
        echo "Deploying application..."
        # Example: scp files to server or run docker-compose up

✅ This pipeline:

Runs on every push to main.

Tests code with pytest.

Deploys app automatically if tests pass.



---

🔹 Benefits of CI/CD

1. Faster feedback → catch bugs immediately.


2. Higher quality → all code is tested before merging.


3. Less risky deployments → small frequent releases instead of big risky ones.


4. Automation saves time → no manual testing/deployment headache.




---

🔹 Tools for CI/CD

GitHub Actions (easy, free for GitHub projects)

GitLab CI/CD (built-in with GitLab)

Jenkins (self-hosted, very powerful)

CircleCI, Travis CI, Azure DevOps, AWS CodePipeline



---

✅ Summary:

CI = build + test automatically on each commit.

CD = deploy automatically after CI passes.

Together → fast, safe, automated software delivery.


