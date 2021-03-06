# PKGBUILD files for building Leptonica and Tesseract-OCR 4.0 on Windows

This repo provides two PKGBUILD files for building both Leptonica and Tesseract OCR on Windows using the MSYS2 build system.

MSYS2 ported the `pacman` package manager from Arch Linux, which has a simple syntax for searching for and installing packages. 

## Usage

1. Install MSYS2 from [here](https://www.msys2.org/) and follow their getting started steps.

In the MSYS2 terminal, do the following,

2. Install the development tools needed to build software from source by running:

```
pacman -S base-devel
```

3. Clone this repo and `cd` to it

```
git clone git@github.com:mespe/Tesseract4-MSYS2.git
cd Tesseract4-MSYS2
```

4. Install leptonica from MSYS2 repos

```
pacman -S leptonica
```

**Alternative: Install Leptonica from source**

Use the PKGBUILD file located in the leptonica folder,

```
cd leptonica
makepkg -sri
cd ..
```

4. Update the pkg-config search path

By default, pkg-config does not look in the /mingw64 directory, so you need to set the `PKG_CONFIG_PATH` variable,

```
export PKG_CONFIG_PATH=/mingw64/lib/pkgconfig/
```

5. Build package

Using the PKGBUILD file, issue the following command to build Tesseract

```
cd tesseract
makepkg -sri
```

