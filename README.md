# stb0899
Dkms tweaked kernel module for low C/N.

This module source will create a new Linux kernel module with enhanced capabilities (performance for low C/N signal, restore signal monitoring ...)

As it is based on kernel module replacing, you need first to install closest kernel source for your distribtion.

As example, for Debian Bullseye, you can take : 

    wget https://mirrors.edge.kernel.org/pub/linux/kernel/v5.x/linux-5.10.tar.xz

Then uncompress it to the right directory:

    sudo tar -xf linux-5.10.tar.xz -C /usr/src

Next, get the repository to local:

    git clone https://github.com/enigma131/stb0899.git

Here, you have to adjust the rigt kernel path for KERNSRC and KERNELSOURCE in Makefile:

    nano stb0899/Makefile 

Make changes and save the file.

Initialize the DKMS structure:

    sudo dkms add ./stb0899

Compile source / Install DKMS:

    sudo dkms install stb0899/enigma13

Verify résult :

    dkms status

    modinfo stb0899

Rebbot and test
