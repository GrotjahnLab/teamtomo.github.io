# Autolamella

Autolamella is a {doc}`Python<computing/python>` program that uses the Thermo Fisher Autoscript 4 API to control TFS DualBeam (FIB/SEM) instruments for automating and accelerating the preparation of "lamellae", which are thin vitreous sections of cells that can be used for in situ cryo-ET.

## Installation
Installation is covered with excellent detail in the [autolamella github](https://github.com/DeMarcoLab/autolamella/blob/master/INSTALLATION.md), but to make things as explicit as possible, the following is a complete set of steps to get a functioning Autolamella installation on a support PC in a two-computer Support/Microscope PC setup for an Aquilos.

```{warning}
Single computer installs should work with the same set of steps, just doing everything on one computer. However, this is not tested by the author.
```

1. Install Autoscript server on the microscope PC with the CD installer.
2. Install Autoscript client on the support PC with the CD installer and verify the connection between the two in the system tray.
3. Prepare a {doc}`Python<computing/python>` 3.7 environment with the necessary packages set up:
	1. Install [miniconda](https://docs.conda.io/en/latest/miniconda.html) for windows.
	2. Open an Anaconda Python prompt and generate a new python environment with python 3.7: `conda env create -n autolam python=3.7 pip`
	```{note}
	More details about setting up python and conda environments can be found in the [Python computing tutorial](/computing/python/getting-started)
	```
	3. Copy all autoscript folders from `C:\Program Files\Python35\envs\Autoscript\Lib\site-packages` to `C:\Users\username\.conda\envs\autolam\Lib\site-packages`
	```{admonition} Example list of folders to copy
	:class: dropdown
	* autoscript_core
	* autoscript_core-5.4.1.dist-info
	* autoscript_sdb_microscope_client
	* autoscript_sdb_microscope_client_tests
	* autoscript_sdb_microscope_client_tests-4.2.2.dist-info
	* autoscript_sdb_microscope_client-4.2.2.dist-info
	* autoscript_toolkit
	* autoscript_toolkit-4.2.2.dist-info
	* thermoscientific_logging
	* thermoscientific_logging-5.4.1.dist-info
	```
4. Activate the autolamella environment: `conda activate autolam`
5. Download the latest [release](https://github.com/DeMarcoLab/autolamella/releases)
6. Navigate the activated prompt to the unzipped release folder and install autolamella: `pip install -r autolamella-0.1.5-py2.py3-none-any.whl`
7. Download and configure a protocol yml file. For mammalian cells, a [sample protocol](configs/grotjahn_protocol.yml) is included.
8. Run autolamella in this prompt: `autolamella grotjahn_protocol.yml`

### Useful Links
* [Autolamella Github](https://github.com/demarcolab/Autolamella)
* [Autolamella Paper](https://www.sciencedirect.com/science/article/abs/pii/S104784772030054X)
* [de Marco Lab](https://www.demarco-lab.com/)
* [Download a Sample Autolamella Protocol File for Mammalian Cells](./configs/grotjahn_protocol.yml)
* [Thermo Fisher Autoscript](https://www.thermofisher.com/us/en/home/electron-microscopy/products/software-em-3d-vis/autoscript-4-software.html)

### Citation
Genevieve Buckley, Gediminas Gervinskas, Cyntia Taveneau, Hariprasad Venugopal, James C. Whisstock, Alex de Marco,
**Automated cryo-lamella preparation for high-throughput in-situ structural biology**,
*Journal of Structural Biology*,
Volume 210, Issue 2,
2020
https://doi.org/10.1016/j.jsb.2020.107488.

#### Guide Contributors
Benjamin Barad](mailto:benjamin.barad@gmail.com)
