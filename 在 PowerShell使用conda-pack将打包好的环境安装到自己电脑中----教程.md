### **在 PowerShell使用conda-pack将打包好的环境安装到自己电脑中----教程**

适用于      CUDA   Version大于12.1的电脑

1 查看本机CUDA版本

![](T:\Users\流年\Desktop\Snipaste_2024-10-18_22-28-22.png)

**请根据你的具体环境和需求调整版本号，确保安装的PyTorch版本与你的CUDA版本兼容。注意，PyTorch版本和CUDA版本需要匹配，否则可能会导致不兼容的问题。**

##### envs_fun.txt，是打包好envs（环境名）中的包名，包括：

*pytorch                   2.3.1           <u>**py3.9_cuda12.1_cudnn8_0    pytorch**</u>*        # pytorch版本
*pytorch-cuda              12.1                 hde6ce7c_5    pytorch*       

*cudnn                     7.6.5                cuda10.1_0*
*cupy                      8.3.0            py39hd4ca531_0*

*pyqt5                     5.15.10                  pypi_0    pypi*
*pyqt5-qt5                 5.15.2                   pypi_0    pypi*

*python                    3.9.19               h1aa4202_1*

等很多训练yolov模型的函数包

##### envs.tar.gz文件是我用conda-pack打包好的环境，可以用来训练yolov模型

###### 1.首先安装 conda-pack：

使用 pip 安装
pip install conda-pack

或者conda安装

conda install conda-pack -c conda-forge

##### 2.解压文件

tar -xzf D:\env_backup\pytorch_env.tar.gz -C D:\deployed_envs\pytorch

D:\env_backup\pytorch_env.tar.gz       是自己.tar.gz所在文件位置

D:\deployed_envs\pytorch                   自己在电脑 D:\Anconda3\envs 目录下新建一个文件夹（名称可以自己定义）

##### 3.激活环境

cd D:\deployed_envs\pytorch     # 打开文件
.\Scripts\activate                         #激活文件



另一种方法可以自己解压envs.tar.gz文件，然后在自己在电脑 D:\Anconda3\envs 目录下新建一个文件夹（名称可以自己定义），将解压文件放到新建目录下，

然后     conda env list （查看所有环境名）     conda  activate  环境名（激活环境）     conda list（查看安装的包）

 