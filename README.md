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

## How to Build with new SDK sdk_tg5050_linux_v1.0.0.tgz
* sdk_tg5050_linux_v1.0.0.tgz, under Xubuntu 25.04
* https://github.com/trimui/toolchain_sdk_smartpro_s/releases/tag/20251208
* see new_sdk_tg5050/Makefile  
CC = /home/wmt/sdk_tg5050_linux_v1.0.0/host/bin/aarch64-none-linux-gnu-g++   
LD = /home/wmt/sdk_tg5050_linux_v1.0.0/host/bin/aarch64-none-linux-gnu-g++ -o  
SYSROOT?=/home/wmt/sdk_tg5050_linux_v1.0.0/host/aarch64-buildroot-linux-gnu/sysroot  
* cd new_sdk_tg5050; make MIYOO=1 clean; make MIYOO=1

## How to Build with old SDK SDK_usr_tg5040_a133p.tgz and aarch64-linux-gnu-7.5.0-linaro.tgz  
* SDK_usr_tg5040_a133p.tgz and  aarch64-linux-gnu-7.5.0-linaro.tgz, under Xubuntu 20.04  
* Modify Makefile, where are gcc and stage_files  
* see aarch64-linux-gnu-7.5.0-linaro.tgz:   
CC = /home/wmt/work_trimui/aarch64-linux-gnu-7.5.0-linaro/bin/aarch64-linux-gnu-g++   
LD = /home/wmt/work_trimui/aarch64-linux-gnu-7.5.0-linaro/bin/aarch64-linux-gnu-g++ -o  
* see SDK_usr_tg5040_a133p.tgz:  
SYSROOT?=/home/wmt/work_trimui  
* https://github.com/trimui/toolchain_sdk_smartpro/releases/tag/20231018  
* https://github.com/trimui/toolchain_sdk_smartpro/releases/download/20231018/aarch64-linux-gnu-7.5.0-linaro.tgz  
* https://github.com/trimui/toolchain_sdk_smartpro/releases/download/20231018/SDK_usr_tg5040_a133p.tgz  
* cd old_sdk_tg5040; make MIYOO=1 clean; make MIYOO=1

## How to debug by bottom USB-C (not the top one) adb connection (not good method, but available and show log)         
* adb push onscripter /mnt/SDCARD/Apps/ons/  
* adb shell  
$ cd /mnt/SDCARD/Apps/ons/ && LD_LIBRARY_PATH=/usr/trimui/lib ./onscripter  

## TODO, remove -ljpeg and -lpng deps, is it necessary ???    
