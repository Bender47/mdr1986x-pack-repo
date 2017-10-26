# Milandr MCU 1986x CMSIS Pack Repository

This repository contains an unofficial Milandr MCU 1986x CMSIS Pack for [GNU MCU Eclipse][packs-manager]
and [Keil MDK 5][packinstaller].

You could download it manually – [_"Milandr.MDR1986BExx.1.4.2.pack"_][pack], or install directly from
this repository.

### How to install the package (Eclipse)

- [Add][packs-manager-config] Milandr MCU repository, specifying the path to [_"index.pidx"_][index.pidx]
file:
```
Eclipse Menu → Window → Preferences → C/C++ → Packages → Repositories → Add...

Type       CMSIS Pack
Name       Milandr
URL        https://raw.githubusercontent.com/in4lio/mdr1986x-pack-repo/master/index.pidx
```
With old versions of Packs Manager, you should use [_"index.idx"_][index.idx] file.

- [Open][packs-manager-persp] the Packs perspective and [install][packs-manager-install] `MDR1986BExx`
package from `Milandr` group.

- The path to the packages is defined in `packs_path` macro, but for the plug-in version that I use,
this macro is not visible from tools configurations. Therefore, you may also need to set `packs_path`
macro manually:
```
Eclipse Menu → Window → Preferences → Run/Debug → String Substitution → New...

Name       packs_path
Value      <path to packages>
```

### How to examine/modify the peripheral registers (Eclipse)

[The peripherals registers view][debug-registers]

### Supported MCUs

[Milandr 32-bit АRМ Cortex-М microcontrollers][milandr-mdr1986x]

- 1986BE9x (MDR32F9Qx)
- 1986BE1 (MDR32F1)
- 1986BE3
- 1986BE4

### The package source list

- [Milandr MCU 1986x Standard Peripherals Library][mdr1986x-std-lib]
- [Milandr MCU 1986x Standard Peripherals Library Documentation][mdr1986x-std-lib-doc]
- [Milandr MCU 1986BExx CMSIS Driver][mdr1986x-CMSIS]
- [Milandr MCU 1986x flashing with J-Link][mdr1986x-JFlash]
- [Milandr MCU 1986BE3T UDP Library][mdr1986x-UDP]
- [Example Projects for GNU ARM Eclipse][mdr1986x-projects]

### How to rebuild the package

- Clone this repository and its submodules if they are not cloned yet:

```
git clone https://github.com/in4lio/mdr1986x-pack-repo.git
cd mdr1986x-pack-repo
git submodule update --init --recursive
```

- Or, update this repository and submodules if they are already cloned:

```
cd mdr1986x-pack-repo
git pull origin master
git submodule foreach git pull origin master
```

- Run the build script with Python 2:

```
python .\build.py
```

[milandr-mdr1986x]:      http://ic.milandr.ru/products/mikrokontrollery_i_protsessory/32_razryadnye_mikrokontrollery/
[packinstaller]:         http://www2.keil.com/mdk5/packinstaller/
[packs-manager]:         https://gnu-mcu-eclipse.github.io/plugins/packs-manager/
[packs-manager-config]:  https://gnu-mcu-eclipse.github.io/plugins/packs-manager/#configuration
[packs-manager-persp]:   https://gnu-mcu-eclipse.github.io/plugins/packs-manager/#the-packs-perspective
[packs-manager-install]: https://gnu-mcu-eclipse.github.io/plugins/packs-manager/#pack-install
[debug-registers]:       https://gnu-mcu-eclipse.github.io/debug/peripheral-registers/
[pack]:                  https://raw.githubusercontent.com/in4lio/mdr1986x-pack-repo/master/Milandr.MDR1986BExx.1.4.2.pack
[index.pidx]:            https://raw.githubusercontent.com/in4lio/mdr1986x-pack-repo/master/index.pidx
[index.idx]:             https://raw.githubusercontent.com/in4lio/mdr1986x-pack-repo/master/index.idx
[mdr1986x-std-lib]:      https://github.com/eldarkg/emdr1986x-std-per-lib
[mdr1986x-std-lib-doc]:  https://github.com/eldarkg/emdr1986x-std-per-lib-doc
[mdr1986x-CMSIS]:        https://github.com/in4lio/mdr1986x-pack-repo/tree/master/source/CMSIS_Driver
[mdr1986x-JFlash]:       https://github.com/in4lio/mdr1986x-JFlash
[mdr1986x-projects]:     https://github.com/in4lio/mdr1986x-pack-repo/tree/master/source/Example_Projects_Eclipse
[mdr1986x-UDP]:          https://github.com/in4lio/mdr1986x-pack-repo/tree/master/source/Example_Projects_Eclipse/1986BE3_UDP
