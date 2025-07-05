# third_party_sonic

## Usage Scenarios

Sonic is an algorithm for audio speed change, enabling basic audio processing such as changing speed without altering pitch, changing pitch without altering speed, and simultaneously changing speed and pitch. It is particularly optimized for speed changes of more than 2x. Sonic includes implementations in both C and Java, with main.c and main.java serving as simple usage examples for each.

## Directory Structure

In the OpenHarmony system, sonic inheritance is implemented within the audio service. Through the service, applications can call relevant interfaces to achieve audio speed change playback, The related interfaces are setSpeed and getSpeed. For detailed instructions, please refer to the link: https://gitee.com/openharmony/docs/blob/master/zh-cn/application-dev/reference/apis-audio-kit/js-apis-audio.md

```
third_party_sonic/
├── debian/             # Debian system source code
├── samples/            # Audio samples
├── Main.java           # Java usage example
├── main.c              # C usage example
├── sonic.c             # C audio speed change source code
├── sonic.h             # C audio speed change source code
├── Sonic.java          # Java audio speed change source code
├── wave.c              # C audio speed change source code
├── wave.h              # C audio speed change source code
├── BUILD.gn            # HarmonyOS build script
├── bundle.json         # HarmonyOS build script
├── Makefile            # Compilation script
├── README_zh.md        # Installation and usage instructions
├── README_en.md        # Installation and usage instructions
├── COPYING             # License declaration
└── LICENSE             # License declaration
```


## OpenHarmony Adaptation for Sonic
Sonic is introduced into the thirdparty directory of OpenHarmony and is compiled using the dependency components in OpenHarmony.

1. Main Code Download

```
repo init -u https://gitee.com/openharmony/manifest.git -b master --no-repo-verify
repo sync -c
repo forall -c 'git lfs pull'
```

1. Add Dependency in the Used Module

```
deps = [ "//third_party/sonic:sonic" ]
```

3. Preprocessing

```
./build/prebuilts_download.sh
```
1. Compilation

```
./build.sh --product-name rk3568 --ccache
```

## License

This project uses the Apache2.0 License. Please refer to the LICENSE fiel for more details.