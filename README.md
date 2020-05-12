# quick-start
ULX3S Quick Start


# Getting toolchain binaries

## Mac OS X support

If you're using homebrew it is enough to add homebrew tap and add packages:

```
brew tap kost/homebrew-ulx3s
brew install --HEAD project-trellis yosys nextpnr-trellis fujprog
```

## Windows support

You can download complete ECP5 toolchain from https://github.com/FPGAwars/toolchain-ecp5/releases

## Linux support

You can download complete ECP5 toolchain from https://github.com/FPGAwars/toolchain-ecp5/releases

If you want to download Intel x86_64 latest binaries, you can download them from the https://github.com/alpin3/ulx3s/releases


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

## Building Linux toolchain from source without docker

Another way is to use scripts to build complete toolchain https://github.com/ulx3s/ulx3s-toolchain

```
git clone https://github.com/ulx3s/ulx3s-toolchain
cd ulx3s-toolchain
./install_all.sh
```

