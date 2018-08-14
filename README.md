# DRN-MXNet
The [autho](https://github.com/zhuangyqin/DRN.git) of this projcet doesn't release the config file and usages.
I was working on semantic segmentation based on MXNet. So I have fix the errors and add usage for the original project.

## 1. Setup
- Python2.7
- OpenCV
- CUDA 8 or 9

### Build MXNet from Source:
- Clone the mxnet source code
- Put `ordering_op-inl.h` into `incubator-mxnet/src/operator/tensor`
- Put `softmax**` into `incubator-mxnet/src/operator/contrib`
- Follow the official instructions to build and install
- `sh init.sh` to build some libs for dataloader and detection task

### Get data and model
- Put data into `data/cistycapes`, you can use soft link to add the dataset
    `ln -s <dataset> ./data/cityscapes`
- Use the model provided by autho to load params(Optional)
    - [Model](https://pan.baidu.com/s/14_zNi_m7hjv-sMWjY0D1Hw)
    - It's not the pretrained model, so I just use it for test.
    - I will try to generate a pretrained model recently

### Train with a simple config file
Because the original paper is not public now, I can only use some magic number of option to run this code. I am working on understanding the model from the code.
#### Train
`python2 experiment/deeplab/drn_train.py --cfg experiment/deeplab/cfgs/resnet_v2_38_deeplab_dcn_gru_v7.yaml`
#### Test
TBD

### Others 
> main result on ade20k testing is 0.5635(symbol-v11)-single model main result on cityscapes testing is 82.4(symbol-v7) and 82.8(symbol-v13) - single model
> If you have question or some advice, email me 'zhuangyq@pku.edu.cn'
> The model release on 'https://pan.baidu.com/s/14_zNi_m7hjv-sMWjY0D1Hw'

Thanks the author anyway!
