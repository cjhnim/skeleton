# Build cmake project on Windows Subsystem Linux 

# 1. Install Windows Subsystem Linux and download build essential tools.

[Summary]

0. Install WSL - https://msdn.microsoft.com/en-us/commandline/wsl/install_guide
1. $ sudo apt install -y build-essential
2. $ sudo apt install -y gdbserver
3. $ sudo apt install -y openssh-server
4. $ sudo nano /etc/ssh/sshd_config
5. Scroll down the “PasswordAuthentication” setting and make sure it’s set to “yes”:
6. $ sudo ssh-keygen -A
7. $ sudo service ssh start

If you want to know more explanation, refer to folloing link.
https://blogs.msdn.microsoft.com/vcblog/2017/02/08/targeting-windows-subsystem-for-linux-from-visual-studio/

# 2. Download source and build CMake 3.9.0
CMake version is 3.5 on Windows Subsystem Ubuntu 16.04. So you have to download source and build CMake 3.9.0.

[Summary]
$ sudo apt-get update
$ sudo apt-get install -y git cmake
$ git clone https://github.com/Kitware/CMake.git
$ cd CMake
$ git checkout tags/v3.9.0
$ mkdir out
$ cd out
$ cmake ../
$ make
$ sudo make install
$ /usr/local/bin/cmake –version
$ cmake -E capabilities

# 3. Install & configure Visual Studio 2017
1. Be sure to select the Visual C++ for Linux workload during the installation  process.
2. Now you can connect to the Windows subsystem for Linux from Visual Studio
* Tools > Options > Cross Platform > Connection  Manager
* Click add and enter "localhost" for the hostname and your wSL user/password.

# 4. check out this repository and just open those folder on visual studio 2017

# 5. Now you can build the sources using cmake on Windows Subsystem Linux.
