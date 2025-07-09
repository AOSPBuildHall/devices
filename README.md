# Munch

## 📲 1. ROM Installation

### 🧹 Clean Flash

1. In recovery, flash the ROM and reboot back to recovery. (Use OrangeFox for Android 15 QPR2 and upper versions)
2. Flash GApps if you’re using a vanilla ROM (not needed for GMSCompat-included ROMs like VoltageOS) or skip this step.  
3. Format data and reboot to system.

### 🔄 Dirty Flash

1. In a custom recovery (e.g., TWRP, OrangeFox), flash the ROM via ADB sideload or from internal storage. (Use OrangeFox for Android 15 QPR2 and upper versions)
2. Reboot back to recovery.  
3. If using a vanilla ROM, flash the same GApps package again, wipe cache, and reboot to system.  
4. Updating via the built-in system updater does not require flashing GApps again, but it will overwrite your custom recovery with the default Lineage-style recovery.

---

## 🛠 2. Building ROMs

1. Make sure you have installed repo and all necessary dependencies.  
2. Initialize your ROM source.  
3. Copy [munch.xml ](https://github.com/AOSPBuildHall/devices/blob/munch/munch.xml)to .repo/local_manifests/munch.xml.  
4. Open .repo/manifests/default.xml (or lineage.xml / aosp.xml) and remove any devicesettings XML entry.  
5. To [sign your build](https://gist.github.com/A2L5E0X1/54cb1b3a49030a9ebf8608b4e68073f5), place your signing keys inside vendor/lineage-priv/keys/your_keys.  
6. *(Optional)* To enable KernelSU-Next, go to the kernel folder (kernel/xiaomi/sm8250-common), then run:
```bash
git submodule init && git submodule update && rm -rf KernelSU-Next/userspace/su
```

7. Build commands:
```bash
.  source build/envsetup.sh					
lunch lineage_munch-bp1a-userdebug				# bp1a: 15 qpr2 | ap4a: 15 qpr1	| ap3a: 15 qpr0	| ap2a: 14 qpr3 / -user -userdebug -eng
m bacon otatools target-files-package -j<number_of_threads>	
```

---

## ✅ 3. Suggestions & Downloads

Recommended GApps: Use NikGapps Core or the crDroid variant.

Updates & Support:
* [Poco F4 Updates Channel (There are more ROM variants, but they are released more slowly)](https://t.me/PocoF4updates)
* [Poco F4 Discussion Channel](https://t.me/PocoF4Discussions)
* [Munch AOSP Updates (There are less ROM variants, but they are released more faster)](https://t.me/munchPOCOF4)
* [Munch AOSP Support Group](https://t.me/munch_chat)

---

## 🐞 4. Bug Reporting

Use adb logcat or any logcat app to capture logs. Share the logs with the maintainer along with a detailed explanation of the issue.

## 🙏 5. Credits For This Wiki and Sources
- [efeisot](https://github.com/efeisot) :
	- https://github.com/AOSPBuildHall/devices/tree/munch
	- https://github.com/efeisot/android_device_xiaomi_munch
	- https://github.com/efeisot/android_device_xiaomi_sm8250-common

- [rik-x777](https://github.com/rik-x777) :
	- https://gitlab.com/rik-x777/vendor_xiaomi_munch
	- https://gitlab.com/rik-x777/vendor_xiaomi_sm8250-common
	- https://gitlab.com/rik-x777/vendor_xiaomi_munch-firmware

- [Olzhas0986](https://github.com/Olzhas-Kdyr) :
	- https://github.com/Olzhas-Kdyr/android_hardware_xiaomi

- [SenseiiX](https://github.com/SenseiiX) :
	- https://github.com/SenseiiX/fusionX_sm8250

- [hdzungx](https://github.com/hdzungx) :
	- https://codeberg.org/munch-devs/android_vendor_xiaomi_miuicamera

- [PocoF3Releases](https://github.com/PocoF3Releases) :
	- https://github.com/PocoF3Releases/packages_resources_devicesettings
