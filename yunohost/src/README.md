
## Prerequisites

It is recommended to build the ARM images from a Docker container.

## Usage

Download the base image according to your board in the `./image` directory:
- Raspberry Pi 3 or 4: https://downloads.raspberrypi.org/raspios_lite_arm64_latest
- Olimex Lime2: https://archive.armbian.com/lime2/archive/Armbian_23.02.2_Lime2_bullseye_current_5.15.93_minimal.img.xz
- Odroid N2/N2+: https://archive.armbian.com/odroidn2/archive/Armbian_23.02.2_Odroidn2_bullseye_current_6.1.11_minimal.img.xz
- Odroid XU4: https://archive.armbian.com/odroidxu4/archive/Armbian_23.02.1_Odroidxu4_bullseye_current_5.4.232_minimal.img.xz
- Odroid HC4: https://archive.armbian.com/odroidhc4/archive/Armbian_23.02.2_Odroidhc4_bullseye_current_6.1.11_minimal.img.xz

For instance:
```bash
wget --trust-server-names https://downloads.raspberrypi.org/raspios_lite_arm64_latest -P ./image
```

Uncompress the image. For instance:
```bash
unxz ./image/2023-05-03-raspios-bullseye-arm64-lite.img.xz
```

Build the image to install Yunohost. The `build_dist` script will try to detect the correct parameter for your board.

For a Raspberry Pi:
```bash
./build_dist docker BOARD=rpi
```

For armbian-based boards (Olimex, Odroid, etc.):
```bash
./build_dist docker BOARD=lime2
```
Change the `BOARD` variable according to your board.

This will create a Yunohost image in the `./output` directory.

### Internet Cube

Once you built an image with Yunohost installed, you can reuse it to deploy the internet cube installer.

Copy the Yunohost image to the `./image` directory and then build your image with the variable `YNH_BUILDER_INSTALLER=internetcube`.

For instance:
```bash
./build_dist docker BOARD=rpi YNH_BUILDER_INSTALLER=internetcube
```

Your image will be stored in the `./output` directory.

### Clic

Once you built an image with Yunohost installed, you can reuse it to deploy the clic installer.

Copy the Yunohost image to the `./image` directory and then build your image with the variable `YNH_BUILDER_INSTALLER=clic`.

For instance:
```bash
./build_dist docker BOARD=rpi YNH_BUILDER_INSTALLER=clic
```

Your image will be stored in the `./output` directory.
