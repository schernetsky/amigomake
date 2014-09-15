AmigoMake
=========

##Install:
```bash
# Makes soft link to amigomake in /usr/bin
sudo ./install.sh
```

##Usage:
```bash
amigomake [flags] [action] {android,ios,x86} [platform-flags]
```

###Supported Platforms: 

android, ios, x86

###General Flags:
```
-h, --help         show this help message and exit
-a , --arch        Specify the target architecture (armv7 by default)
-f , --file        Specify AmigoMakefile path
-r , --root        Specify dir for external dependency soures
-d, --debug        Compile non-optimized with debug flags
--all              apply action to everything including dependencies
-v, --verbose      verbose mode
```

###Actions:

Pass actions to be interpreted by the make file (clean, test, etc...)

The default action is: **build**  

###Platform Flags:
####X86:
None
####Android:
```
-n , --ndk           Specify path to the Android NDK(Required)
-v , --sdk-version   Specify Android SDK version to use(Required)
```
####iOS:
```
-v , --sdk-version   Specify iOS SDK version to use(Required)
--sim                Build for simulator
```
##Examples:

###IOS:
```bash
# Clean non sim build and external dependencies:
amigomake --all clean ios -v 7.0

# Build IOS7 without rebuilding external dependencies:
amigomake ios -v 7.0

# Build iOS7 simulator build and external dependencies:
amigomake --all ios -v 7.0 --sim
```

###Android:
```bash
# Build Android without rebuilding external dependencies for SDK version 14:
amigomake android -n ~/android-ndk/ -v 14
```

###x86:
```bash
# Build x86 without rebuilding external dependencies:
amigomake x86
```