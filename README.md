# FP8-Transformer
- Study of FP8 quantization for BERT-tiny

Based on the use of FP8 emulation toolkit from INTEL: https://github.com/IntelLabs/FP8-Emulation-Toolkit.git  
Also check: https://github.com/intel/neural-compressor.git

## Installation
It is suggested to follow the instructions for the FP8 emulation toolkit from INTEL.  
Requirements from INTEL:
- Linux Machine
  - For Windows, we can use WSL: https://canonical-ubuntu-wsl.readthedocs-hosted.com/en/latest/guides/install-ubuntu-wsl2/
- Python >= 3.8.5
- NVIDIA CUDA >= 11.1 or AMD ROCm >= 5.6
- gcc >= 8.4.0

Here, we only give details of our specific environment implementation:
1. Create the conda environment and activate it:  
   `conda create --name fp8_env python=3.10.12`  
   `conda activate fp8_env`
2. Install PyTorch with CUDA:  
   `conda install pytorch==2.1.0 torchvision==0.16.0 torchaudio==2.1.0 pytorch-cuda=12.1 -c pytorch -c nvidia`
  2.1 For WSL CONDA need to be installed there too: https://docs.nvidia.com/cuda/wsl-user-guide/index.html and https://developer.nvidia.com/cuda-12-1-0-download-archive?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_network  
5. Install git:  
   `conda install git`
6. Clone FP8 emulation toolkit repo:  
   `git clone https://github.com/IntelLabs/FP8-Emulation-Toolkit.git`
7. Install FP8 emulation toolkit requirements:  
   `cd FP8-Emulation-Toolkit`    
   `pip install -r requirements.txt`  
   `python setup.py install`  
   `conda install conda-forge::tensorboard`  
   `conda install conda-forge::tqdm`  
8. Install requirements to use Transformers (HuggingFace):  
   `pip install -q transformers`  
   `pip install -q datasets`  
   `pip install accelerate -U`  
   `pip install ipywidgets`
9. Binary fractions for test vector generation: https://pypi.org/project/binary-fractions/  
   `pip install binary-fractions`  
10. Clone this repo:  
   `git clone https://github.com/asbc19/FP8-Transformer.git`

## Examples
1. `INTEL_emulator/tutorial_0/fp8_tutorial.ipynb`  
   Jupiter notebook to verify the emulator installation and basic capabilities.
2. `INTEL_emulator/example_modified/bert/`  
   Modified example from INTEL to run inference on the whole dataset using BERT-tiny.
   - SQUAD2 dataset is required -> check `README.md` in the corresponding folder.
   - Use the `bash` command to run any of the options: `cmd_inferTiny.sh`, `cmd_inferTiny_e4m3.sh`, etc.
3. `INTEL_emulator/fp8_application/bert_tiny_selfatt.ipynb`  
   Jupiter notebook to reproduce the self-attention layer of BERT-tiny to obtain intermediate feature maps.
   - Use INTEL emulator for quantization.
4. `INTEL_emulator/fp8_application/simple_inference.ipynb`  
   Jupiter notebook to perform inference of simple networks using INTEL emulator.
5. `fp16_test/test_vector.ipynb`    
   Jupiter notebooks to generate test vectors for reconfigurable accumulator testbench.
5. `fp8_test/test_vector.ipynb`    
   Jupiter notebooks to generate test vectors for BERT-tiny self-attention layer testbench.
