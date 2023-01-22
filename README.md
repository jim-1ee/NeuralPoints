# Neural Points

In this project, we propose Neural Points, a novel point cloud representation and apply it to the arbitrary-factored upsampling task. Different from traditional point cloud representation where each point only represents a position or a local plane in the 3D space, each point in Neural Points represents a local continuous geometric shape via neural fields. Therefore, Neural Points contain more shape information and thus have a stronger representation ability. Neural Points is trained with surface containing rich geometric details, such that the trained model has enough expression ability for various shapes. Specifically, we extract deep local features on the points and construct neural fields through the local isomorphism between the 2D parametric domain and the 3D local patch. In the final, local neural fields are integrated together to form the global surface. Experimental results show that Neural Points has powerful representation ability and demonstrate excellent robustness and generalization ability. With Neural Points, we can resample point cloud with arbitrary resolutions, and it outperforms the state-of-the-art point cloud upsampling methods. 

This repo is the code of our CVPR 2022 paper **Neural Points: Point Cloud Representation with Neural Fields for Arbitrary Upsampling**.
This is a joint work by GUET & USTC, while I was visiting USTC, advised by Feng Wanquan and Zhang Juyong.

- Paper address: [https://www.computer.org/csdl/proceedings-article/cvpr/2022/694600s8612/1H0KFnuPS6c](https://www.computer.org/csdl/proceedings-article/cvpr/2022/694600s8612/1H0KFnuPS6c)
- Project webpage: [https://jim-1ee.github.io/NeuralPoints.html](https://jim-1ee.github.io/NeuralPoints.html)


![avatar](./utils/Pipeline_v5.png)

## Prerequisite Installation
The code has been tested on Ubuntu 18, with Python3.8, PyTorch 1.6 and Cuda 10.2:

    conda create --name NePs
    
    conda activate NePs
    
    conda install pytorch=1.6.0 torchvision=0.7.0 cudatoolkit=10.2 -c pytorch
    
    conda install -c conda-forge igl

Before running the code, you need to build the cuda&C++ extensions of Pytorch:

    cd [ProjectPath]/model/model_for_supp/pointnet2
    
    python setup.py install


​    
## How to use the code: 
Download our dataset: [dataset](https://pan.baidu.com/s/1BLFobnIkuLqrXsdAAVqA0g), (extracting code: qiqq). Put the 'Sketchfab2' folder into: [ProjectPath]/data.

Firstly, you need to change the working directory: 

    cd [ProjectPath]/model/conpu_v6

To obtain the testing results of the testing set, run:

    python train_script101_test.py

To train our network, run:

    python train_script101.py


## Citation
Please cite this paper with the following bibtex:

    @inproceedings{feng2022np,
        author    = {Wanquan Feng and Jin li and Hongrui Cai and Xiaonan Luo and Juyong Zhang},
        title     = {Neural Points: Point Cloud Representation with Neural Fields for Arbitrary Upsampling},
        booktitle = {{IEEE/CVF} Conference on Computer Vision and Pattern Recognition (CVPR)},
        year      = {2022}
    }



