# How to Setup Dotenv

## Setup Procedure

This procedure describes how to setup documentation. The project name, `TEMPLATE`, used in this procedure is a placehold and should be replaced. (Capitalization of `TEMPLATE` is only used for emphasis.)

### 1. Install dotenv

Make sure the correct virtual environment is active.

```bash
$ pip install -U python-dotenv
```

### 2. Create `.env` file

```bash
$ # change to the root directory of the project repository
$ touch .env
```

### 3. Add environment variables to the `.env` file

```bash
# important environment variables
MEANING_OF_LIFE=42
```

### 4. Add `.env` file to `.gitignore`

The `.env` file many contain sensitive credential data; therefore, it shouldn't be version controlled.

### 5. Update main application to load environment variables

If using "pipenv", opening the shell will automatically load the environment variables from the `.env` file. If the `.env` files is modified, reload the environment variables by sourcing the file.

```bash
$ source .env
```

If not using "pipenv", the environment variables can be loaded programatically by adding the following lines to the main application file:

```python
from dotenv import load_dotenv
load_dotenv()
```

## Workflow

N/A

## Directory Structure

The final directory structure looks like the following. Files and directories not related to testing are not shown.

```
TEMPLATE/              # project repository
├── TEMPLATE/          # main python package
│   ├── __init__.py    # python module package file
│   └── app.py         # main application program
└── .env               # dotenv file
```
