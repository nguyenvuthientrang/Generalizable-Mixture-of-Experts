# Welcome to Sparse Fusion Mixture-of-Experts for Domain Generalization

[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/sparse-fusion-mixture-of-experts-are-domain/domain-generalization-on-domainnet)](https://paperswithcode.com/sota/domain-generalization-on-domainnet?p=sparse-fusion-mixture-of-experts-are-domain)

In this work, we reveal the mixture-of-experts (MoE) model's generalizability on DG by leveraging to distributively handle multiple aspects of the predictive features across domains.

### Preparation

```sh
pip3 install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu116

python3 -m pip uninstall tutel -y
python3 -m pip install --user --upgrade git+https://github.com/microsoft/tutel@main

pip3 install -r requirements.txt
```

### Datasets

```sh
python3 -m domainbed.scripts.download \
       --data_dir=./domainbed/data
```

### Environments

Environment details used in paper for the main experiments on Nvidia V100 GPU.

```shell
Environment:
	Python: 3.9.12
	PyTorch: 1.12.0+cu116
	Torchvision: 0.13.0+cu116
	CUDA: 11.6
	CUDNN: 8302
	NumPy: 1.19.5
	PIL: 9.2.0
```

## Start Training

Train a model:

```sh
python3 -m domainbed.scripts.train\
       --data_dir=./domainbed/data/OfficeHome/\
       --algorithm GMOE\
       --dataset OfficeHome\
       --test_env 2
```

## License

This source code is released under the MIT license, included [here](LICENSE).

## Acknowledgement

The MoE module is built on [Tutel MoE](https://github.com/microsoft/tutel).