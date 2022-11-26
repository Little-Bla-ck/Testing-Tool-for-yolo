# Testing-Tool-for-yolo

## Step One

### Install mm-yolo dependency

【推荐】安装 anaconda。下面的步骤以 anaconda 环境下的虚拟环境来进行实践。

首先我们在 anaconda 中执行以下命令创建一个虚拟环境，需要的 Python 版本为 3.8（如果本地 Python 版本非此版本建议使用 anaconda 创建虚拟环境）。

```bash
conda create --name openmmlab python=3.8 -y
conda activate openmmlab
```

这里的 `openmmlab` 可以换成你喜欢的名字，然后我们下载 mmlab-yolo 需要的一些依赖。

GPU 版本：

```bash
conda install pytorch torchvision -c pytorch
```

CPU 版本：

```bash
conda install pytorch torchvision cpuonly -c pytorch
```

mm-openlab 通过 openmim 进行包管理，因此接下来我们需要执行以下的指令：

```bash
pip install -U openmim
mim install "mmengine>=0.3.1"
mim install "mmcv>=2.0.0rc1,<2.1.0"
mim install "mmdet>=3.0.0rc3,<3.1.0"
```

如果你是 CPU 版本的话，你可以将 `mim install "mmcv>=2.0.0rc1,<2.1.0"` 替换为 `mim install "mmcv-lite>=2.0.0rc1"`，后者是不包含一些 CUDA 算子的，更加轻便。

### Install mm-yolo

因为我们不需要自己训练，所以直接使用 `mim install "mmyolo"` 进行安装即可。

## Step Two

第二步是安装图像扩增框架 [imgaug](https://github.com/aleju/imgaug)，我们在上面的 anaconda 环境中执行以下的指令：

```bash
pip install imgaug
```