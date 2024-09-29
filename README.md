# How to Build

## Introduction to DTK

DTK (deepin tool kit) is a comprehensive UI graphics library developed based on Qt5, designed to facilitate the creation of a unified style for the deepin desktop and deepin series applications. Its main features include:

- Providing a single instance interface for direct use, eliminating the need to reinvent the wheel.
- Offering a series of functions for XCB window movement, resizing, and other operations, suitable for borderless windows.
- Providing aesthetically pleasing custom-drawn controls that can be directly dragged and used.

DTK Link: [https://github.com/orgs/linuxdeepin/repositories?q=dtk](https://github.com/orgs/linuxdeepin/repositories?q=dtk)

**DTK Core Repositories:**

- **dtkcore:** [https://github.com/linuxdeepin/dtkcore](https://github.com/linuxdeepin/dtkcore)
- **dtkgui:** [https://github.com/linuxdeepin/dtkgui](https://github.com/linuxdeepin/dtkgui)
- **dtkwidget:** [https://github.com/linuxdeepin/dtkwidget](https://github.com/linuxdeepin/dtkwidget)
- **qt5integration:** [https://github.com/linuxdeepin/qt5integration](https://github.com/linuxdeepin/qt5integration)

> To compile and install dtk components from source, please follow the sequence of dtkcore > dtkgui > dtkwidget, ensuring that the versions of dtkcore, dtkgui, and dtkwidget are consistent. Compilation risks are at your own discretion!!

> If you do not wish to participate in development, it is recommended that you switch to the corresponding tag version for building.

## Basic Environment

If you need to compile DTK components from source, you must first install the basic environment. Open the terminal and enter the following command:

```bash
sudo apt install git build-essential cmake devscripts doxygen graphviz
```

## Installation and Compilation of dtkcore

dtkcore is the core component of DTK, equivalent to the core component in Qt5. This component is installed by default in the Deepin system. If you need to reinstall it, open the terminal and enter the following command:

```bash
sudo apt install libdtkcore5 --reinstall
sudo apt install libdtkcore-dev      # Libraries required for development software
```

If you are compiling from source, follow these steps:

```bash
git clone -b [tags] https://github.com/linuxdeepin/dtkcore.git
cd dtkcore
sudo apt build-dep ./
cmake -B build
cmake --build build -j$(nproc)
```

If you need to install after compilation, there are two optional methods:

```bash
debuild -us -uc -b    # Package into a deb package for sharing with others
sudo make install     # Install from source
```

> It is recommended to use the debuild command.
>
> The make install command is suitable for packaging and calling. Direct installation in this way may disrupt the environment; risks are at your own discretion.

## Installation and Compilation of dtkgui

dtkgui is the graphical core component of DTK, equivalent to the gui component in Qt5. This component is installed by default in the Deepin system. If you need to reinstall it, open the terminal and enter the following command:

```bash
sudo apt install libdtkgui5 --reinstall
sudo apt install libdtkgui-dev      # Libraries required for development software
```

If you are compiling from source, follow these steps:

```bash
git clone -b [tags] https://github.com/linuxdeepin/dtkgui.git
cd dtkgui
sudo apt build-dep ./
cmake -B build
cmake --build build -j$(nproc)
```

If you need to install after compilation, there are two optional methods:

```bash
debuild -us -uc -b    # Package into a deb package for sharing with others
sudo make install     # Install from source
```

> It is recommended to use the debuild command.
>
> The make install command is suitable for packaging and calling. Direct installation in this way may disrupt the environment; risks are at your own discretion.

## Installation and Compilation of dtkwidget

dtkwidget is the core component of DTK, equivalent to the widget component in Qt5. This component is installed by default in the Deepin system. If you need to reinstall it, open the terminal and enter the following command:

```bash
sudo apt install libdtkwidget5 --reinstall
sudo apt install libdtkwidget-dev      # Libraries required for development software
```

If you are compiling from source, follow these steps:

```bash
git clone -b [tags] https://github.com/linuxdeepin/dtkwidget.git
cd dtkwidget
sudo apt build-dep ./
cmake -B build
cmake --build build -j$(nproc)
```

If you need to install after compilation, there are two optional methods:

```bash
debuild -us -uc -b    # Package into a deb package for sharing with others
sudo make install     # Install from source
```

> It is recommended to use the debuild command.
>
> The make install command is suitable for packaging and calling. Direct installation in this way may disrupt the environment; risks are at your own discretion.

## Installation and Compilation of qt5integration

qt5integration is the plugin component of DTK, equivalent to the plugin component in Qt5. This component is installed by default in the Deepin system. If you need to reinstall it, open the terminal and enter the following command:

```bash
sudo apt install qt5integration --reinstall
```

If you are compiling from source, follow these steps:

```bash
git clone -b [tags] https://github.com/linuxdeepin/qt5integration.git
cd qt5integration
mkdir build && cd build
sudo apt build-dep ../
qmake ..
make
```

If you need to install after compilation, there are two optional methods:

```bash
sudo make install     # Install from source
debuild -us -uc -b    # Package into a deb package for sharing with others
```