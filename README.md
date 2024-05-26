<div align="center">

# ISO Builder

## Branches
The branches have the following format `DE-PIKAVERSION_ARCH`

So the GNOME version of PikaOS 4 for x64-v3 would be:
`gnome-4_x64-v3`

## Building Locally

The following example uses Docker and assumes you have Docker correctly installed and set up:

 1) Clone this project & `cd` into it:

    ```
    git clone -b gnome-4_x64-v3 https://github.com/PikaOS-Linux/live-iso && cd live-iso
    ```

 2) Run the build:

    ```
    docker run --privileged -i -v /proc:/proc \
        -v ${PWD}:/working_dir \
        -w /working_dir \
        ghcr.io/vanilla-os/pico:main \
        /bin/bash -s etc/terraform.conf < build.sh
    ```

 3) When done, your image will be in the `builds` folder.
