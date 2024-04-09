# Project Title

## Introduction
Run machine learning models locally on Raspberry Pi 5 with Coral TPU M.2 Accelerator via PCIE to M.2 hat. 

## Requirements

 **Hardware**

  - Raspberry Pi 5
  - Coral TPU M.2 Accelerator
  - Pineberry Pi Hat AI!

**Software**
  - Raspberry Pi OS (Tested). Potentially compatible with Ubuntu (not yet tested).
  - `pyenv` for managing Python versions, ensuring Python 3.9 is installed and set as the local version for the project (as it is compatible with the PyCorla API and other dependencies.
  - PyCoral API (For interfacing with the Coral TPU. Installation instructions are available in the setup guide.)
  - TensorFlow Lite (Required for running model inferences on the Coral TPU.)
  - Additional Dependencies (Refer to the `requirements.txt` file for a detailed list.)

## Setup and Installation

### Pi Config Changes

  - Confirm current kernel version
	
	`uname -a`

  - Manually edit config.txt to add settings
	
	`sudo nano /boot/firmware/config.txt`

  - Inside nano, add these lines at the end:

	`kernel=kernel8.img`

	`dtparam=pciex1`

	`dtparam=pciex1_gen=2`

  - Save and exit: Ctrl-X, then press Y and Enter

  - Disable ASPM by editing cmdline.txt

	`sudo nano /boot/firmware/cmdline.txt`

  - Add `pcie_aspm=off` before `rootwait`. 

  - Save and exit as above.

  - Reboot to apply changes

	`sudo reboot`

 - Confirm kernel version post-reboot

	`uname -a`

### Pyenv Installation

Provide instructions on how to install `pyenv` and set up the required Python version, including steps to verify the installation.

### Virtual Environment Setup

To create and activate a Python virtual environment for the project, use the following commands:
- Creating a virtual environment: `python3 -m venv coral-env`
- Activating the virtual environment: `source coral-env/bin/activate`

### Dependencies Installation

With the virtual environment activated, install the required Python packages by running:
- `python3 -m pip install --extra-index-url https://google-coral.github.io/py-repo/ pycoral~=2.0`

List all necessary dependencies and how to install them. Include instructions for creating a `requirements.txt` file and using it to install dependencies.

## Running the Application

Detailed instructions on how to run your application, including any necessary command-line arguments or configuration files.

## Troubleshooting

Common issues users might encounter and how to resolve them.


## Credits
TBD
Acknowledge the sources, articles, GitHub comments, and other resources that helped you build your project. You can format this as a list:
- Article or GitHub resource title
- Another helpful resource
