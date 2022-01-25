# stb0899

This module source will create a new Linux kernel demodulator module with enhanced capabilities (performance for low C/N signal, restore signal monitoring ...). This module is part of my TechnoTrend TT-budget S2-3200 PCI card and also in other devices: https://www.linuxtv.org/wiki/index.php/STMicroelectronics_STB0899

Tuner tweaks (second repository stb6100) can also be used if included in device (my use case).

Total changes from Linux sources are in separate file [ListOfChanges](ListOfChanges). 

I use it since kernel 4.x on different distribution familys (Ubuntu, Debian, Arch ,Fedora, Redhat).

## Installing:

This module is based on kernel module replacing and is linked to others media sources of kernel, you need first to install closest kernel source for your distribtion.

As example, for Debian Bullseye, you can take : 

    wget https://mirrors.edge.kernel.org/pub/linux/kernel/v5.x/linux-5.10.tar.xz

Then uncompress it to the source directory:

    sudo tar -xf linux-5.10.tar.xz -C /usr/src

Next, get the repository to local:

    git clone https://github.com/enigma131/stb0899.git

If different kernel, you have to adjust the right path for KERNSRC and KERNELSOURCE in Makefile:

    nano stb0899/Makefile 

If changes made, save the file then exit nano.

Initialize the DKMS structure:

    sudo dkms add ./stb0899

Compile source / Install DKMS:

    sudo dkms install stb0899/enigma13

Verify result :

    dkms status

    modinfo stb0899

Reboot and test
