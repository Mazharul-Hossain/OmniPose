# Setup the Environment

Setup the code base first.

    git clone <https://github.com/bmartacho/OmniPose.git>

## Setup env

Create Conda environment.

    conda create -n torchEnv python=3.11

    To activate this environment, use
    $ conda activate torchEnv

    To deactivate an active environment, use
    $ conda deactivate

## Add MS Dev tools to path

Search google to to find "vs c++ redistributable". This is the official website for latest version: <https://visualstudio.microsoft.com/downloads/>.  
As the original code, I downloaded old Microsoft Visual Studio 2019 from here: <https://visualstudio.microsoft.com/vs/older-downloads/>, and installed VS Dev tools 2019, version 16.11.36. Search individual component "vs c++ redistributable".  
Even older versions can be found here: <https://learn.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170>

If VS code can not find Dev tools. Add BuildTools to system environment. "C:\Program Files (x86)\Microsoft Visual Studio\2019\BuildTools\"

## Update conda and pip

    conda update -n base -c defaults conda
    python -m pip install --upgrade  pip

## Install torch

Follow your way from here: <https://pytorch.org/get-started/locally/>

    python -m pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
    conda install tensorboard
    python -m pip install tensorboardX
    python -m pip install torch-tb-profiler

## Install other requirements

    python -m pip install opencv-python
    python -m pip install matplotlib
    python -m pip install Cython
    python -m pip install yacs tqdm json-tricks
    python -m pip install scipy

## Install pycocotools

Follow your way from here: <https://stackoverflow.com/a/56722306/2049763>

    python -m pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI

## Run the Demo

    python inference.py --cfg=experiments/coco/omnipose_w48_384x288.yaml

## Run the test

    python test.py --cfg=experiments/coco/omnipose_w48_384x288.yaml

## Run the training

    python train.py --cfg=experiments/coco/omnipose_w48_384x288.yaml
