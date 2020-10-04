# quick-start
ULX3S Quick Start

# Getting toolchain binaries

## Precompiled opensource tools for all platforms

  - https://github.com/emard/ulx3s/blob/master/doc/MANUAL.md#precompiled-opensource-tools-for-all-platforms

On linux based systems you may also need to add a udev rule to enable user access to the usb device, once added you’ll need to un-plug and reconnect the ULX3S for it to take effect

```
$ cat /etc/udev/rules.d/80-fpga-ulx3s.rules
# file: /etc/udev/rules.d/80-fpga-ulx3s.rules
# this is for usb-serial tty device
SUBSYSTEM=="tty", ATTRS{idVendor}=="0403", ATTRS{idProduct}=="6015", \
  MODE="664", GROUP="dialout"
# this is for ujprog libusb access
ATTRS{idVendor}=="0403", ATTRS{idProduct}=="6015", \
  GROUP="dialout", MODE="666"
```

# Building toolchain from source

If you want to build complete toolchain from source, there are different ways to build it.

## Building Linux toolchain from source with docker

If you want to build complete toolchain yourself, you can rebuild complete toolchain using docker:

```
git clone https://github.com/alpin3/ulx3s/
cd ulx3s
make build
make bins
```

## Building Barebones Linux toolchain

(coming soon)

This installs only the bare essentials (yosys/nextpnr/fujprog) to get started with FPGA programming.

For ESP32, RISC-V and other features - see the full toolchain.

## Building Full Linux toolchain from source without docker

Another way is to use scripts to build complete toolchain https://github.com/ulx3s/ulx3s-toolchain

```
sudo apt-get install git --assume-yes
mkdir -p ~/workspace
cd ~/workspace

git clone https://github.com/ulx3s/ulx3s-toolchain.git
cd ulx3s-toolchain
chmod +x ./install_all.sh
./install_all.sh
```

## Building Full Windows Subsystem for Linux (WSL) toolchain from source without docker

This buld assumes [WSL](https://docs.microsoft.com/en-us/windows/wsl/faq) is already installed. WSL2 has not yet been tested.

The only difference from regular Linux install is this one puts files on the `C:\Workspace` directory 
for safe and easy access from Windows. 
Be aware of the [dangers](https://devblogs.microsoft.com/commandline/do-not-change-linux-files-using-windows-apps-and-tools/)
of editing WSL file system from Windows.

```
sudo apt-get install git --assume-yes
mkdir -p /mnt/c/workspace/
cd /mnt/c/workspace/

git clone https://github.com/ulx3s/ulx3s-toolchain.git
cd ulx3s-toolchain
chmod +x ./install_all.sh
./install_all.sh
```
# Know your programmer!

Newer versions of the ULX3S, such as those shipped to [Crowd Supply](https://www.crowdsupply.com/radiona/ulx3s) backers, require the [latest version of fujprog](https://github.com/kost/fujprog/releases). 

Older versions of `fujprog` as well as [ujprog](https://github.com/f32c/tools/tree/master/ujprog) *MAY NOT WORK PROPERLY*.

# Next steps

Now, you're ready for the next steps, we suggest following:

  - https://github.com/emard/ulx3s/blob/master/doc/MANUAL.md
  - https://github.com/emard/ulx3s-misc
  - https://github.com/ulx3s/fpga-odysseus
  - https://github.com/emard/ulx3s-examples
  - https://github.com/emard/ulx3s-bin
  - https://github.com/kost/ulx3s-ghdl-examples/

Discord chanel

  - https://discord.gg/qwMUk6W

Gitter chanel

  - https://gitter.im/ulx3s/Lobby (Focused on deevelopment)

Or explore different projects available at: https://ulx3s.github.io/


