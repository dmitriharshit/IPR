# Optimal LED Spectral Multiplexing for NIR2RGB Translation

[Lei Lui](https://github.com/loklz), [Yuze Chen](https://github.com/cccyz), [Junchi Yan](https://thinklab.sjtu.edu.cn), Yinqiang Zheng

This paper has been accpected by **CVPR2022**. In this short tutorial, we will guide you through setting up the system environment for running the code, which used for NIR-to-RGB translation.


## Requirments

- *Ubuntu 16.04*
- *CUDA 9.1*
- *pytorch 1.7.1*

run ``` pip install requirements.txt ```


## Datasets

download the processed [Dataset](https://drive.google.com/drive/folders/1wAhW3AUIy0lMjJmUYQHcKuDriUXoVYeO?usp=sharing).

### Training phase
    ``` 
    python3 train.py --dataroot path/to/the/datasets/icvl/train --name experiment_name 

    eg - python3 train.py --dataroot Dataset/CSS_13S2C/ICVL --name experiment_name 
    ```
 On training image outputs and model are stored in `checkpoints/experiment_name`, if you have multi GPUs, using `--gpu_ids 0` to specify the gpu you want to use.


### Testing phase


 After the training step, or download the pretrained model and put them in `checkpoints/experiment_name` folder. Run the following command to translate NIR images to RGB images:
    ``` 
    python3 test.py --dataroot path/to/the/datasets/icvl/test --name experiment_name 

    eg - python3 test.py --dataroot Dataset/CSS_13S2C/ICVL --name experiment_name 
    ```

The results are stored in `results/experiment_name` folder. 

## RGB Variance Maximization (RVM)

Run the following command to see the results of RVM with 3 cameras:
    ```
    python3 util/rvm.py
    ```
    
