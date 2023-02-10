---
layout: post
title:  "Compiling Cartographer ROS on Jetson Nano"
date:   2023-02-10 00:00:00 +0800
categories: ROS
---
# Compiling Cartographer ROS on Jetson Nano

According to [Cartographer — Cartographer documentation](https://google-cartographer.readthedocs.io/en/latest/#system-requirements), packages below should be installed first.

```bash
sudo apt-get install -y \
    clang \
    cmake \
    g++ \
    git \
    google-mock \
    libboost-all-dev \
    libcairo2-dev \
    libceres-dev \
    libcurl4-openssl-dev \
    libeigen3-dev \
    libgflags-dev \
    libgoogle-glog-dev \
    liblua5.2-dev \
    libsuitesparse-dev \
    lsb-release \
    ninja-build \
    python3-sphinx \
    stow
```

Then use `wstool` to add Cartographer ROS to a catkin workspace. The catkin workspace can either already exist or be newly created. Giving Cartographer ROS an independent catkin workspace makes it easier to compile and upgrade.

```bash
mkdir carto_ws
cd carto_ws
wstool init src
wstool merge -t src https://raw.githubusercontent.com/cartographer-project/cartographer_ros/master/cartographer_ros.rosinstall
wstool update -t src
```

If `sudo rosdep init` hasn't been run, run it.

Dependencies can be installed by `rosdep` automatically.

```bash
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y
```

Abseil needs to be installed manually using the given script.

```bash
src/cartographer/scripts/install_abseil.sh
```

Besides the official document, protobuf should be installed manually too. You can install it using the provided script below.

```bash
src/cartographer/scripts/install_proto3.sh
```

On arm devices like Jetson Nano, 

```bash
cd protobuf/
./autogen.sh
./configure --host=arm-linux --with-protoc=protoc
make
sudo make install
```

After the installation of protobuf, run

```bash
protoc --version
```

If it was installed properly, message like `libprotoc 3.4.0` will be displayed.

If problem like this occurs, 

```
error while loading shared libraries: libprotobuf.so.xx
```

run `ldconfig` to create necessary links and cache to the newly installed shared libraries.

Then you can build and install Cartographer ROS in your catkin workspace.

```bash
catkin_make_isolated --install --use-ninja
```

According to [在ARM平台安装Cartographer（Jetson NX 和 Xavier亲测）_wallong的博客-CSDN博客](https://blog.csdn.net/ewtewtewrt/article/details/113727155), protobuf with conflicting versions may have been installed with ROS already installed on the device. When the problem occurs, `catkin_make_isolated` will throw a "protobuf version not match" warning. 

To solve this problem, delete `usr/local/include/google/protobuf` and `/usr/bin/protoc` manually to remove the old protobuf with conflicting versions. Then install your new build again. 

Now, run `catkin_make_isolated --install --use-ninja` in catkin workspace, the problem should be solved.

To use cartographer in ROS, you need to run `source ~/cartographer_ws/install_isolated/setup.bash` first. Add it to `~/bash.rc` to run it automatically when bash terminal launchs.

After completing all the steps above, Download the Deutsches Museum demo bag and launch `cartographer_ros` to test it if was installed properly.

```bash
wget -P ~/Downloads https://storage.googleapis.com/cartographer-public-data/bags/backpack_2d/cartographer_paper_deutsches_museum.bag
roslaunch cartographer_ros demo_backpack_2d.launch bag_filename:=${HOME}/Downloads/cartographer_paper_deutsches_museum.bag
```

References:

[Cartographer — Cartographer documentation](https://google-cartographer.readthedocs.io/en/latest/#system-requirements)

[Compiling Cartographer ROS &mdash; Cartographer ROS documentation](https://google-cartographer-ros.readthedocs.io/en/latest/compilation.html)

[在ARM平台安装Cartographer（Jetson NX 和 Xavier亲测）_wallong的博客-CSDN博客](https://blog.csdn.net/ewtewtewrt/article/details/113727155)
