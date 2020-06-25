# MANet
MANet: Multimodal Attention Network based Point- View fusion for 3D Shape Recognition


Created by Yaxin Zhao, Jichao Jiao*, Tangkun Zhang, Xinping Chen, Chenxu Wang, Wei Cui School of Electronic Engineering Beijing University of Posts and Telecommunications Beijing, China


![Architecture of the proposed MANet](https://github.com/YaXin-Zhao1996/MANet/blob/master/MANet.png)


# Abstract

**3D shape recognition** has attracted more and more attention as a task of 3D vision research. The proliferation of 3D data encourages various deep learning methods based on 3D data. Now there have been many deep learning models based on point- cloud data or multi-view data alone. However, in the era of big data, integrating data of two different modals to obtain a unified 3D shape descriptor is bound to improve the recognition accuracy. Therefore, this paper proposes **a fusion network based on multimodal attention mechanism for 3D shape recognition.** Considering the limitations of multi-view data, we introduce **a soft attention scheme,** which can use the global point-cloud features to filter the multi-view features, and then realize the effective fusion of the two features. More specifically, we obtain the enhanced multi-view features by mining the contribution of each multi-view image to the overall shape recognition, and then fuse the point-cloud features and the enhanced multi-view features to obtain a more discriminative 3D shape descriptor. We have performed relevant experiments on the ModelNet40 dataset, and **experimental results verify the effectiveness of our method.**

# Configuration

Code is tested under the environment of Pytorch 0.4.1, Python 3.6 and CUDA 9.0  using 2 NVIDIA TITAN Xp GPUs.

**Data**:

[point cloud data](https://drive.google.com/file/d/1DUh_8PQjh3ds4yO0O8q_vb0HPistOJ4y/view)

[multi-view(12-view) data](https://drive.google.com/file/d/12JbIPLvcSUsMjxb_CZYXI8xQK2UKosio/view)

**Pretrained Model:** 

[PVRNet](https://drive.google.com/file/d/1g3Ef68jRSY2mNf54dOeqNFYZTm4cO13d/view)

[MANet](https://drive.google.com/file/d/1vWp1_jdcdO0zjXwiP44LRBM_iN-N7GhY/view?usp=sharing)


**Note:** You can compare our MANet pre-training model with the PVRNet pre-training model. Our model size is 507.17MB, while the latter is 579.16MB. With the loss of 0.2% accuracy, but our algorithm successfully reduced the model by 12.43%. This is supported by practical basis and theory, because our algorithm has only processed the point-view data once effectively, while there are three parts of PVRNet that using point-view data. They are Relation Score Module, Point-Single-view Fusion and Point-Multi-view Fusion. We must admit that such processing method in PVRNet has a certain improvement in accuracy, but this is at the expense of efficiency and model parameters. It can be seen in the code that the amount of our parameters in the fusion module is lower than PVRNet.Based on the balanced accuracy and model complexity, our algorithm that reduces training parameters and model size has a certain contribution.

# Usage

Download data and our pretrained ckpt from above links. Create dir for data as well as result, and place them under corresponding dirs(./data/ and ./result/ckpt/).

```
mkdir -p data result/ckpt
```

