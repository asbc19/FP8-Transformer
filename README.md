# FP8-Transformer
- Study of FP8 quantization for BERT-tiny

Based on the use of FP8 emulation toolkit from INTEL: https://github.com/IntelLabs/FP8-Emulation-Toolkit.git
Also check: https://github.com/intel/neural-compressor.git

## Conda Environment
It is suggested to follow the instructions for the FP8 emulation toolkit from INTEL.  
Requirements from INTEL:
- Linux Machine
  - For Windows, we can use WSL: https://canonical-ubuntu-wsl.readthedocs-hosted.com/en/latest/guides/install-ubuntu-wsl2/
- Python >= 3.8.5
- NVIDIA CUDA >= 11.1 or AMD ROCm >= 5.6
- gcc >= 8.4.0

Here, we only give details of our specific environment implementation:
