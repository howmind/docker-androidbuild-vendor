# docker-androidbuild-vendor

Docker image for building android source from vendor and future verions.

You can build the image locally.

    git clone https://github.com/howmind/docker-androidbuild-vendor.git
    cd docker-androidbuild-vendor/L/mtk
    docker build -t howmind/androidbuild-l .

## Usage ##
You can launch the image using the docker command line, suppose you have prepared a folder for android codebase download at the local host, e.g. **~/codebase,

    docker run --name='androidbuild-l' -it --rm \
    -v ~/codebase:/home/android/codebase \
    howmind/androidbuild-l \
    /bin/bash

The **/home/android/codebase is the mounted point inside the container.

Once entering the container, you can operate as the normal developing:

    0 android@ ~ $ cd codebase
    0 android@ ~/aosp $ git config --global user.email "name@example.com"
    0 android@ ~/aosp $ git config --global user.name "My Name"
    0 android@ ~/aosp $ repo init -u https://android.googlesource.com/platform/manifest -b android-l-preview_r2
    0 android@ ~/aosp $ repo sync
    0 android@ ~/aosp $ source build/envsetup.sh
    0 android@ ~/aosp $ lunch ......

## Pre-Configured ##
- Ubuntu 14.04
- Default user account: name=**android**, password=**android**
- Toolchains as from [http://source.android.com/source/initializing.html](http://source.android.com/source/initializing.html)
- Repo tool as from [http://source.android.com/source/downloading.html](http://source.android.com/source/downloading.html)


