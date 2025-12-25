# AI-deck-dory
Deploy MV2 in DORY-examples to bitcraze AI deck.


1. Install dory
(https://github.com/pulp-platform/dory)
git clone https://github.com/pulp-platform/dory
cd dory
git submodule update --remote --init dory/dory_examples
git submodule update --remote --init dory/Hardware_targets/PULP/Backend_Kernels/pulp-nn
git submodule update --remote --init dory/Hardware_targets/PULP/Backend_Kernels/pulp-nn-mixed
python3 -m pip install -e .

If an error about setuptools is reported, modify setup.py
setup.py
from setuptools import setup, Extension
import setuptools # add this
import os

setup(name='dory',
      version='0.1',
      description='A library to deploy networks on MCUs',
      url='https://github.com/pulp-platform/dory/',
      author='Alessio Burrello',
      author_email='alessio.burrello@unibo.com',
      license='MIT',
      packages=setuptools.find_packages(),
	    python_requires='>=3.5',
	    install_requires=[
	        "onnx",
	        "numpy",
              "ortools",
              "mako"
	    ],
      package_data={"": ['Makefile*'], "": ['*.[json,c,h]']},
      include_package_data=True,
      zip_safe=False)

3. 
