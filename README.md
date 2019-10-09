# Darknet

# TRAIN env

clone repo

```
$ git clone https://github.com/mgoldchild/darkne://github.com/mgoldchild/darknet
```

update compile opts

```
$ cat Makefile
GPU=1
CUDNN=1
OPENCV=0
OPENMP=1
DEBUG=0
```

compile darknet

```
$ make
```

create data

```
$ wget https://pjreddie.com/media/files/VOCtrainval_06-Nov-2007.tar
$ tar xf VOCtrainval_06-Nov-2007.tar
$ wget https://pjreddie.com/media/files/VOCtest_06-Nov-2007.tar
$ tar xf VOCtest_06-Nov-2007.tar
$ python voc_label.py
$ cat 2007_train.txt 2007_val.txt  > train.txt # this may not need.
$ cat train.txt | wc -l
```

update voc.data

```
$ cat cfg/voc.data
classes= 20
train  = /home/jupyter/darknet/2007_train.txt
valid  = /home/jupyter/darknet/2007_val.txt
names = data/voc.names
backup = backup
```

download pretrained model

```
$ wget https://pjreddie.com/media/files/darknet19_448.conv.23
```

execute training

```
$ ./darknet detector train cfg/voc.data cfg/yolov2-voc.cfg darknet19_448.conv.23
```

ref https://pjreddie.com/darknet/yolov2/

# Just test on local

```
$ wget https://pjreddie.com/media/files/yolov2-tiny-voc.weights
$ darknet detector test cfg/voc.data cfg/yolov2-tiny-voc.cfg yolov2-tiny-voc.weights data/dog.jpg
```


![Darknet Logo](http://pjreddie.com/media/files/darknet-black-small.png)

# Darknet #
Darknet is an open source neural network framework written in C and CUDA. It is fast, easy to install, and supports CPU and GPU computation.

For more information see the [Darknet project website](http://pjreddie.com/darknet).

For questions or issues please use the [Google Group](https://groups.google.com/forum/#!forum/darknet).
