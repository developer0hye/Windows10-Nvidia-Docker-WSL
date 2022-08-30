# Run Nvidia Docker on WSL(Windows10)

1. Update OS

2. Download [the latest version of the gpu driver](https://www.nvidia.com/Download/index.aspx?lang=en-us)

3. Update WSL and install Ubuntu on the **administrator**  Windows Command Prompt

```bash
wsl --update
wsl --install -d Ubuntu
```

4. Run Ubuntu

5. (Optional) Install [a CUDA Toolkit for Linux x86](https://docs.nvidia.com/cuda/wsl-user-guide/index.html#cuda-support-for-wsl2) following Option 1

Step 5. allows you to build a cuda source code on WSL Ubuntu.

6. Install [Docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

7. Install [Nvidia Docker]()

