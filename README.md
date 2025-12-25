# AI-deck-dory
Deploy MV2 in DORY-examples to bitcraze AI deck.


## 1. Install dory
(https://github.com/pulp-platform/dory)
git clone https://github.com/pulp-platform/dory
cd dory
git submodule update --remote --init dory/dory_examples
git submodule update --remote --init dory/Hardware_targets/PULP/Backend_Kernels/pulp-nn
git submodule update --remote --init dory/Hardware_targets/PULP/Backend_Kernels/pulp-nn-mixed
python3 -m pip install -e .
Fix Setup.py (if needed)

If an error about setuptools is reported, modify setup.py

import setuptools # add this line



