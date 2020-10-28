# How to Setup Pylint

## Setup Procedure

### 1. Install pylint

```bash
$ pip install pylint
```

### 2. Create RC File

```bash
pylint --generate-rcfile > ~/.pylintrc
```

### 3. Edit configuration

Add `logging-fstring-interpolation` to the disable list.

## Usage

Wildcards are acceptable.

```bash
$ pylint <file>
```
