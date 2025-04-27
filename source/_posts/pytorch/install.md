---
title: install pytorch
categories:
  - pytorch
tags:
  - pytorch
---

# Install pytorch

## Install conda
```sh
wget --user-agent=“Mozilla” + https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-202│
4.06-1-Linux-x86_64.sh\n                                                                                │
sh Anaconda3-2024.06-1-Linux-x86_64.sh

conda create --name ml-project
conda activate ml-project
pip install torch==2.6.0 torchvision torchaudio
```

## Pytorch version
```sh
torch.__version__
'2.6.0+cu124'
```
so what does `2.6.0+cu124` mean?
- `2.6.0` is the pytorch version
- `cu124` is the cuda version, which means it is compatible with cuda 12.4
- `+` means it is a pre-release version, which means it is not the final version.
- `cu` means it is compatible with cuda
- `12` means it is compatible with cuda 12
- `4` means it is compatible with cuda 12.4

[link](https://blog.csdn.net/AngelCryToo/article/details/145570686)