# FasterViT: Fast Vision Transformers with Hierarchical Attention

Official PyTorch implementation of [**FasterViT: Fast Vision Transformers with Hierarchical Attention**](https://arxiv.org/abs/2306.06189).

[Ali Hatamizadeh](https://research.nvidia.com/person/ali-hatamizadeh),
[Greg Heinrich](https://developer.nvidia.com/blog/author/gheinrich/),
[Hongxu (Danny) Yin](https://scholar.princeton.edu/hongxu),
[Andrew Tao](https://developer.nvidia.com/blog/author/atao/),
[Jose M. Alvarez](https://alvarezlopezjosem.github.io/),
[Jan Kautz](https://jankautz.com/), 
[Pavlo Molchanov](https://www.pmolchanov.com/).

For business inquiries, please visit our website and submit the form: [NVIDIA Research Licensing](https://www.nvidia.com/en-us/research/inquiries/)


--- 

FasterViT achieves a new SOTA Pareto-front in
terms of accuracy vs. image throughput (no extra training data !)

<p align="center">
<img src="https://github.com/NVlabs/FasterViT/assets/26806394/253d1a2e-b5f5-4a9b-a362-6cdd16bfccc1" width=62% height=62% 
class="center">
</p>


We introduce a new self-attention mechanism, denoted as Hierarchical
Attention (HAT), that captures both short and long-range information by learning
cross-window carrier tokens.

![teaser](./assets/hierarchial_attn.png)

## 💥 News 💥

- **[06.09.2023]** 🔥🔥 We have released source code and ImageNet-1K FasterViT-models !

## Catalog
- [x] ImageNet-1K training code
- [x] ImageNet-1K pre-trained models
- [ ] ImageNet-21K pre-trained models
- [ ] ImageNet-21K fine-tune scripts
- [ ] Any-resolution FasterViT
- [ ] Detection code (DINO) + models
- [ ] Segmentation code + models


## Results + Pretrained Models

### ImageNet-1K
**FasterViT ImageNet-1K Pretrained Models**

<table>
  <tr>
    <th>Name</th>
    <th>Acc@1(%)</th>
    <th>Acc@5(%)</th>
    <th>Throughput(Img/Sec)</th>
    <th>Resolution</th>
    <th>#Params(M)</th>
    <th>FLOPs(G)</th>
    <th>Download</th>
  </tr>

<tr>
    <td>FasterViT-0</td>
    <td>82.1</td>
    <td>95.9</td>
    <td>5802</td>
    <td>224x224</td>
    <td>31.4</td>
    <td>3.3</td>
    <td><a href="https://drive.google.com/uc?export=download&id=1twI2LFJs391Yrj8MR4Ui9PfrvWqjE1iB">model</a></td>
</tr>

<tr>
    <td>FasterViT-1</td>
    <td>83.2</td>
    <td>96.5</td>
    <td>4188</td>
    <td>224x224</td>
    <td>53.4</td>
    <td>5.3</td>
    <td><a href="https://drive.google.com/uc?export=download&id=1r7W10n5-bFtM3sz4bmaLrowN2gYPkLGT">model</a></td>
</tr>

<tr>
    <td>FasterViT-2</td>
    <td>84.2</td>
    <td>96.8</td>
    <td>3161</td>
    <td>224x224</td>
    <td>75.9</td>
    <td>8.7</td>
    <td><a href="https://drive.google.com/uc?export=download&id=1n_a6s0pgi0jVZOGmDei2vXHU5E6RH5wU">model</a></td>
</tr>

<tr>
    <td>FasterViT-3</td>
    <td>84.9</td>
    <td>97.2</td>
    <td>1780</td>
    <td>224x224</td>
    <td>159.5</td>
    <td>18.2</td>
    <td><a href="https://drive.google.com/uc?export=download&id=1tvWElZ91Sia2SsXYXFMNYQwfipCxtI7X">model</a></td>
</tr>

<tr>
    <td>FasterViT-4</td>
    <td>85.4</td>
    <td>97.3</td>
    <td>849</td>
    <td>224x224</td>
    <td>424.6</td>
    <td>36.6</td>
    <td><a href="https://drive.google.com/uc?export=download&id=1gYhXA32Q-_9C5DXel17avV_ZLoaHwdgz">model</a></td>
</tr>

<tr>
    <td>FasterViT-5</td>
    <td>85.6</td>
    <td>97.4</td>
    <td>449</td>
    <td>224x224</td>
    <td>975.5</td>
    <td>113.0</td>
    <td><a href="https://drive.google.com/uc?export=download&id=1mqpai7XiHLr_n1tjxjzT8q369xTCq_z-">model</a></td>
</tr>

<tr>
    <td>FasterViT-6</td>
    <td>85.8</td>
    <td>97.4</td>
    <td>352</td>
    <td>224x224</td>
    <td>1360.0</td>
    <td>142.0</td>
    <td><a href="https://drive.google.com/uc?export=download&id=12jtavR2QxmMzcKwPzWe7kw-oy34IYi59">model</a></td>
</tr>

</table>


### Robustness (ImageNet-A - ImageNet-R - ImageNet-V2)

All models use `crop_pct=0.875`. Results are obtained by running inference on ImageNet-1K pretrained models without finetuning.
<table>
  <tr>
    <th>Name</th>
    <th>A-Acc@1(%)</th>
    <th>A-Acc@5(%)</th>
    <th>R-Acc@1(%)</th>
    <th>R-Acc@5(%)</th>
    <th>V2-Acc@1(%)</th>
    <th>V2-Acc@5(%)</th>
  </tr>

<tr>
    <td>FasterViT-0</td>
    <td>23.9</td>
    <td>57.6</td>
    <td>45.9</td>
    <td>60.4</td>
    <td>70.9</td>
    <td>90.0</td>
</tr>

<tr>
    <td>FasterViT-1</td>
    <td>31.2</td>
    <td>63.3</td>
    <td>47.5</td>
    <td>61.9</td>
    <td>72.6</td>
    <td>91.0</td>
</tr>

<tr>
    <td>FasterViT-2</td>
    <td>38.2</td>
    <td>68.9</td>
    <td>49.6</td>
    <td>63.4</td>
    <td>73.7</td>
    <td>91.6</td>
</tr>

<tr>
    <td>FasterViT-3</td>
    <td>44.2</td>
    <td>73.0</td>
    <td>51.9</td>
    <td>65.6</td>
    <td>75.0</td>
    <td>92.2</td>
</tr>

<tr>
    <td>FasterViT-4</td>
    <td>49.0</td>
    <td>75.4</td>
    <td>56.0</td>
    <td>69.6</td>
    <td>75.7</td>
    <td>92.7</td>
</tr>

<tr>
    <td>FasterViT-5</td>
    <td>52.7</td>
    <td>77.6</td>
    <td>56.9</td>
    <td>70.0</td>
    <td>76.0</td>
    <td>93.0</td>
</tr>

<tr>
    <td>FasterViT-6</td>
    <td>53.7</td>
    <td>78.4</td>
    <td>57.1</td>
    <td>70.1</td>
    <td>76.1</td>
    <td>93.0</td>
</tr>

</table>

A, R and V2 denote ImageNet-A, ImageNet-R and ImageNet-V2 respectively. 
## Training

Please see [TRAINING.md](TRAINING.md) for detailed training instructions of all models. 

## Evaluation

The FasterViT models can be evaluated on ImageNet-1K validation set using the following: 

```
python validate.py \
--model <model-name>
--checkpoint <checkpoint-path>
--data_dir <imagenet-path>
--batch-size <batch-size-per-gpu
``` 

Here `--model` is the FasterViT variant (e.g. `faster_vit_0_224_1k`), `--checkpoint` is the path to pretrained model weights, `--data_dir` is the path to ImageNet-1K validation set and `--batch-size` is the number of batch size. We also provide a sample script [here](https://github.com/NVlabs/FasterViT/blob/main/validate.sh). 


## Installation

The dependencies can be installed by running:

```bash
pip install -r requirements.txt
```

## Third-party Extentions
We always welcome third-party extentions/implementations and usage for other purposes. If you would like your work to be listed in this repository, please raise and issue and provide us with detailed information.  


## Acknowledgement
This repository is built on top of the [timm](https://github.com/huggingface/pytorch-image-models) repository. We thank [Ross Wrightman](https://rwightman.com/) for creating and maintaining this high-quality library.  

## Licenses

Copyright © 2023, NVIDIA Corporation. All rights reserved.

This work is made available under the NVIDIA Source Code License-NC. Click [here](LICENSE) to view a copy of this license.

For license information regarding the timm repository, please refer to its [repository](https://github.com/rwightman/pytorch-image-models).

For license information regarding the ImageNet dataset, please see the [ImageNet official website](https://www.image-net.org/). 
