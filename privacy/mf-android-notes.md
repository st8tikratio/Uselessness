# Motherfucking Android Notes


## Verifying APK Signature Hashes
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
