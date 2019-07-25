# TP-GAN
data中5pt文件为人脸关键点部位,用mtcnn模型识别,五行分别是左右眼嘴鼻的x和y坐标,代码能在tensorflow0.12版本下跑,不想修改兼容其他版本了  
mtcnn的模型不能在tf0.12下跑,用5pt文件做下中转  
没用到face_db_align_single_custom.m  
tensorflow0.12要求CUDA版本Cuda 8.0 and CudNN 5.1?  
# 使用镜像运行
sudo nvidia-docker pull nvidia/cuda:8.0-cudnn5-devel-ubuntu16.04能跑通  
拉取镜像后需要:  
1.apt-get update后apt-get install python3-dev python3-pip vim  
2.再pip3 install tensorflow-gpu==0.12 scipy pillow  
3.下载代码,放数据集后修改下路径
## 数据集相关信息见https://github.com/HRLTY/TP-GAN
记得修改下identical output的数目  
uitils.py里的scipy.misc的imread和imsave用imageio的imread和imwrite代替(较新版本的scipy.misc去除了这两个功能)
