# CI/CD Demo

A simple Python project demonstrating **CI/CD using GitHub Actions and GitHub Pages**.

## Project Structure

```text
cicd-demo/
├── .github/
│   └── workflows/
│       └── pipeline.yml
├── site/
│   └── index.html
├── app.py
├── test_app.py
└── README.md
```

## What This Project Does

* Runs automated tests using **pytest**
* Uses **GitHub Actions** for CI/CD
* Generates an HTML page using Python
* Deploys the website automatically to **GitHub Pages**

## CI/CD Pipeline

The workflow performs these steps:

1. Checks out the code
2. Sets up Python 3.12
3. Installs pytest
4. Runs the tests
5. Generates the website
6. Uploads the website as a GitHub Pages artifact
7. Deploys the website to GitHub Pages

## Testing

The project contains tests for:

* `add()` function
* `is_even()` function

To run the tests locally:

```bash
pip install pytest
pytest
```

## GitHub Pages

After a successful deployment, the website can be accessed from:

**Settings → Pages**

GitHub will display:

> Your site is live at: ...

## CI/CD Test

To test the CI/CD pipeline, change the following in `app.py`:

```python
return a + b
```

to:

```python
return a - b
```

Push the changes to GitHub. The tests will fail because:

```python
assert add(2, 3) == 5
```

After changing it back to:

```python
return a + b
```

and pushing again, the tests should pass and the deployment can proceed.
