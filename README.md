# Qemu

This snap includes kvm tool to run virtual guest machines over a host machine

see [Qemu](https://www.qemu.org/)
see [KVM](https://wiki.qemu.org/Features/KVM)

## Requirements

Only tested on x86 host machine

## Installation

In a snap enabled system type

```
snap install qemu-rmescandon 
snap connect qemu:kvm core:kvm
```

## How to use

After snap installation you can launch kvm by using ```qemu.kvm``` with the params you desire.
For instance

```
qemu.kvm -snapshot -m 1500 -net nic -net user,hostfwd=tcp:127.0.0.1:59327-:22 -serial telnet:127.0.0.1:59427,server,nowait -monitor telnet:127.0.0.1:59527,server,nowait ./ubuntu-core-16.img
```

Where the image file should be?. Any path within home folder will be accessible.