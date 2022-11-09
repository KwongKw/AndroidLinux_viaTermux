# AndroidLinux_viaTermux
To perform a linux envornment under non-root android system via Termux

## Introduction
This project is not something very useful, in fact, the intalled envronment is full of limitations that need time to tackle with,

- Arm64 (For most of the Android devices) is an architecture that not compatible with many packages
- Root access under the environment is virtual, not able to configure any kernel and device settings
- Not able to access and create device nodes in /dev
- Not able to run init systems
- Low performance

Then, why?

- Don't wanna bring my ~2kg laptop with my ~500g charger everytime when I go out
- Don't wanna buy a new light-weight laptop wile I am having a tablet
- The optimization for most android applications for tablet are bad
- like to mess around with my devices

The project is based on many similar projects on the internet, I do not own any copyright for any code, procedure below. It is just an integration project.

## Device information

Samsung Tab S7 (SM-T870), Android 12

## Procedures

### Setting up Termux

Get Termux from F-droid or Github release (__Not from Play Store__)

Provide the access permission of the storage space to termux
```{bash}
termux-setup-storage
```

Update packages to latest version
```{bash}
pkg update
```

If the device is in Android 12 or above, the Phantom Proceessing Killing must be disabled.

### Installing the Proot Environment

Install Proot-distro
```{bash}
pkg install proot-distro
```

Listing the available distros and installation
```{bash}
proot-distro list

# Arch is installed in the project
proot-distro install archlinux
```

Login to the distro after installation
```{bash}
proot-distro login archlinux
```

### Basic configuration in the distro (Arch)

Update the packages
```{bash}
pacman -Syu
```

In default, we are root, it is better to add a sudo user
```{bash}
# Change passwod of the root
passwd

# add a user to the distro
useradd -m -g users -G wheel,audio,video,storage {User_Name}
passwd kwongkw

# install the sudo package
pacman -S sudo

# Modifying the sudoers file
vi /etc/sudoers
```
Add sudo user by modifying the sudoers file
template:
```{bash}
...
root ALL=(ALL:ALL) ALL
{User_Name} ALL=(ALL:ALL) ALL
...
```

Login to the user
```{bash}
su {User_Name}
```

### Install the desktop environment

Install XFCE desktop environment
```{bash}
sudo pacman -S xfce4 xfce4-goodies lightdm
```

### VNC
### Termux-x11