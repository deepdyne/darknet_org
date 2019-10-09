# MEMO


TRAIN

```
$ wget https://pjreddie.com/media/files/VOCtrainval_06-Nov-2007.tar
$ tar xf VOCtrainval_06-Nov-2007.tar
$ wget https://pjreddie.com/media/files/VOCtest_06-Nov-2007.tar
$ tar xf VOCtest_06-Nov-2007.tar
$ python voc_label.py
$ cat 2007_train.txt 2007_val.txt  > train.txt
$ cat train.txt | wc -l
```

https://pjreddie.com/darknet/yolov2/

Just testing

```
$ wget https://pjreddie.com/media/files/yolov2-tiny-voc.weights
$ darknet detector test cfg/voc.data cfg/yolov2-tiny-voc.cfg yolov2-tiny-voc.weights data/dog.jpg
```


![Darknet Logo](http://pjreddie.com/media/files/darknet-black-small.png)

# Darknet #
Darknet is an open source neural network framework written in C and CUDA. It is fast, easy to install, and supports CPU and GPU computation.

For more information see the [Darknet project website](http://pjreddie.com/darknet).

For questions or issues please use the [Google Group](https://groups.google.com/forum/#!forum/darknet).
