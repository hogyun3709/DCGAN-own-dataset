# DCGAN-tensorflow-own-dataset
***
This repository explains selective implementation of train DCGAN with your own dataset. If you want to experience fully stable
model, visit (https://github.com/carpedm20/DCGAN-tensorflow).


## Prerequisites

- Python 2.7 or Python 3.3+
- [Tensorflow 0.12.1](https://github.com/tensorflow/tensorflow/tree/r0.12)+
- [SciPy](http://www.scipy.org/install.html)
- [pillow](https://github.com/python-pillow/Pillow)

## Implementation

This model supports both cpu and gpu training. 
First of all, checkout either python2 or python3 use gpu as default device or not. 
In writer's case, python3 uses gpu as training device, following usage will be written by python3 command
***
1. Prepare dataset:

```bash
$ mkdir data/your-dataset-folder-name
```

2. Train a model

```bash
$ python3 main.py --dataset your-dataset-folder-name --crop --train
```
or you can set the image demension: recomended 108
```bash
$ python3 main.py --dataset your-dataset-folder-name --input_height=108 --output_height=108 --train
```
based on image demension the training speed might be faster or slower

If you have decent gpu, make sure the gpu and cuda executed properly. You need to check following logs in your terminal.
```bash
StreamExecutor device (*): GeForce GTX **** **, Compute Capability *.*
successfully opened CUDA library libcublas.so.**.** locally
```

## Result
My own dataset is a combination of style lookbook.
Looking for 8x8 neatly generated clothes but, around 15 epoch, it seems the result with high noise. Further modification required.<br>
![result](/lookbook-result.gif)

With given target dataset which is celebA from original repo, even up to the 1 epoch, it shows feasible result

![result2](/celebA-result.gif)

