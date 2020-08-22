# How to Setup Tests

## Setup Procedure

This procedure describes how to setup documentation. The project name, `TEMPLATE`, used in this procedure is a placehold and should be replaced. (Capitalization of `TEMPLATE` is only used for emphasis.)

### 1. Install pytest

Make sure the correct virtual environment is active.

```bash
$ pip install -U pytest
$ pytest --version        # verify the installation
```

### 2. Create `tests` directory

```bash
$ # change to the root directory of the project repository
$ mkdir tests
```

### 3. Create test modules

Create all tests within the `tests` directory.

## Workflow

* Create all tests in the `tests` directory
* From the root directory of the project repository, run the tests

```bash
$ # change to the root directory of the project repository
$ python -m pytest
```

## Directory Structure

The final directory structure looks like the following. Files and directories not related to testing are not shown.

```
TEMPLATE/              # project repository
├── TEMPLATE/          # main python package
│   ├── __init__.py    # python module package file
│   └── app.py         # main application program
└── tests/             # test source directory
    └── test_app.py    # test modules, contains tests against app.py
```
