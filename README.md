TWRP device tree for Xiaomi Redmi 5 (rosy)
========================================================

<img alt="GitHub Releases" src="https://img.shields.io/github/downloads/Bodya-Kolibass/TWRP_device_xiaomi_rosy/3.3.0-0/total">   <img alt="GitHub Releases" src="https://img.shields.io/github/downloads/Bodya-Kolibass/TWRP_device_xiaomi_rosy/3.3.1-0/total">   <img alt="GitHub Releases" src="https://img.shields.io/github/downloads/Bodya-Kolibass/TWRP_device_xiaomi_rosy/3.3.1-1/total">

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
git apply -v ../../device/xiaomi/rosy/patches/0002-Change-default-font-some-gui-and-RU-translation-changes.patch    
git apply -v ../../device/xiaomi/rosy/patches/0003-Add-action-Reset-lockscreen.patch    
git apply -v ../../device/xiaomi/rosy/patches/0004-TWRP-add-an-option-to-exclude-the-TWRP-app.patch     
git apply -v ../../device/xiaomi/rosy/patches/0005-Fix-decrypt.patch   
git apply -v ../../device/xiaomi/rosy/patches/0006-Allow-Gui-File-Selector-filter-to-check-among-more-extensions.patch  
git apply -v ../../device/xiaomi/rosy/patches/0007-Add-the-ability-to-flash-image-bin-in-the-install-img-page.patch     
cd ../..    
. build/envsetup.sh   
lunch rosy-eng    
mka recoveryimage   
