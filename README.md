# FI-UNet

## Installing Dependencies
To install the necessary Python libraries:

torch==1.13.0 torchvision==0.14.0 torchaudio==0.13.0 --extra-index-url https://download.pytorch.org/whl/cu117  
packaging  
timm==0.4.12  
pytest chardet yacs termcolor  
submitit tensorboardX  
triton==2.0.0  
causal_conv1d==1.0.0  # causal_conv1d-1.0.0+cu118torch1.13cxx11abiFALSE-cp38-cp38-linux_x86_64.whl  
mamba_ssm==1.0.1  # mamba_ssm-1.0.1+cu118torch1.13cxx11abiFALSE-cp38-cp38-linux_x86_64.whl  
scikit-learn matplotlib thop h5py SimpleITK scikit-image medpy yacs  


## This project uses the following datasets for training and testing:

[ISIC2018 Dataset](https://drive.google.com/file/d/1XM10fmAXndVLtXWOt5G0puYSQyI2veWy)  
[Synapse Dataset](https://www.synapse.org/#!Synapse:syn3193805/wiki/)  

Place the downloaded files into the './data' folder in the project root directory.

Pre-trained Model Weights

The weights of the pre-trained VMamba could be downloaded ：https://github.com/MzeroMiko/VMamba. After that, the pre-trained weights should be stored in './pretrained_weights/'.


## Dataset Configuration
You can modify the dataset configuration in the configs folder to select different datasets. For example:

datasets = 'isic18'  # You can change this to 'isic17' or another dataset as needed  
if datasets == 'isic18':  
      &emsp; data_path = './data/isic2018/'  
elif datasets == 'isic17':  
      &emsp; data_path = './data/isic2017/'  
else:  
      &emsp; raise Exception('Dataset is not correctly specified!')  
Ensure that the datasets variable is set correctly to load the appropriate dataset.

## Training and Validation
After preparing the environment, you can start training and validation by running the train.py script:

python train.py  
This command will initiate the training process and evaluate the model on the selected dataset.
