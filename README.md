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

### Installing the envornmnt

Get Termux from F-droid or Github release (__Not from Play Store__)

Provide the access permission of the storage space to termux
`termux-setup-storage`

Update packages to latest version
`pkg update`

