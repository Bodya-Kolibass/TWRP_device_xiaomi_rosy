TWRP device tree for Xiaomi Redmi 5 (rosy)
========================================================
How to build:
--------------------------------------------
mkdir omni_8.1
cd omni_8.1
repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-8.1
repo sync -f --force-sync
mkdir device && mkdir device/xiaomi && mkdir device/xiaomi/rosy
git clone https://github.com/Bodya-Kolibass/TWRP_device_xiaomi_rosy.git -b android-8.1 device/xiaomi/rosy
cd bootable/recovery
git apply -v ../../device/xiaomi/rosy/patches/0001-Delete-all-languages-except-EN-and-RU.patch
git apply -v ../../device/xiaomi/rosy/patches/0002-Add-action-Reset-lockscreen.patch
cd ../..
. build/envsetup.sh
lunch rosy-eng
mka recoveryimage
