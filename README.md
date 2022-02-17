#<base target="_blank"/>


Article title "Taming the data deluge: designing a deep learning system for classifying marine biological and environmental images"
By "Hongsheng Bi, Yunhao Cheng, Xuemin Cheng, Mark C. Benfield, David G. Kimmel, Haiyong Zheng, Kezhen Ying"
DOI: #####

## Prerequisites
- Windows
- Visual Studio 2019(install *desktop development with C++*)
- CPU or NVIDIA GPU + CUDA 10.1

## Installation

### Prepare environment
Download our base [environment](Google Driver or BaiduCloud link) and put it to *'anaconda/envs'* folder, then activate it.
  
```shell
conda activate dete2
``` 

### Install cocoAPI
For Python, you can simply install cocoapi with the following command:

```shell
cd cocoapi/PythonAPI
python setup.py build_ext install
``` 

### Install Detectron2
You can simply install detectron2 with the following command:

```shell
cd maskrcnn
python setup.py build develop
``` 

## Train/Test
### For scene classification
- Prepare scene training dataset, its format reference folder 'dataset/scene'.
- Modify parameters in *'config\scene_training.yml'*, train a model:
```shell
python main.py --mode scene_training  --config_file config\scene_training.yml
```

- Modify parameters in *'config\scene_testing.yml'*, test the model:
```shell
python main.py --mode scene_testing  --config_file config\scene_testing.yml
```

### For mask r-cnn
- Prepare mask r-cnn training dataset, its format reference folder *'dataset/maskrcnn'*. Using Labelme to labeled data.  
- Modify parameters in *'config\maskrcnn_training.yml'*, train a model:
```shell
python main.py --mode maskrcnn_training  --config_file config\maskrcnn_training.yml
```
- Modify parameters *in 'config\maskrcnn_testing.yml'*, test the model:
```shell
python main.py --mode maskrcnn_testing  --config_file config\maskecnn_testing.yml
```
### For the process of the image
Modify parameters in *'config\process_image.yml'*, run:
```shell
python main.py --mode process_image  --config_file config\process_image.yml
```

# Bibtex
If you use this code for your research, please cite our papers.

```
@InProceedings{Bi_MarineDeepLearning,
    author    = {Bi, Hongsheng and Cheng, Yunhao and Cheng, Xuemin and Benfield, Mark C. and Kimmel, David G. and Zheng, Haiyong and Ying, Kezhen},
    title     = {Taming the data deluge: designing a deep learning system for classifying marine biological and environmental images},
    Journal = {IEEE Transactions on Neural Networks and Learning Systems},
    month     = {},
    year      = {Submitted},
    pages     = {#####}
}
```

# Acknowledgement
For some of model functions used in this source code, we need to acknowledge the repo of [Detectron2](https://github.com/facebookresearch/detectron2) and [cocoapi](https://github.com/cocodataset/cocoapi).
