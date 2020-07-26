# quick-start
ULX3S Quick Start

# Know your programmer!

Newer versions of the ULX3S, such as those shipped to [Crowd Supply](https://www.crowdsupply.com/radiona/ulx3s) backers, 
require the [latest version of fujprog](https://github.com/kost/fujprog/releases). Older versions of `fujprog` as well
as [ujprog](https://github.com/f32c/tools/tree/master/ujprog) *MAY NOT WORK PROPERLY*. Further, running the [test scripts](https://github.com/goran-mahovlic/ULX3S_testing)
on prior versions of the ULX3S may update the FTDI software, which in turn will also make the prior versions of the programmers no longer function. 
See [fujprog issue #5](https://github.com/kost/fujprog/issues/5)

# Getting toolchain binaries

## Linux binaries

You can download complete ECP5 toolchain from https://github.com/FPGAwars/toolchain-ecp5/releases

If you want to download Intel x86_64 latest binaries, you can download them from the https://github.com/alpin3/ulx3s/releases

## Mac OS X support

If you're using homebrew it is enough to add homebrew tap and add packages:

```
brew tap kost/homebrew-ulx3s
brew install --HEAD project-trellis yosys nextpnr-trellis fujprog
```

## Windows support

You can download complete ECP5 toolchain from https://github.com/FPGAwars/toolchain-ecp5/releases

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

# Next steps

Now, you're ready for the next steps, we suggest following:

  - https://github.com/ulx3s/fpga-odysseus
  - https://github.com/emard/ulx3s-examples
  - https://github.com/emard/ulx3s-bin
  - https://github.com/kost/ulx3s-ghdl-examples/

Or explore different projects available at: https://ulx3s.github.io/


