# DeepSonic

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

An alpha barebones version of the DeepSonic website. You can visit DeepSonic at deepsonic.ml or https://deepsonic.herokuapp.com

DeepSonic is a fully open source Deep Learning music experiment that is capable of synthesizing, generating, remixing, modifying music, all using the power of AI. Thanks to powerful open-source libraries such as Magenta by Tensorflow/Google and Jukebox by OpenAI, we were able to create a multi-functional AI Audio Engineer. 

Note: This notebook runs all code natively. No cloud service is required unless you do not have a dedicated Nvidia GPU.

# Basic Hardware Requirements and Recommendations

The DeepSonic Experiment requires considerably powerful hardware. 

An NVIDIA Geforce RTX 2000 (Turing) Series GPU with 8GB of VRAM is required, at the least. A cloud-based NVIDIA Tesla or a server NVIDIA Quadro GPU with atleast 16GB VRAM is recommended, while a supercomputer will perform best, depending on the task. There are no explicit CPU requirements for DeepSonic, however, an AMD Ryzen 3 3200 or Intel Core i3 8100 (or higher) is recommended. The more powerful, the better.

# How to get started?

To get started with DeepSonic, all you have to do is install Magenta and Jukebox from their official GitHub repositories.

# Quick Install Guide:

Run the follow code in your shell (taken from the official Magenta and Jukebox wiki) to install the required tools. We recommend using a Debian-based operating system. The Windows Subsystem for Linux (WSL2) and Windows didn't appear to work at the time of our testing, possibly due to early support for Cuda on WSL. Also note: root privileges are required for installing audio libraries.

```bash
# Required commands:

sudo apt-get update && sudo apt-get install build-essential libasound2-dev libjack-dev portaudio19-dev
curl https://raw.githubusercontent.com/tensorflow/magenta/main/magenta/tools/magenta-install.sh > /tmp/magenta-install.sh
bash /tmp/magenta-install.sh
conda create --name jukebox python=3.7.5
conda activate jukebox
conda install mpi4py=3.0.3 # if this fails, try: pip install mpi4py==3.0.3
conda install pytorch=1.4 torchvision=0.5 cudatoolkit=10.0 -c pytorch
git clone https://github.com/openai/jukebox.git
cd jukebox
pip install -r requirements.txt
pip install -e .
conda install av=7.0.01 -c conda-forge 
pip install ./tensorboardX
 
# Following two commands are optional: Apex for faster training with fused_adam 

conda install pytorch=1.1 torchvision=0.3 cudatoolkit=10.0 -c pytorch
pip install -v --no-cache-dir --global-option="--cpp_ext" --global-option="--cuda_ext" ./apex
```
