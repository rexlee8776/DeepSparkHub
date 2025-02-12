# VGG16
## Model description
VGG is a classical convolutional neural network architecture. It was based on an analysis of how to increase the depth of such networks. The network utilises small 3 x 3 filters. Otherwise the network is characterized by its simplicity: the only other components being pooling layers and a fully connected layer.


## Step 1: Preparing

### Install requirements
```bash
pip3 install -r requirements.txt
```

### Set up dataset path
Sign up and login in [imagenet official website](https://www.image-net.org/index.php), then choose 'Download' to download the whole imagenet dataset. Specify `/path/to/imagenet` to your imagenet path in later training process.
:beers: Done!


## Step 2: Training
### Multiple GPUs on one machine
Set data path by `export DATA_PATH=/path/to/imagenet`. The following command uses all cards to train:

```bash
bash train_vgg16_amp_dist.sh
```
Install zlib-1.2.9 if reports "iZLIB_1.2.9 not found" when run train_vgg16_amp_dist.sh

```bash
wget http://www.zlib.net/fossils/zlib-1.2.9.tar.gz
tar xvf zlib-1.2.9.tar.gz
cd zlib-1.2.9/
./configure && make install
cd ../
rm -rf zlib-1.2.9.tar.gz zlib-1.2.9/
```



:beers: Done!


## Reference
- [torchvision](https://github.com/pytorch/vision/tree/main/references/classification)
