## Tested with Ubuntu 22.04 
## Clone  recursive

```
git clone https://github.com/muskie82/MonoGS.git --recursive
cd MonoGS
```

## Create Conda env with python=3.7.13
```
conda create --name MonoGS python=3.7.13
```

## Activate into MonoGS

```
conda activate MonoGS
```
## Install torch, torchvision, torchaudio for cuda 11.6

```
pip install torch==1.12.1+cu116 torchvision==0.13.1+cu116 torchaudio=0.12.1+cu116 --extra-index-url https://download.pytorch.org/whl/cu116
```
## Install Cuda-Toolkit for CUDA 11.6

```
conda install -c "nvidia/label/cuda-11.6.2" cuda-toolkit
```
## Install Other dependencies mentioned in  environment.yaml

```
pip install plyfile=0.8.1 tqdm submodules/simple-knn submodules/diff-gaussian-rasterization opencv-python==4.8.1.78 munch trimesh evo==1.11.0 open3d==0.17.0 torchmetrics imgviz PyOpenGL glfw PyGLM wandb lpips rich ruff
```
## Download dataset for Quick Demo

```
mkdir -p datasets/tum
cd datasets/tum

wget https://vision.in.tum.de/rgbd/dataset/freiburg3/rgbd_dataset_freiburg3_long_office_household.tgz

tar -xvzf rgbd_dataset_freiburg3_long_office_household.tgz
```

## Quick Demo

```
python slam.py --config configs/mono/tum/fr3_office.yaml
```

