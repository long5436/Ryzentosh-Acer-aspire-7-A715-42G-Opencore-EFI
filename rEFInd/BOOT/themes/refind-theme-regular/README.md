## Minimalistic black rEFInd theme

[rEFInd](http://www.rodsbooks.com/refind/) is a simplistic boot manager for UEFI
based systems. This is a clean and minimal black theme for it.

![rEFInd Minimalistic](screenshot.png)

### Usage

1. Locate your refind EFI directory. In our OpenCore [hackintosh](https://github.com/chriswayg/hackintosh-opencore/tree/master/rEFInd-BOOT-folder) use case the refind directory is `/EFI/BOOT/` though it will depend on where you mount your ESP and where rEFInd is
   installed.

2. Clone this repository into the applicable refind directory.

3. To enable the theme add `include theme-minimal-black/theme.conf` at the end of
   `refind.conf`.

Here's an example hackintosh menuentry configuration

```nginx
menuentry "Arch Linux" {
    icon /EFI/BOOT/theme-minimal-black/icons/os_arch.png
    loader vmlinuz-linux
    initrd initramfs-linux.img
    options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows 10" {
    loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "OpenCore" {
    ostype   "MacOS"
    graphics "on"
    icon     /EFI/BOOT/theme-minimal-black/icons/os_opencore.png
    volume   "EFI"
    loader   /EFI/OC/OpenCore.efi
}
```

Entries that are autodetected should also show the proper icons.

### Attribution

Original minmal theme: [evanpurkhiser.com/refind-minimal](http://evanpurkhiser.com/rEFInd-minimal "http://evanpurkhiser.com/rEFInd-minimal")

Original minimal black theme: [andersfischernielsen/rEFInd-minimal-black](https://github.com/andersfischernielsen/rEFInd-minimal-black)

The original OS icons are from [Lightness for burg][icons] by [SWOriginal][icon-author].

The OpenCore icon is from [acidanthera/OpenCorePkg](https://github.com/acidanthera/OpenCorePkg/tree/master/Docs/Logos)

[icons]: http://sworiginal.deviantart.com/art/Lightness-for-burg-181461810
[icon-author]: http://sworiginal.deviantart.com/

[chriswayg]: https://github.com/chriswayg/theme-minimal-black
