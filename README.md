# FreeAgent SmartOS Overlay.

# NO LONGER USED #


## How to use

This repo is designed to be checked out into and existing smartos-live checkout under the overlays directory.

You then need to edit the configure config file to place this overlay first in the list of overlays.

Alternatively copy the sample file freeagent.configure.smartos to smartos-live/configure.smartos which is already configured.

## How to modify

Make your changes and ensure that you update the manifest file with the fiels you want to end up in the platform build. The format
of the manifest should be self evident.

## Changes from Vanilla

* kernel/drv/sd.conf

We disable power management of all SD devices. Running with power managment enabled has caused issues with Dell's firmware previously

* smartdc/lib/smartos_prompt_config.sh

We add a hook that looks for an executable file served from PXE at /system/boot/config_script, and if it exists we execute it. This allows hooking a script in to the configuration of a new hyp by injecting it via PXE.

* etc/issue

Addition of yak



