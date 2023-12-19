# third_party_sonic

## 使用场景

Sonic是一个用于音频变速的算法，可以实现音频变速不变调、变调不变速、同时变速变调等基本音频处理，尤其对2倍以上的变速进行了优化。Sonic包含了C和Java两种实现，main.c和main.java分别为两者的简单使用示例。

## 目录结构

third_party_sonic/
├── debian/
├── doc/
├── samples/
├── COPYING
├── Main.java
├── Makefile
├── README
├── Sonic.java
├── main.c
├── mkorig
├── sonic.1
├── sonic.c
├── sonic.h
├── wave.c
└── wave.h


## OpenHarmony对于sonic的适配
sonic引入openharmony的thirdparty目录下， 使用OpenHarmony中依赖部件的方式进行编译。

1. 主干代码下载

```
repo init -u https://gitee.com/openharmony/manifest.git -b master --no-repo-verify
repo sync -c
repo forall -c 'git lfs pull'
```

2. 在使用的模块进行依赖

```
deps = [ "//third_party/sonic:sonic" ]
```

3. 预处理

```
./build/prebuilts_download.sh
```
4. 编译

```
./build.sh --product-name rk3568 --ccache
```

## 许可证

本项目使用Apache 2.0许可证。请参阅LICENSE文件以获取更多详细信息。