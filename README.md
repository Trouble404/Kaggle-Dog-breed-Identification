# Kaggle-Dog-breed-Identification
Determine the breed of a dog in an image

# MXnet GPU version configuration (Windows 10. GTX960M)
## Tools
* [Microsoft Visual Studio 2015](https://www.visualstudio.com/zh-hans/vs/older-downloads/)
* [CUDA 9.0](http://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/)
* [cuDNN7](https://developer.nvidia.com/cudnn)
* [CMake](https://cmake.org/)
* [OpenCV3.0](https://sourceforge.net/projects/opencvlibrary/files/opencv-win/3.0.0/opencv-3.0.0.exe/download)
* [OpenBLAS](https://sourceforge.net/projects/openblas/files/v0.2.14/)
* [Anaconda](https://www.anaconda.com/download/)

---

## Methods
* Step 1: Install VS2015

* Step 2: Install CUDA 9.0

* Step 3: Install cuDNN7 解压后把cudnn目录下的bin目录加到PATH环境变量里

* Step 4: Install Opencv 下载并解压，然后创建环境变量OpenCV_DIR，把opencv/build目录添加进去,把\opencv\build\x64\vc12\bin和\opencv\build\x86\vc12\bin添加到PATH路径

* Step 5: Install openBLAS 需要下载mingw64_dll.zip和OpenBLAS-v0.2.14-Win64-int64.zip两个文件. 创建环境变量 OpenBLAS_HOME，把openBLAS根目录加进去,把DLL所在目录需要添加到环境变量path中. 创建  ```C:\Program files (x86)\OpenBLAS\``` 复制相关文件进去

* Step 6: Install Anaconda 把安装路径添加到PATH里去

* Step 7: Install MXnet 创建MXnet 文件夹 然后使用命令行CD至该文件夹 ```git clone --recursive https://github.com/dmlc/mxnet``` 在根目录创建build文件夹  (补充操作 目前未使用： 打开make文件夹的config.mk 文件 修改USE_CUDNN = 0 to USE_CUDNN = 1, 修改USE_BLAS = openBLAS )

* Step 8: Install Cmake Configure and Genreate VS工程 **mxnet.sln**  Configure的配置选择如下图
![image](https://raw.githubusercontent.com/Trouble404/Kaggle-Dog-breed-Identification/master/readme_pic_add/cmake.PNG)

* Step 9: 使用VS2015 打开mxnet.sln 切换成release模式 64位 然后启动编译 编译完成后，在mxnet_build\Release目录下生成了**libmxnet.dll**文件

* Step 10: 使用Anaconda 新建一个虚拟环境 ```conda create  --name MXNet python=2.7```  MXNET目前不太适配python3, 激活环境 ```activate MXNet``` 

* Step 10: cd 至mxnet文件夹的python文件夹里， 拷贝如图的各个文件到该文件夹 ```python setup.py install```
