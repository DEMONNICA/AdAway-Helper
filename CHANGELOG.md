> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.5.0]
>
> - License Changes.
> - Changed the structure of `README.md` for a better impression.
> - Updated `README.md` description and feature list.
> - Updated `customize.sh` and `verify.sh` for better future performance.
> - Improved `detect_root_all` to match latest root manager variants.
> - Improved `set_donate_link` timezone detection with multiple fallbacks.
> - Fixed `local var=$(...)` declarations for better shell compatibility.
> - Fixed `post_install_actions` missing `NAME_MODULE` definition.
> - Fixed bind mount not allowing AdAway to write new hosts file.
> - Added `chmod 644` on hosts file after mounting.
> - Added numbered comments throughout `customize.sh` for better readability.
> - Added auto-refresh of AdAway after hosts file is mounted.
> - Added system notification in `service.sh` after hosts is applied.
> - Added `FolkLite` (`mi.yuki.folk`) detection to `detect_root_all`.
> - Removed `display_soc_info` and `socs.json` dependency.
---

> [3.0.0]
>
> - Added `Donate` action in module.
> - Improved detection of root manager method users.
> - Some code has been `changed/fixed` and improved in `customize.sh`.
> - Remove `emoji` and folder Worker after mounting is complete.
> - Remove unnecessary code in `verify.sh`.
> - Cleaning Note changes to the module so that it is cleaner.
---