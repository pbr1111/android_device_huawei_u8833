CyanogenMod device configuration for the Huawei Ascend Y300/G510.

How to Build
---------------

Initialise from CyanogenMod:

    repo init -u git://github.com/CyanogenMod/android.git -b jellybean

Use the following local manifest:

    <?xml version="1.0" encoding="UTF-8"?>
	<manifest>
	<remove-project name="CyanogenMod/android_vendor_cm" />
	<project name="pbr1111/android_device_huawei_u8833" path="device/huawei/u8833" revision="jellybean" />
	<project name="pbr1111/android_kernel_huawei_msm8x25-common" path="kernel/huawei/u8833" revision="jb" />
	<project name="pbr1111/proprietary_vendor_huawei" path="vendor/huawei" revision="jellybean" />

	<!-- FM Radio -->
	<project path="hardware/qcom/fm" name="legaCyMod/android_hardware_qcom_fm" revision="jellybean" />
	<project path="packages/apps/FM2" name="legaCyMod/android_packages_apps_FM2" revision="jellybean" />
	
	<!-- QCom legacy -->
	<project name="Dazzozo/android_hardware_qcom_display-legacy" path="hardware/qcom/display-legacy" revision="jellybean-mr2" />
	<project name="Dazzozo/android_hardware_qcom_media-legacy" path="hardware/qcom/media-legacy" revision="jellybean-mr2" />

	<!-- WiFi -->
	<project name="legaCyMod/android_hardware_atheros_wlan" path="hardware/atheros/wlan" revision="jellybean" />
	<project name="Dazzozo/android_hardware_atheros_wifi_ath6kl-huawei" path="hardware/atheros/wifi/ath6kl-huawei" revision="master" />

	<!-- CM Vendor --> 
	<project name="pbr1111/android_vendor_cm" path="vendor/cm" revision="jellybean" />
	</manifest>

Sync and build:

    repo sync -j4
    vendor/cm/get-prebuilts
    . build/envsetup.sh
    brunch u8833
