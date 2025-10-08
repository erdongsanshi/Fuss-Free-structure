# The Effectiveness of a Simplified Structure for Crowd Counting

## 🎉 Great News!

This work has been accepted by **IEEE Transactions on Instrumentation and Measurement (TIM)**!  

Official implementation of our paper:  **[The Effectiveness of a Simplified Structure for Crowd Counting](https://ieeexplore.ieee.org/document/10938701)**

## Installation

```
pip install -r requirements.txt
```
## Data Preparation

- Download crowd-counting datasets, e.g., [ShanghaiTech](https://drive.google.com/file/d/1pSXVqS9NxIKs8W4-DAH38StWiWvBv1Zh/view?usp=drive_link)
                                          [NWPU](https://drive.google.com/file/d/1Mt9aEyejhsx3rCIaW2jepFQGacv5qFzw/view?usp=drive_link)

- You can also implement your own datasets processing according to the processing file

## Training
update root "data-dir" and "dataset" in ./train.py, Other parameters can be adjusted as required
```bash
python train.py
```
You can set ```--wandb 1``` in ```train.py``` after having logged in to wandb (```wandb login``` in console) to visualize the training process

## Testing
Due to the image clipping size is different during training, the clipping size should be adjusted accordingly during validation. The clipping size is 256×256 for SHA, 512×512 for SHB, and 384×384 for NWPU.
```bash
python test_image_patch.py
```


## Pretrained Models

| Dataset                  | Model Link  | MAE |
| ------------------------ | ----------- | --- |
| ShanghaiTech PartA       |  [SHA_model.pth](https://drive.google.com/file/d/1vQLWSIYTUXMJKMnVlKgiuYGbsVqPyN9W/view?usp=drive_link)   | 48.30 |
| ShanghaiTech PartB       |  [SHB_model.pth](https://drive.google.com/file/d/1LhRde7Ztpg1pn3C7DIfZj9tkP5FrHh1P/view?usp=drive_link)   |  6.1  |
| NWPU(Val)                |  [NWPU_model.pth](https://drive.google.com/file/d/1zCkfSvTV2Cx5boEZ3a6lgyQMCPeeNGmi/view?usp=drive_link)  | 41.26 |



## How to cite
Please cite this paper when using it:
```
@article{gao2025effectiveness,
  title={The Effectiveness of a Simplified Model Structure for Crowd Counting},
  author={Gao, Xingen and Chen, Lei and Chao, Fei and Chang, Xiang and Gao, Xinghang and Jiang, Huali and Liu, Li and Zhang, Hongyi},
  journal={IEEE Transactions on Instrumentation and Measurement},
  year={2025},
  publisher={IEEE}
}
```


## Acknowledgement

We thank the authors of [DM-Count](https://github.com/cvlab-stonybrook/DM-Count) and [CCtrans](https://github.com/wfs123456/CCTrans) for open-sourcing their work.
