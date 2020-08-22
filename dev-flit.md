# How to Setup Flit

## Setup Procedure

### 1. Install Flit

Make sure the correct virtual environment is active.

```bash
$ pipenv install flit
$ flit --version # verify the installation
```

### 2. Initialize Flit

Run the init command and answer the prompts. This will create `pyproject.toml` file.

```bash
$ flit init
```

### 3. Configure Flit

Create/edit the file `~/.pypirc` with the following text.

```
index-servers =
   pypi
   testpypi

[pypi]
repository = https://upload.pypi.org/legacy/
username = aracnid

[testpypi]
repository = https://test.pypi.org/legacy/
username = aracnid
```

### 4. Publish to TestPyPI

Register an account on TestPyPI.

```bash
$ flit publish --repository testpypi
```

### 5. Install package locally

Install the package locally in editable mode.

```bash
$ flit install --symlink
```
