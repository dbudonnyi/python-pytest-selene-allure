# Project Title
This project is show ability to run automation tests in **Github Actions** with **Selenoid**.
**Pytest** was choosen as automation framework with **selene** to manipulate UI elements.
Reports are generating with **Allure**.
Testing UI is performed for [Saucedemo](https://www.saucedemo.com/)

## Description
Automation Tests workflow are executing on each pull request or push into *master* branch.
Tests are running with *pytest* in 4 parallel streams with *Selenoid*.
Results of each trigger of workflow can be found by the link - [https://github.com/dbudonnyi/python-pytest-selene-allure/](https://github.com/dbudonnyi/python-pytest-selene-allure/)
Configuration file of workflow - [https://github.com/dbudonnyi/python-pytest-selene-allure/blob/master/.github/workflows/python-app.yml](https://github.com/dbudonnyi/python-pytest-selene-allure/blob/master/.github/workflows/python-app.yml)

## Getting Started (running tests on local machine)

### Requirements
Requirements to run tests on local machine:
* python 3
* modules specified in requirements.txt. Install all modules with command:
 ```
 pip install requirements.txt
 ```
* Allure
* Selenoid

### Running tests on local machine
Command to run tests:
```
pytest tests --alluredir=reports
```
Command to run tests in parallel:
```
pytest tests -n 4 --alluredir=reports
```

### Generate Allure report
To have a history in Allure report, copy *history* folder from *allure-report* folder to *history* folder in *reports* folder before running tests.
Command to copy folder (for Windows):
```
Xcopy allure-report\history reports\history /E /H /C /I
```
Commands to generate report:
```
allure generate --clean reports
allure open allure-report
```