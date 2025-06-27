# third_party_sonic

## Usage Scenarios

Sonic is an algorithm for audio speed change, enabling basic audio processing such as changing speed without altering pitch, changing pitch without altering speed, and simultaneously changing speed and pitch. It is particularly optimized for speed changes of more than 2x. Sonic includes implementations in both C and Java, with main.c and main.java serving as simple usage examples for each.

## Directory Structure

third_party_sonic/
├── debian/
├── doc/
├── samples/
├── BUILD.gn
├── bundle.json
├── COPYING
├── LICENSE
├── Main.java
├── main.c
├── Main.java
├── Makefile
├── mkorig
├── OAT.xml
├── README
├── README_en.md
├── README_ch.md
├── README.OpenSource
├── sonic.1
├── sonic.c
├── sonic.h
├── Sonic.java
├── wave.c
└── wave.h


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