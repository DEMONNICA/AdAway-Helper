> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [4.0.0]
>
> - Added `detect_adaway` check at the start of `customize.sh` — aborts installation if AdAway (`org.adaway`) is not installed.
> - Added `get_app_label` function in `customize.sh` to dynamically retrieve AdAway app name from APK via `strings`.
> - Added `post-fs-data.sh` for early boot bind mount of hosts file.
> - Added boot wait (`sys.boot_completed`) in `service.sh` before refreshing AdAway.
> - Added `restorecon` on `/system/etc/hosts` after bind mount in `post-fs-data.sh`.
> - Changed `service.sh` — mount logic moved to `post-fs-data.sh`, now only handles AdAway refresh and notification.
> - Fixed AdAway unable to write new hosts file on APatch — caused by missing boot wait and mount running too late.
> - Removed `SKIPUNZIP=1` and `DEBUG=false` from `customize.sh`.
> - Removed `zip=$(clean_path "$zip")` from `extract()` in `verify.sh`.
> - Removed `worker` directory from `prepare_hosts` — overlay mount no longer used.
---

> [3.5.0]
>
> - Added `FolkLite` (`mi.yuki.folk`) detection to `detect_root_all`.
> - Added numbered comments throughout `customize.sh` for better readability.
> - Added auto-refresh of AdAway after hosts file is mounted.
> - Added system notification in `service.sh` after hosts is applied.
> - Added `chmod 644` on hosts file after mounting.
> - Changed license from GNU General Public License to Apache License 2.0.
> - Changed structure of `README.md` for a better impression.
> - Changed `README.md` description and feature list.
> - Changed `customize.sh` and `verify.sh` for better future performance.
> - Changed `detect_root_all` to match latest root manager variants.
> - Changed `set_donate_link` timezone detection with multiple fallbacks.
> - Fixed `local var=$(...)` declarations for better shell compatibility.
> - Fixed `post_install_actions` missing `NAME_MODULE` definition.
> - Fixed bind mount not allowing AdAway to write new hosts file.
> - Removed `display_soc_info` and `socs.json` dependency.
---

> [3.0.0]
>
> - Added `Donate` action in module.
> - Changed improved detection of root manager method.
> - Changed various code improvements in `customize.sh`.
> - Removed emoji and `worker` folder after mounting is complete.
> - Removed unnecessary code in `verify.sh`.
---

> [2.5.0]
>
> - Changed banner.
> - Changed minor improvements to mount handling.
> - Changed `customize.sh` and `verify.sh` for more complex handling.
---

> [2.0.0]
>
> - Added `prepare_hosts` function to centralize hosts file preparation, copying, and overlay mount setup.
> - Changed extracted files categorization: separated into module files (`service.sh`, `module.prop`) and assets (`ADH.jpg`).
> - Changed hosts file handling, permissions, and worker directory creation moved from main script to `prepare_hosts`.
> - Changed bind mount logic in `service.sh` to conditionally copy if bind fails, without fallback `true`.
> - Changed overlay mount in `service.sh` to remove unconditional `|| true` for better error control.
> - Removed explicit PATH modifications and sdcardfs filesystem check.
> - Removed mandatory dependency checks for `sha1sum`, `sha224sum`, `sha384sum`, `sha512sum`, `awk`, and `sed`.
---

> [1.5.0]
>
> - Added `root_detect_magisk` function for identifying Magisk variants (Stable, Canary, Kitsune, Alpha) with precise version printing.
> - Added `root_detect_apatch` with `dumpsys` for APK version extraction and GitHub API for latest KernelPatch tag.
> - Added `root_detect_ksunki` for granular KernelSU detection (Standard, Next, SukiSU Ultra) using package checks and `su -c ksud` fallback.
> - Added `display_soc_info` for automatic Snapdragon/MediaTek SOC detection via multiple `ro.*` props.
> - Added `post-fs-data.sh` and `service.sh` to `FILES_TO_EXTRACT`.
> - Added conditional overlay mount for KernelSU using `worker` directory.
> - Added strict root method validation.
> - Added streamlined 15-variant devil messages.
> - Changed `display_device_info` to capitalize device name.
> - Changed system image renamed from `AdAway_Helper.jpg` to `ADH.jpg`.
> - Changed robust `/system/etc/hosts` installation with error-handling, `chmod 644`, and `worker` dir creation.
---

> [1.0.0]
>
> - Added SELinux context restoration in `customize.sh` using `busybox chcon` to match `/system/etc/hosts`.
> - Added fallback `cp -f` in `service.sh` for hosts file if `mount -o bind` fails.
> - Changed optimized hosts file mounting in `customize.sh` with `mount -o bind` and fallback to copy.
> - Changed `service.sh` to replace `[BETA]` with `[FIX]` in `module.prop`.
> - Changed streamlined author update in `service.sh` by assuming existing author line.
> - Fixed minor tweaks for consistent execution and error handling across scripts.
> - Removed redundant `skip_mount` file creation in `customize.sh`.
---

> [0.5.0]
>
> - Initial release.
---