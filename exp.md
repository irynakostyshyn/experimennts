# DeblurGAN-v2: Deblurring (Orders-of-Magnitude) Faster and Better
As I have a limited resources I trained only 40 epochs
## Setup 1
---
warmup_num: 3

model: fpn_mobilenet

batch_size: 4

optimizer: 
    name: adam
    lr: 0.0001

scheduler: No scheduler


## Setup 2
---
warmup_num: 7

model: fpn_mobilenet

num_workers: 4

batch_size: 2

optimizer: 
    name: adam
    lr: 0.0001

scheduler:
    name: linear
    start_epoch: 25
    min_lr: 0.0000001



## Setup 3
---
project: deblur_gan
experiment_desc: fpn2
dataroot_train: dataset/
dataroot_val: dataset/
phase: train
warmup_num: 3
model:
    g_name: resnet
    blocks: 9
    d_name: patch_gan
    d_layers: 3
    content_loss: l1
    feature_loss: perceptual
    disc_loss: ragan
    content_coef: 0.5
    feature_coef: 0.006
    adv_coef: 0.001
    learn_residual: True
    norm_layer: instance
    dropout: True  
num_epochs: 40
num_workers: 4
batch_size: 4
image_size: [256, 256]
fineSize: 256
dataset: 
    task: deblur
optimizer: 
    name: adam
    lr: 0.0001
scheduler:
    name: linear
    start_epoch: 25
    min_lr: 0.0000001



## Setup 4
learning rate - 10−4

## Setup 5
learning rate - 10−4

## Setup 6
learning rate of 10−4

