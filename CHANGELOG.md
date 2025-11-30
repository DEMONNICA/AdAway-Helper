> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [1.5.0]
>
> - `customize.sh`: Introduced detailed `root_detect_magisk` function for identifying Magisk variants (Stable, Canary, Kitsune, Alpha) with precise version printing and frog icon.
> - Enhanced `root_detect_apatch` with `dumpsys` for APK version extraction, GitHub API for latest KernelPatch tag, and persistent file writing to `/data/adb/ap/version` and `kernelver`.
> - Added new `root_detect_ksunki` for granular KernelSU detection (Standard, Next, SukiSU Ultra) using package checks and `su -c ksud` fallback with panda/bear icons.
> - Updated `display_device_info` to capitalize device name; introduced `display_soc_info` for automatic Snapdragon/MediaTek SOC detection via multiple `ro.*` props.
> - Expanded `FILES_TO_EXTRACT` to include `post-fs-data.sh` and `service.sh`; renamed system image from `AdAway_Helper.jpg` to `ADH.jpg`; added strict root method validation.
> - Implemented robust `/system/etc/hosts` installation with error-handling, `chmod 644`, `worker` dir creation, and streamlined 15-variant devil messages.
> - Added conditional overlay mount for KernelSU using `worker` directory to ensure proper `/system/etc/hosts` overlay on all root methods.
---

> [1.0.0] `FIX`
>
> - Optimized hosts file mounting in `customize.sh` with `mount -o bind` and fallback to copy, ensuring reliable ad-blocking across root environments.
> - Added SELinux context restoration in `customize.sh` using `busybox chcon` to match `/system/etc/hosts` for seamless integration.
> - Updated `service.sh` to replace `[BETA]` with `[FIX]` in `module.prop`, reflecting improved module stability.
> - Enhanced `service.sh` with fallback `cp -f` for hosts file if `mount -o bind` fails, improving compatibility on diverse devices.
> - Removed redundant `skip_mount` file creation in `customize.sh` for cleaner installation process.
> - Streamlined author update in `service.sh` by assuming existing author line, simplifying `module.prop` modifications.
> - Minor tweaks for consistent execution and error handling across scripts.
---

> [0.5.0] `BETA`
>
> - Initial release.
---