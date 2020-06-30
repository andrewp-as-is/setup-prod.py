<!--
https://readme42.com
-->



[![](https://img.shields.io/badge/OS-Unix-blue.svg?longCache=True)]()
[![](https://img.shields.io/pypi/v/setup-prod.svg?maxAge=3600)](https://pypi.org/project/setup-prod/)
[![](https://img.shields.io/badge/License-Unlicense-blue.svg?longCache=True)](https://unlicense.org/)
[![](https://github.com/andrewp-as-is/setup-prod.py/workflows/tests42/badge.svg)](https://github.com/andrewp-as-is/setup-prod.py/actions)

### Installation
```bash
$ [sudo] pip install setup-prod
```

### Concept
pypi/prod `setup.py` without unnecessary metadata

#### Features
`MANIFEST.in`
```
include requirements.txt
exclude MANIFEST.in
```

#### Examples
```bash
setup-prod > setup.py
```

```python
import setuptools

setuptools.setup(
    name='NAME',
    install_requires=open('requirements.txt').read().splitlines(),
    packages=setuptools.find_packages()
)
```

environment variables
```bash
scripts="$(find scripts -type f)"
export SETUP_NAME="custom-name"
export SETUP_SCRIPTS="$scripts"
setup-prod > setup.py
```

```python
import setuptools

setuptools.setup(
    name='custom-name',
    install_requires=open('requirements.txt').read().splitlines(),
    packages=setuptools.find_packages(),
    scripts=['scripts/file1','scripts/file2']
)
```

<p align="center">
    <a href="https://readme42.com/">readme42.com</a>
</p>