# Lattice-Distortion

Release: [![PyPI](https://img.shields.io/pypi/v/pqam-rmsadtandoc2023)](https://pypi.org/project/pqam-rmsadtandoc2023)

Compatible with: [![PyPI - Python Version](https://img.shields.io/pypi/pyversions/pqam_RMSADTandoc2023)](https://pypi.org/project/pqam_RMSADTandoc2023)

Tests: [![small runtime test](https://github.com/amkrajewski/pqam_RMSADTandoc2023/actions/workflows/runtimeTesting.yml/badge.svg)](https://github.com/amkrajewski/pqam_RMSADTandoc2023/actions/workflows/runtimeTesting.yml)

License: [![License: LGPL v3](https://img.shields.io/badge/License-LGPL_v3-blue.svg)](https://www.gnu.org/licenses/lgpl-3.0)

## This Fork

This small repository is a lightweight fork (with extra checks) version of the original one by Tandoc. It is only slightly modified to fit automated pipelines of the [ULTERA Database (ultera.org)](https://ultera.org) infrastrcutre, which expects `model.py` script with `predict(comp: pymatgen.Composition)` and `predict(comp: str)` function returning an ordered array of output numbers or a labeled dictionary of them corresponding to the machine-readible definition under `outputDefinition.json`.

Chemical Space: `["Ti", "Zr", "Hf", "V", "Nb", "Ta", "Mo", "W", "Re", "Ru"]`

Output Order: [`rmsad_Tandoc2023`]

Output Meaning (all based on [10.1038/s41524-023-00993-x](https://doi.org/10.1038/s41524-023-00993-x)):
- `rmsad_Tandoc2023` - Root Mean Squared Atomic Displacement in the units of Angstrom

## Install and Use

There are no dependencies beyond a fairly recent pymatgen (>=2022.1.9). You need to simply

    pip install pqam-rmsadtandoc2023

and you should be good to go! Then you can run it on your compositions in Python like

    from pqam-rmsadtandoc2023 import predict
  
    print(predict('Mo25 Nb25 Hf50'))
    print(predict('MoNbHf'))
    print(predict('Mo33.3 Nb33.3 Hf33.3'))
  
or from command line like 

    python -c "import pqam_rmsadtandoc2023 as m;print(m.predict('Mo25 Nb25 Hf50'));print(m.predict('MoNbHf'));print(m.predict('Mo33.3 Nb33.3 Hf33.3'))"
  

## Original README by Tandoc 

>This repository contains relevant code and data for "Mining lattice distortion, strength, and intrinsic ductility of refractory high-entropy alloys using physics-informed >statistical learning" by Christopher Tandoc, Yong-Jie Hu, Liang Qi, and Peter K. Liaw to be published in npj Computational Materials
>
>RMSAD_tool.py is a linux command line script written in python that takes a chemical composition in the form of a text string and prints the lattice distortion in angstroms. 
>
>example usgage: 
>./RMSAD_tool.py Ti0.5V0.5
>
>-This script uses pymatgen (https://pymatgen.org/) to process the input string and is thus a requirement for the script to work. Depending on the version of pymatgen you have >installed, lines 3 and 380 may need to be modified (https://matsci.org/t/python-problem-with-pymatgen/35720)
>-numpy (https://numpy.org/) is also a dependency
>-This tool is currently only able to make predictions for compositions containing Ti,Zr,Hf,V,Nb,Ta,Mo,W,Re,Ru and will return an error if any other elements are present in >the input
>-B2 and elemental feature data are defined in dictionaries at the beginning of the code
>
>training.ipynb and training_data.csv contains code and data to reproduce the rmsad model training that was performed in the paper
>-jupyter notebook is needed to open training.ipynb, dependencies are numpy, pymatgen, matplotlib (https://matplotlib.org/), pandas (https://pandas.pydata.org/), and >sklearn(https://scikit-learn.org/stable/)

## Miscellaneous

Last maintenance check: January 22nd, 2024
