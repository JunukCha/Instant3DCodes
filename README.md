# Easy to install & run
## Install
```
source scripts/install.sh
```
## Download
[weights](https://drive.google.com/file/d/1SXQco_5n0yQBeuEsLO5-KR-jJQ8v9gxF/view?usp=sharing) 

Download and put it in `ckpts` folder.

## Huggingface login
```
huggingface-cli login
```
Enter your token. [Huggingface token](https://huggingface.co/settings/tokens)

You need to login to download sd2.1 in `ckpts` folder.

## Run
```
soruce scripts/run.sh
```
## Result
Text prompt: _a white man wearing a steampunk hat is singing_

### RGB
https://github.com/user-attachments/assets/ab498a5b-809f-4f4a-85ff-b2f60ee30457

### Depth
https://github.com/user-attachments/assets/86bc150a-23a0-4ef2-8d35-698562060c1f

### Normal
https://github.com/user-attachments/assets/cb9a16bd-2b8d-4240-8ec7-9966edef6f4b


# Official Instant3D Codes
## This is the official implementation of our paper [Instant3D: Instant Text-to-3D Generation](https://arxiv.org/abs/2311.08403).
## The project page is [here](https://ming1993li.github.io/Instant3DProj/).

## 1. Building the required Conda environment by requirements.txt

## 2. Downloading the pre-trained ckpts
### 2.1 Our Instant3D network [weights](https://drive.google.com/file/d/1SXQco_5n0yQBeuEsLO5-KR-jJQ8v9gxF/view?usp=sharing) 
(revise args.py --evaluate accordingly)
### 2.2 Pretrained CLIP and Stable Diffusion weights (revise args.py ----pretrained_path)
#### 2.2.1 The CLIP weight for ViT-L/14
#### 2.2.2 downloading SD 2.1, sign in hugging face account through 
`from huggingface_hub import login
login('')`

## 3. Install tiny-cuda-nn 

## 4. DDP running
python -m torch.distributed.launch --nproc_per_node=1 --master_port=2349 ./main.py --batch-size 1 --random_seed 666 --gpu-ids 0

## Citation
```
@article{li2023instant3d,
title     = {Instant3D: Instant Text-to-3D Generation},
author    = {Li, Ming and Zhou, Pan and Liu, Jia-Wei, and Keppo, Jussi and Lin, Min and Yan, Shuicheng and Xu, Xiangyu},
journal   = {International Journal of Computer Vision},
year      = {2024},
}
```
