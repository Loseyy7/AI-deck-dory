# AI-deck-dory
Deploy MV2 in DORY-examples to bitcraze AI deck.


## 1. Install dory
(https://github.com/pulp-platform/dory)

git clone https://github.com/pulp-platform/dory

## 2. Install dory_examples
(https://github.com/pulp-platform/dory_examples)

git clone https://github.com/pulp-platform/dory_examples

** put it into /dory/dory/dory_examples

cd dory

git submodule update --remote --init dory/dory_examples

git submodule update --remote --init dory/Hardware_targets/PULP/Backend_Kernels/pulp-nn

git submodule update --remote --init dory/Hardware_targets/PULP/Backend_Kernels/pulp-nn-mixed

python3 -m pip install -e .

** If an error about setuptools is reported, modify setup.py

** import setuptools # add this line in setup.py

## 3. Deploy the example

python3 network_generate.py Quantlab PULP.GAP8 \

  ./dory/dory_examples/config_files/config_Quantlab_MV2_8bits.json \
  
  --app_dir ./application_mv2


docker run --rm -it \ -v $PWD:/module \ -w /module \ bitcraze/aideck \ bash -c " export GAP_SDK_HOME=/gap_sdk && \ export GAP_TARGET=GAPOC_B_V2 && \ source /gap_sdk/configs/gapoc_b_v2.sh && \ make clean all platform=gvsoc CORE=8 "

*Use crazyradio to connect

cfloader flash \ BUILD/GAP8_V2/GCC_RISCV_PULPOS/main \ deck-bcAI:gap8-fw \ -w radio://0/80/2M/E7E7E7E7E7




