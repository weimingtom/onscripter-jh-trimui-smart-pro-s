# onscripter-jh-trimui-smart-pro-s
[WIP] My ONScripter-jh TRIMUI SMART PRO S port

## Original ONScripter-Jh readme
```
ONScripter是一个开源的NScripter脚本解释工具，主要由Ogapee开发维护
原版的Readme请查看Readme.old。

这是一个修改版的ONScripter源码，在GPLv2协议下发布，使用时请遵守。

修改目标：
	提供比原版ONScripter更好的性能，适当增加一些功能
	添加中文支持
	尽可能的兼容原版ONS脚本
	
进度

	SDL2分支提供各种改进并可在SDL2环境编译
	目前Windows、Android、iOS、Linux、Windows Phone平台均编译通过实测可用，其余平台未测试
```

## [WIP] How to Build  
* Modify Makefile, where are gcc and stage_files  
* see aarch64-linux-gnu-7.5.0-linaro.tgz:   
CC = /home/wmt/work_trimui/aarch64-linux-gnu-7.5.0-linaro/bin/aarch64-linux-gnu-g++   
LD = /home/wmt/work_trimui/aarch64-linux-gnu-7.5.0-linaro/bin/aarch64-linux-gnu-g++ -o  
* see SDK_usr_tg5040_a133p.tgz:  
SYSROOT?=/home/wmt/work_trimui  
* https://github.com/trimui/toolchain_sdk_smartpro/releases/tag/20231018  
* https://github.com/trimui/toolchain_sdk_smartpro/releases/download/20231018/aarch64-linux-gnu-7.5.0-linaro.tgz  
* https://github.com/trimui/toolchain_sdk_smartpro/releases/download/20231018/SDK_usr_tg5040_a133p.tgz  
* Run 'make clean && make MIYOO=1'  

## How to debug by bottom USB-C (not the top one) adb connection (not good method, but available and show log)         
* adb push onscripter /mnt/SDCARD/Apps/ons/  
* adb shell  
$ cd /mnt/SDCARD/Apps/ons/ && LD_LIBRARY_PATH=/usr/trimui/lib ./onscripter  
