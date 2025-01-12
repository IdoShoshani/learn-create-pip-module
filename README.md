# Learn-Create-Pip-Module

A guide to building and publishing a Python module to PyPI.

## Project Structure

```
.
├── LICENSE
├── README.md
├── calculator
│   ├── __init__.py
│   └── calculator.py
├── main.py
└── setup.py
```

## Files and Directories

- **LICENSE**: Contains the license information for your project.
- **README.md**: This file contains information about the project, usage instructions, and contribution guidelines.
- **calculator/**: This is the package directory containing the module files.
  - `__init__.py`: Makes the directory a Python package.
  - `calculator.py`: Contains the core logic of the module.
- **main.py**: Entry point script for the project (used for testing or execution).
- **setup.py**: Contains metadata and instructions for building and publishing the module.

## Setup Instructions

### 1. Install Required Tools

Ensure you have Python 3.6+ installed and `pip` for managing packages.

### 2. Write Your Module Code

Define your module's core logic in `calculator.py`. Include functions or classes as necessary for your module's functionality.

### 3. Define Package Metadata in `setup.py`

`setup.py` is crucial for building your pip module. Example:

```python
from setuptools import setup, find_packages

setup(
    name="calculator",  # Package name
    version="0.1.0",    # Version
    author="Your Name",
    author_email="your.email@example.com",
    description="A simple calculator module",
    long_description=open("README.md").read(),
    long_description_content_type="text/markdown",
    url="https://github.com/yourusername/calculator",  # Replace with your repo URL
    packages=find_packages(),
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires=">=3.6",
)
```

### 4. Prepare for Distribution

Run the following commands to prepare your package:

```bash
pip install setuptools wheel
python setup.py sdist bdist_wheel
```

This generates a `dist/` directory with distribution files.

### 5. Publish to PyPI

Install `twine` for uploading:

```bash
pip install twine
```

Upload your package to PyPI:

```bash
twine upload dist/*
```

### 6. Install Your Package

Once published, you can install your module via pip:

```bash
pip install calculator
```

## Testing Locally

You can test the module locally before publishing:

```bash
pip install .
```

Run the `main.py` file to verify functionality.

## Contribution

Feel free to contribute by forking the repository, making changes, and submitting a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
