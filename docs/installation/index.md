---
icon: material/cog-box
---

# :material-cog-box: Installation & Setup

## Requirements

EasyDiffraction is a multi-platform Python library compatible with **Python
3.9 through 3.12**. Ensure Python is installed
on your system before proceeding with the installation.

## Environment setup <small>optional</small> { #environment-setup data-toc-label="Environment setup" }

We recommend using a **virtual environment** to isolate dependencies and avoid
conflicts with system-wide packages. If issues arise, you can simply delete and
recreate the environment.

#### Creating and Activating a Virtual Environment:

- Create a new virtual environment:
  ```console
  python3 -m venv venv
  ```
<!-- prettier-ignore-start -->
- Activate the environment:

    === ":material-apple: macOS"
        ```console
        . venv/bin/activate
        ```
    === ":material-linux: Linux"
        ```console
        . venv/bin/activate
        ```
    === ":fontawesome-brands-windows: Windows"
        ```console
        . venv/Scripts/activate      # Windows with Unix like shells
        .\venv\Scripts\activate.bat  # Windows with CMD
        .\venv\Scripts\activate.ps1  # Windows with Power shell
        ```
<!-- prettier-ignore-end -->
- The terminal should now show `(venv)`, indicating that the virtual
  environment is active.

#### Deactivating and Removing the Virtual Environment:

- Exit the environment with:
  ```console
  deactivate
  ```
<!-- prettier-ignore-start -->
- If this environment is no longer needed, delete it:

    === ":material-apple: macOS"
        ```console
        rm -rf venv
        ```
    === ":material-linux: Linux"
        ```console
        rm -rf venv
        ```
    === ":fontawesome-brands-windows: Windows"
        ```console
        rmdir /s /q venv
        ```
<!-- prettier-ignore-end -->

## Installation guide

### Installing from PyPI <small>recommended</small> { #from-pypi data-toc-label="Installing from PyPI" }

EasyDiffraction is available on **PyPI (Python Package Index)** and
can be installed using `pip`. It is advised to install it within a virtual
environment, as outlined in the previous section
[Environment setup](#environment-setup).

We recommend installing the latest release of EasyDiffraction with the
`charts` extras, which include optional dependencies used for simplified
visualization of charts and tables. This can be especially useful for running
the Jupyter Notebook examples. To do so, use the following command:

```console
pip install 'easydiffraction[charts]'
```

If only the core functionality is needed, the library can be installed simply
with:

```console
pip install easydiffraction
```

To install a specific version of EasyDiffraction, e.g. 1.0.3:

```console
pip install 'easydiffraction==1.0.3'
```

Upgrading to the latest version can be done with:

```console
pip install --upgrade --force-reinstall easydiffraction
```

To check the installed version:

```console
pip show easydiffraction
```

### Installing from GitHub

Installing an unreleased version is generally not recommended but can be useful
for testing purposes.

To install EasyDiffraction from, e.g., the `develop` branch of GitHub:

```console
pip install git+https://github.com/easyscience/EasyDiffractionLib@develop
```

To include extra dependencies (e.g., charts):

```console
pip install 'easydiffraction[charts] @ git+https://github.com/easyscience/EasyDiffractionLib@develop'
```

## Running tutorials

EasyDiffraction provides a collection of **Jupyter Notebook examples** that
demonstrate various functionalities. These tutorials are available in the
[:material-school: Hands-on tutorials](../tutorials/index.md) section of the
documentation.

You can also run these tutorials:

- **Locally on your machine**
- **Online via Google Colab** (no local installation required)

These Jupyter Notebook examples can be downloaded either one by one from the
[:material-school: Hands-on tutorials](../tutorials/index.md) section or all
together as a zip archive from the
[EasyDiffraction releases](https://github.com/easyscience/EasyDiffractionLib/releases/latest).

### Run tutorials locally

To run tutorials locally, install Jupyter Notebook or JupyterLab.
Here are the steps to take in the case of Jupyter Notebook:

- Install Jupyter Notebook:
  ```console
  pip install notebook
  ```
- Download the latest EasyDiffraction tutorial examples from GitHub, e.g.,
  using curl:
  ```console
  curl --location --remote-name https://github.com/easyscience/EasyDiffractionLib/releases/latest/download/examples.zip
  ```
- Unzip the archive:
  ```console
  unzip examples.zip
  ```
- Run Jupyter Notebook server in the `examples/` directory:
  ```console
  jupyter notebook examples/
  ```
- Open your web browser and go to:
  ```console
  http://localhost:8888/
  ```
- Select one of the `*.ipynb` files.

### Running tutorials via Google Colab

**Google Colab** allows you to run Jupyter Notebooks in the cloud without any
local installation.

To use Google Colab:

- Ensure you have a **Google account**.
- Navigate to the
  **[:material-school: Hands-on tutorials](../tutorials/index.md)** section of
  the documentation.
- Click the :google-colab: **Open in Google Colab** button available for each
  tutorial.

This method allows you to experiment with EasyDiffraction tutorials
instantly, without setting up a Python environment on your system.
