# QEMU
the FAST! processor emulator

QEMU is a processor and machine emulator for many processors (although the KaOS KCP package only supports x86_64 emulation). It is most commonly used with KVM to provide fast, efficient virtualization.

The QEMU package can be installed on its own, but for best results it is recommended you install the spice-protocol, spice, usbredir, slirp, and virglrenderer packages first. These will enable extra QEMU features, providing better emulated graphics hardware, easy user-mode networking, and the ability to use SPICE clients with QEMU for enabling shared clipboard, drag-n-drop file sharing, and folder sharing. To install everything in the right order, use the following sequence of commands:

```
kcp -u
kcp -i spice-protocol
kcp -i spice
kcp -i usbredir
kcp -i slirp
kcp -i virglrenderer
kcp -i qemu
```

These packages should be updated in this same order to ensure they continue working together correctly.
