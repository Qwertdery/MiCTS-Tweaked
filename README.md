# MiCTS

[![Downloads](https://img.shields.io/github/downloads/parallelcc/MiCTS/total)](https://github.com/parallelcc/MiCTS/releases) [![Release](https://img.shields.io/github/v/release/parallelcc/MiCTS)](https://github.com/parallelcc/MiCTS/releases/latest)

[简体中文](/README.md)&nbsp;&nbsp;|&nbsp;&nbsp;English

Trigger Circle to Search on any Android 9–15 device

*This app only aims to trigger Circle to Search and cannot handle issues that may occur after triggering successfully*

## How to Use

1. Install the latest version of [Google](https://play.google.com/store/apps/details?id=com.google.android.googlequicksearchbox), enable auto-start, disable background restrictions, and set Google as the default assistant app


2. Install and launch MiCTS
   - If you're lucky, Circle to Search will be triggered directly without LSPosed when launching MiCTS
   - If nothing happened, then activate the module in LSPosed, enable `Device spoof for Google` in the [MiCTS settings](#how-to-enter-settings), and force restart Google
   - If it still doesn't work, try clearing Google’s data, then launch Google and force restart it


3. Set up the trigger method
   - Launching MiCTS will trigger, so you can use other apps like Quick Ball, Xposed Edge, ShortX, etc., set launching MiCTS as the action to customize the trigger method
   - MiCTS provides a trigger tile, so you can add it to the Quick Settings panel and trigger by clicking it
   - For Xiaomi devices, MiCTS has built-in support for `Trigger by long press gesture handle` and `Trigger by long press home button`, which can be enabled in the MiCTS settings (need to activate the module and restart the phone after installing MiCTS)

## Settings

### How to enter Settings
- Long press the MiCTS app icon to show the Settings option, then click to enter
- From the Modules page in LSPosed, click MiCTS, then click the settings icon to enter
- Long press the Quick Settings panel tile to enter

### App Settings
- Default trigger delay: The delay when triggering by launching MiCTS
- Tile trigger delay: The delay when triggering by the Quick Settings panel tile

### Module Settings
Need to activate the module in LSPosed
- System trigger service: The system service used by triggering. Only the services supported will be shown. Need to add System Framework to the scope in LSPosed
   - VIS: Supports on Android 9-15. Need to set Google as the default assistant app and the screen edge will flash when triggering. If the module is not activated, only this service will be used
   - CSHelper: Supports on Android 14 QPR3 and above. Don’t need to set Google as the default assistant app and the screen edge will not flash when triggering


- Trigger by long press gesture handle: Only supports on Xiaomi devices. Need to add System Launcher/POCO Launcher to the scope in LSPosed


- Trigger by long press home button: Only supports on Xiaomi devices. Need to add System Framework to the scope in LSPosed


- Device spoof for Google: Need to add Google to the scope in LSPosed
   - Manufacturer: Modify the `ro.product.manufacturer` value that Google reads
   - Brand: Modify the `ro.product.brand` value that Google reads
   - Model: Modify the `ro.product.model` value that Google reads
   - Device: Modify the `ro.product.device` value that Google reads

## FAQ

### Does it require root?

As mentioned in step 2 of [How to Use](#How-to-Use), it's possible to trigger without root, depending on your device's configuration, for example, many Xiaomi devices can trigger directly without root, so you can give it a try. However, if it doesn't work, it's likely because your device didn't pass Google's device check. In this case, you'll need device spoof, which is what the LSPosed module provides

### Prompt "Trigger failed!"

Most likely because Google is not set as the default assistant, check it

### Google assistant appears instead of Circle to Search

Ensure that Google is the latest version

### Sometimes, the screen edge flashed but did not trigger successfully, the interface appeared after opening Google

This is likely due to the tombstone mechanism. Check if your device has related settings and add Google to the whitelist, such as selecting "No restrictions" in battery saver

This issue should not occur when the `System trigger service` is set to `CSHelper` in the Module Settings

## Star History

<a href="https://star-history.com/#parallelcc/micts&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=parallelcc/micts&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=parallelcc/micts&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=parallelcc/micts&type=Date" />
 </picture>
</a>
