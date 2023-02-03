293.51U is FLAIR UNet model trained on 293 UPenn cases, fine-tuned with 51 UCSF cases

# remove all pip packages from unet.yml, just keep the conda forge repos.
create the conda env:
conda create --prefix=  -f unet_copy.yml

pip install:
tensorflow
pandas
tensorrt

CUDA was looking for shared libraries with `so.7` and the ones I got installed are `so.8`.
I sym linked and that works.

(WMLseg_no_ver) gemini$ ls /home/vhasfccuneod/miniconda3/lib/python3.10/site-packages/tensorrt
__init__.py                           libnvinfer_plugin.so.7  libnvinfer.so.7  libnvonnxparser.so.8  __pycache__
libnvinfer_builder_resource.so.8.5.3  libnvinfer_plugin.so.8  libnvinfer.so.8  libnvparsers.so.8     tensorrt.so


export CUDA_VISIBLE_DEVICES=0
Used this solution in `CIND_start.py`.
https://gist.github.com/Quasimondo/7e1068e488e20f194d37ba80696b55d8
