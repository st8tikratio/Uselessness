# Motherfucking Android Notes

---

## Relevant GrapheneOS Links
- [User Guide](https://grapheneos.org/usage#sandboxed-google-play-installation)
- [Removing and updating apps later](https://discuss.grapheneos.org/d/5302-removing-play-services-after-having-used-them)
- [Financial Institutions](https://privsec.dev/posts/android/banking-applications-compatibility-with-grapheneos/)

---

## Cross-Verified App APKs Using AppVerifier and Android Tools
- [Tutanota Github](https://github.com/tutao/tutanota)
  - [APK - FDroid](https://f-droid.org/en/packages/de.tutao.tutanota/)
  - [APK](https://github.com/tutao/tutanota/releases/tag/tutanota-android-release-253.241126.2)
- [Cake Wallet APK](https://github.com/cake-tech/cake_wallet/releases)
  - [Cupcake Wallet](https://github.com/cake-tech/cake_wallet/releases)
  - [Monero Wallet](https://github.com/cake-tech/cake_wallet/releases)
- [KOReader]()
- [BitWarden APK](https://github.com/bitwarden/mobile/releases/download/v2024.10.0/com.x8bit.bitwarden.apk)
- [Brave APK](https://github.com/brave/brave-browser/releases)
- [Transistor](https://codeberg.org/y20k/transistor/src/tag/v4.2.2)
- [Karbon - XEEditor](https://github.com/Xed-Editor/Xed-Editor/releases/tag/v2.9.0)
- [Thunderbird](https://github.com/thunderbird/thunderbird-android/releases/tag/THUNDERBIRD_8_2)
- [K-9 Mail](https://github.com/thunderbird/thunderbird-android/releases/tag/K9MAIL_8_2)
- [Organic Maps](https://github.com/organicmaps/organicmaps/releases/tag/2024.11.27-12-android)
- [Markor](https://github.com/gsantner/markor/releases/tag/v2.13.1)
- [Symphony](https://github.com/gsantner/markor/releases/tag/v2.13.1)
- [QUIK SMS](https://github.com/octoshrimpy/quik/releases/tag/v4.0.7-testing)
- [AF Weather](https://github.com/Gitsaibot/AF-Weather-Widget/releases/tag/v2.8)
- [Osmand](https://osmand.net/releases/)
- [NetGuard](https://github.com/M66B/NetGuard/releases/tag/2.330)
- [Material Notes](https://github.com/maelchiotti/LocalMaterialNotes/releases/tag/v1.9.1)
- [Element](https://github.com/element-hq/element-android/releases/tag/v1.6.24)
- Currencies -> No APK, must build or get from F-Droid
- [Orbot](https://github.com/guardianproject/orbot/releases/tag/17.2.1-RC-1-tor-0.4.8.7)
- [Firefox Focus](https://archive.mozilla.org/pub/focus/releases/133.0/android/focus-133.0-android-arm64-v8a/)
- [Tor Browser](https://www.torproject.org/download/#android)
- OnionShare - https://docs.onionshare.org/ -> No APK
- Save - https://www.open-archive.org/save -> No APK
- [Open Camera](https://sourceforge.net/projects/opencamera/)
- [OSS Weather](https://github.com/Akylas/oss-weather/releases/tag/android%2Fgithub%2F2.9.3%2F146)
- [Stratum Auth](https://github.com/stratumauth/app/releases/tag/v1.1.0)
- [QuillPad](https://github.com/quillpad/quillpad/releases/tag/v1.4.20)
- [Bunny Media Editor](https://artectrex.eu/bunny-media-editor/)
  - [APK](https://gitlab.shinice.net/pixeldroid/bunny/-/releases)
- [yetCalc](https://github.com/Yet-Zio/yetCalc/releases/tag/2.0.4)
- [LabNex](https://github.com/labnex/LabNex/releases/tag/2.0.0)
- [Mastadon](https://github.com/mastodon/mastodon-android/releases/tag/v2.9.3)
- [Wireguard](https://download.wireguard.com/android-client/)
- [Fair Email](https://github.com/M66B/FairEmail/releases/tag/1.2251)
- [Session](https://github.com/session-foundation/session-android/releases/tag/1.20.7)
  - [formerly Loki Net - alt download](https://getsession.org/download)
  - [part of Oxen.IO now](https://oxen.io/session-lokinet)
- [Exif Eraser](https://github.com/Tommy-Geenexus/exif-eraser/releases/tag/v6.3.0)
- [Breezy Weather](https://github.com/breezy-weather/breezy-weather/releases/tag/v5.3.1)
- [KeePass2Android](https://github.com/PhilippC/keepass2android/releases/tag/v1.11-r0)
  - [Cern recommendation](https://devices.docs.cern.ch/pss/keepass2android/)
- [KeePassDX Libre](https://github.com/Kunzisoft/KeePassDX/releases/tag/4.1.1)
- [OpenKeychain](https://www.openkeychain.org/)
  - [APK](https://f-droid.org/packages/org.sufficientlysecure.keychain/)
- []()
- []()
- 

---

## Verifying APK Signature Hashes
### Method #1
##### [Source](https://stackoverflow.com/questions/7104624/how-do-i-verify-that-an-android-apk-is-signed-with-a-release-certificate)
#### If Java Is Installed
Use `keytool`
```
keytool -printcert -jarfile [file.apk]
```

### Method #2
##### [Source](https://android.stackexchange.com/questions/9312/how-can-i-verify-the-authenticity-of-an-apk-file-i-downloaded)
#### Getting and executing apksigner
Apksigner is a Java tool and Google provides for start-up a batch file apksigner.bat(Windows) respectively a shell script apksigner.sh (Linux, MacOS).

As mentioned before it is included in each build-tools version of Android SDK. But it is not placed in PATH so you can not simply open a command-prompt or terminal and execute apksigner, instead you have to manually provide the full path to apksigner.bat/apksigner.sh.

If you don't want to install the whole Android SDK (with or without Android Studio) you can directly download build tools and extract and execute apksigner. Links to the all build-tools are provided on this website (the provided links go to the original Google download locations).

##### I prefer apksigner from build-tools v30:
- [build-tools 30.0.1 Linux](https://dl.google.com/android/repository/build-tools_r30.0.1-linux.zip)
- [build-tools 30.0.1 MacOS](https://dl.google.com/android/repository/build-tools_r30.0.1-macosx.zip)
- [build-tools 30.0.1 Windows](https://dl.google.com/android/repository/build-tools_r30.0.1-windows.zip)

- You only need the file lib/apksigner.jar from the archive. Extract it and open a shell in the folder. Then execute java -jar apksigner.jar. To execute you need Java 9 or higher (best Java 11 or 17).

##### Using this direct approach the command to execute apksigner is

```
java -jar apksigner.jar verify --verbose --print-certs "Signal-website-universal-release-4.49.13.apk"
```
##### Or if you use full path names - replace the <..> sections with the appropriate path that works on your OS:

```
<path to java 9+>/java -jar <path to apksigner>/apksigner.jar verify --verbose --p
```

---
