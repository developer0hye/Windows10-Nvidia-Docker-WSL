# Run Nvidia Docker on WSL(Windows10)

1. Update Windows10 OS

2. Download [the latest version of the gpu driver](https://www.nvidia.com/Download/index.aspx?lang=en-us)

3. Update WSL and install Ubuntu on the **administrator**  Windows Command Prompt

```bash
wsl --update
wsl --install -d Ubuntu
```

4. Run Ubuntu

5. (Optional) Install [a CUDA Toolkit for Linux x86](https://docs.nvidia.com/cuda/wsl-user-guide/index.html#cuda-support-for-wsl2) following **Option 1(Recommended)**

Step 5. allows you to build a cuda source code on native WSL Ubuntu.

6. Install [Docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

7. Install [Nvidia Docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker)

```bash
sudo service docker stop
sudo service docker start
sudo docker run --rm --gpus all nvidia/cuda:11.0.3-base-ubuntu20.04 nvidia-smi
```

If you install successfully `nvidia-docker`, you can see the below results.

```
Tue Aug 30 10:47:15 2022
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 515.65.01    Driver Version: 516.94       CUDA Version: 11.7     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  NVIDIA GeForce ...  On   | 00000000:01:00.0  On |                  N/A |
|  0%   51C    P0    54W / 240W |   1070MiB /  8192MiB |      1%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|  No running processes found                                                 |
+-----------------------------------------------------------------------------+
```
