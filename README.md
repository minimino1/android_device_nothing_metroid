# Android Device Tree for Nothing Phone (3) - Metroid

OrangeFox Recovery device tree for Nothing Phone (3) (codename: Metroid, model: A024)

## Device Specifications

| Feature  | Specification                  |
| -------- | ------------------------------ |
| Chipset  | Qualcomm Snapdragon 8s Gen 4   |
| Platform | sun                            |
| CPU      | Octa-core                      |
| GPU      | Adreno                         |
| Memory   | 8/12 GB                        |
| Storage  | 256/512 GB                     |
| Display  | 6.7" 1080 x 2400 pixels, 120Hz |

## Current Status

| Feature        | Status               |
| -------------- | -------------------- |
| Boot           | ✅ Working           |
| Touch          | ✅ Working           |
| ADB            | ✅ Working           |         
| Sideload       | ✅ Working           |
| Backup/Restore | ❌ Not Working (WIP) |     
| Encryption     | ❌ Not Working (WIP) |

## Build a bootable recovery image

This repository is a device tree and must be used inside a full OrangeFox/TWRP source tree.

1. Sync a compatible Android 12/12.1-era OrangeFox/TWRP source tree.
2. Place this tree at:
   - `/path/to/recovery/source/device/nothing/Metroid`
   - (or symlink it there from your local clone)
3. In the recovery source root:
   - `source build/envsetup.sh`
   - `lunch twrp_Metroid-eng`
   - `mka recoveryimage`
4. The output image will be:
   - `out/target/product/Metroid/recovery.img`

## Flash and verify

This device tree is configured as A/B with a dedicated recovery partition, so flash `recovery.img` directly to `recovery`.

1. Reboot to bootloader.
2. Flash:
   - `fastboot flash recovery out/target/product/Metroid/recovery.img`
3. Boot directly to recovery and verify:
   - touch works
   - ADB works
   - sideload works
