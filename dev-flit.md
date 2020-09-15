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

## Workflow

Follow this workflow whenever publishing a new version.

1. Set the version number in the `__init__.py` file.
2. Commit this modification to the main branch.
3. Set the `SOURCE_DATE_EPOCH` environment variable to support reproducible builds.

```bash
$ SOURCE_DATE_EPOCH=$(git log -1 --pretty=%ct)
```

4. Push the main branch to GitHub. The following example will push the "main" branch to the remote named "github".

```bash
$ git push github main
```

5. Create a version tag (e.g., "v1.0.0-alpha.1") for the last commit and push the new version tag to GitHub.

```bash
$ git tag <version>
$ git push github --tags
```

6. Publish the code using Flit.

```bash
$ flit publish
```
