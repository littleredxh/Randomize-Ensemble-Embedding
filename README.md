# Deep Randomized Ensembles for Metric Learning

This repository contains a PyTorch(1.0.0) implementation of Deep Randomized Ensembles for Metric Learning(ECCV2018)

Paper link: https://arxiv.org/abs/1808.04469

Prepare the training data and testing data in python dictionary format. 

For example:
```
data_dict = {'tra' : {'class_tra_01':[image list],
                      'class_tra_02':[image list],
                      'class_tra_03':[image list],
                      ....,
                      'class_tra_XX':[image list]}
                 
             'test': {'class_test_01':[image list],
                      'class_test_02':[image list],
                      'class_test_03':[image list],
                      ....,
                      'class_test_XX':[image list]}
            }
```
                 

Replace data_dict_tra and data_dict_test in line 14 and line 18 of ```main.py```

We only have the color nomarlization info for CUB, CAR, SOP, CIFAR100, In-shop cloth, and PKU vehicleID data. If you use other dataset please add the color nomarlization data in the file: ```_code/color_lib.py```

We also supply our efficient recall@K accuracy calculation functions which are located in ```_code/Utils.py```

```
This function is for CAR,CUB and SOP dataset
recall(Fvec, imgLab,rank=None) 
Fvec:   Feature vectors, N by D torch.Tensor
imgLab: Image label, python list
rank:   k of recall@k, python list

This function is for In-shop Cloth dataset
recall2(Fvec_val, Fvec_gal, imgLab_val, imgLab_gal,rank=None) 
Fvec_val:     Probe feature vectors, N_val by D torch.Tensor
Fvec_gal:     Gallary feature vectors, N_gal by D torch.Tensor
imgLab_val:   Probe image label, python list
imgLab_gal:   Gallary image label, python list
rank:         k of recall@k, python list
```

The example of calling the function is shown in  ```Recall.ipynb```

Please cite our paper, if you use these functions for recall calculation.

### Requirements
Pytorch 1.0.0

Python 3.5

### Updates
05/01/2019/: 

Upgrade to PyTorch 1.0.0 version

Simplified the codes structure

Fix the bug in Recall.ipynb

Add recall functions for In-shop CAR, CUB, SOP and cloth dataset

### Citation
```
@InProceedings{Xuan_2018_ECCV,
author = {Xuan, Hong and Souvenir, Richard and Pless, Robert},
title = {Deep Randomized Ensembles for Metric Learning},
booktitle = {The European Conference on Computer Vision (ECCV)},
month = {September},
year = {2018}
}
```