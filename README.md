TWRP device tree for Xiaomi Redmi 5 (rosy)
========================================================

<img alt="GitHub Releases" src="https://img.shields.io/github/downloads/Bodya-Kolibass/TWRP_device_xiaomi_rosy/3.3.0-0/total">   <img alt="GitHub Releases" src="https://img.shields.io/github/downloads/Bodya-Kolibass/TWRP_device_xiaomi_rosy/3.3.1-0/total">   <img alt="GitHub Releases" src="https://img.shields.io/github/downloads/Bodya-Kolibass/TWRP_device_xiaomi_rosy/3.3.1-1/total">   <img alt="GitHub Releases" src="https://img.shields.io/github/downloads/Bodya-Kolibass/TWRP_device_xiaomi_rosy/3.5.0_9-0/total">   <img alt="GitHub Releases" src="https://img.shields.io/github/downloads/Bodya-Kolibass/TWRP_device_xiaomi_rosy/3.5.2_9-0/total">

How to build:
--------------------------------------------
mkdir omni_8.1    
cd omni_8.1   
repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-8.1   
repo sync -f --force-sync   
mkdir device && mkdir device/xiaomi && mkdir device/xiaomi/rosy   
git clone https://github.com/Bodya-Kolibass/TWRP_device_xiaomi_rosy.git -b android-8.1 device/xiaomi/rosy   
rm -rf bootable/recovery    
git clone https://github.com/Bodya-Kolibass/android_bootable_recovery.git -b rosy-3.5.2 bootable/recovery    
. build/envsetup.sh   
lunch rosy-eng    
mka recoveryimage   
