# FREYA-STREAM-CASTER-SDK-FOR-ANDROID
FREYA STREAM CASTER SDK停止公开
</br>
</br>
:zap:FREYA STREAM CASTER SDK(ANDROID)是一款优秀的免费安卓RTMP推流SDK，适用于移动设备直播，JNI层全开源
</br>
</br>
拥有极强的性能与兼容性，是目前唯一支持全平台且JNI层开源的软编推流SDK。针对ARM、ARMV7-A、ARM64-V8A、X86、X86_64、MIPS、MIPS64全平台极致优化。让低端设备也可以流畅地进行高清推流
</br>
</br>
联动项目：[FREYA LIVE LIBRARY OPTIMIZER FOR ANDROID](https://github.com/jkkj93/FREYA-LIVE-LIBRARY-OPTIMIZER-FOR-ANDROID) -- RTMP直播推流常用库的编译简化/优化工具
</br>
</br>
一、系统要求
</br>
</br>
1.开发IDE：ANDROID STUDIO
</br>
</br>
2.编译JNI层需要在LINUX X64下进行，编译需使用NDK R13或以上版本
</br>
</br>
3.运行环境默认为ANDROID 4.0.3及以上系统
</br>
如有需要，可通过修改JNI层编译脚本中的相关变量，使本软件支持更低版本的ANDROID系统，详见“如何编译JNI层”部分
</br>
</br>
二、支持平台
</br>
</br>
FREYA STREAM CASTER SDK(ANDROID)是目前支持平台数最多的RTMP直播推流SDK
</br>
支持ARM、ARMV7-A、ARM64-V8A、X86、X86_64、MIPS、MIPS64全平台，并针对这些平台进行了极致优化，延迟仅为1-2S
</br>
</br>
三、软件功能
</br>
</br>
1.支持H264+AAC编码，FLV封装的RTMP、RTMPT、RTMPE、RTMPTE、RTMPS推流
</br>
</br>
2.无视频分辨率限制，在摄像头支持的情况下可推高分辨率视频流(如1080P)
</br>
</br>
3.JNI层极致优化，让低端设备也可以流畅地进行高清推流
</br>
</br>
4.H264视频编码支持BASELINE、MAIN、HIGH、HIGH10、HIGH422、HIGH444全部PROFILE
</br>
</br>
5.H264视频编码支持ULTRAFAST、SUPERFAST、VERYFAST、FASTER、FAST、MEDIUM、SLOW、SLOWER、VERYSLOW、PLACEBO共10种速度模式
</br>
</br>
6.AAC音频编码支持LC、HE、HEv2全部PROFILE
</br>
</br>
7.支持横屏、竖屏推流
</br>
</br>
8.支持前后摄像头实时切换
</br>
</br>
9.支持视频+音频、单视频、单音频三种推流模式
</br>
</br>
10.支持视频码率自定义
</br>
</br>
11.支持视频GOP容量自定义(GOP容量参数用于取得视频质量、压缩率、延迟的平衡。GOP容量值越小，视频质量越高、压缩率越小、延迟越小。GOP容量值越大，视频质量越低、压缩率越大、延迟越大)
</br>
</br>
12.支持音频码率自定义
</br>
</br>
13.支持音频采样率自定义
</br>
</br>
14.支持音频单声道、立体声自定义
</br>
</br>
15.支持开关闪光灯
</br>
</br>
四、优化方案
</br>
</br>
FREYA STREAM CASTER SDK(ANDROID)的核心功能使用了FFMPEG、X264、FDKAAC、LIBRTMP(RTMPDUMP)、POLARSSL、LIBYUV开源项目
</br>
为最大程度提升运行效率，对这些组件与JNI层的编码推流核心进行了大量编译优化。具体优化方案如下：
</br>
</br>
1.ARM优化方案：
</br>
FFMPEG： VFP+针对ARMV5TE的CPU调优
</br>
X264： VFP+多核多线程优化+针对ARMV5TE的CPU调优
</br>
FDKAAC： VFP+针对ARMV5TE的CPU调优
</br>
LIBRTMP： 针对ARMV5TE的CPU调优
</br>
POLARSSL： 汇编优化+针对ARMV5TE的CPU调优
</br>
LIBYUV： VFP+针对ARMV5TE的CPU调优
</br>
JNI： 针对ARMV5TE的CPU调优
</br>
</br>
2.ARMV7-A优化方案：
</br>
FFMPEG： NEON指令集+VFPV3+针对ARMV7-A的CPU调优
</br>
X264： NEON指令集+VFPV3+多核多线程优化+针对ARMV7-A的CPU调优
</br>
FDKAAC： NEON指令集+VFPV3+针对ARMV7-A的CPU调优
</br>
LIBRTMP： 针对ARMV7-A的CPU调优
</br>
POLARSSL： 汇编优化+针对ARMV7-A的CPU调优
</br>
LIBYUV： NEON指令集+VFPV3+针对ARMV7-A的CPU调优
</br>
JNI： 针对ARMV7-A的CPU调优
</br>
</br>
3.ARM64-V8A优化方案：
</br>
FFMPEG： NEON指令集+VFPV4+针对ARM64-V8A的CPU调优
</br>
X264： NEON指令集+VFPV4+多核多线程优化+针对ARM64-V8A的CPU调优
</br>
FDKAAC： NEON指令集+VFPV4+针对ARM64-V8A的CPU调优
</br>
LIBRTMP： 针对ARM64-V8A的CPU调优
</br>
POLARSSL： 汇编优化+针对ARM64-V8A的CPU调优
</br>
LIBYUV： NEON指令集+VFPV4+针对ARM64-V8A的CPU调优
</br>
JNI： 针对ARM64-V8A的CPU调优
</br>
</br>
4.X86/X86_64优化方案：
</br>
FFMPEG： SSSE3指令集+汇编优化+针对ATOM的CPU调优
</br>
X264： SSSE3指令集+汇编优化+多核多线程优化+针对ATOM的CPU调优
</br>
FDKAAC： 针对ATOM的CPU调优
</br>
LIBRTMP： 针对ATOM的CPU调优
</br>
POLARSSL： 汇编优化+SSE2指令集+针对ATOM的CPU调优
</br>
LIBYUV： SSSE3指令集+针对ATOM的CPU调优
</br>
JNI： 针对ATOM的CPU调优
</br>
</br>
5.MIPS优化方案：
</br>
FFMPEG： DSP R2+MSA+MIPS FPU+针对MIPS32R2的CPU调优
</br>
X264： DSP R2+MSA+MIPS FPU+多核多线程优化+针对MIPS32R2的CPU调优
</br>
FDKAAC： DSP R2+MSA+MIPS FPU+针对MIPS32R2的CPU调优
</br>
LIBRTMP： 针对MIPS32R2的CPU调优
</br>
POLARSSL： 汇编优化+针对MIPS32R2的CPU调优
</br>
LIBYUV： DSP R2+MIPS FPU+针对MIPS32R2的CPU调优
</br>
JNI： 针对MIPS32R2的CPU调优
</br>
</br>
6.MIPS64优化方案：
</br>
FFMPEG： DSP R2+MSA+MIPS FPU+针对MIPS64R6的CPU调优
</br>
X264： DSP R2+MSA+MIPS FPU+多核多线程优化+针对MIPS64R6的CPU调优
</br>
FDKAAC： DSP R2+MSA+MIPS FPU+针对MIPS64R6的CPU调优
</br>
LIBRTMP： 针对MIPS64R6的CPU调优
</br>
POLARSSL： 汇编优化+针对MIPS64R6的CPU调优
</br>
LIBYUV： MIPS FPU+针对MIPS64R6的CPU调优
</br>
JNI： 针对MIPS64R6的CPU调优
</br>
</br>
五、如何编译JNI层
</br>
</br>
1.jni_source目录中，包含JNI层源码、依赖的静态库文件与头文件、编译脚本，其中编译需要用到的脚本如下：
</br>
freya_sdk_compile_all.sh用于一键编译所有平台的库文件
</br>
freya_sdk_compile_arm.sh用于编译ARM库文件
</br>
freya_sdk_compile_armv7a.sh用于编译ARMV7-A库文件
</br>
freya_sdk_compile_arm64v8a.sh用于编译ARM64-V8A库文件
</br>
freya_sdk_compile_x86.sh用于编译X86库文件
</br>
freya_sdk_compile_x86_64.sh用于编译X86_64库文件
</br>
freya_sdk_compile_mips.sh用于编译MIPS库文件
</br>
freya_sdk_compile_mips64.sh用于编译MIPS64库文件
</br>
</br>
2.JNI层的编译需在LINUX X64系统下进行，推荐UBUNTU-12.04.5-DESKTOP-AMD64或以上版本
</br>
</br>
3.编译需使用NDK R13或以上版本
</br>
</br>
4.jni_source目录中的armeabi、armeabi-v7a、arm64-v8a、x86、x86_64、mips、mips64目录下，已经包含了编译JNI层所需的静态库文件与头文件
</br>
如需自己编译静态库并提取头文件，可使用我的另一个项目：[FREYA LIVE LIBRARY OPTIMIZER FOR ANDROID](https://github.com/jkkj93/FREYA-LIVE-LIBRARY-OPTIMIZER-FOR-ANDROID)
</br>
</br>
5.将jni_source目录中的文件复制到LINUX系统中
</br>
</br>
6.找到需要使用的编译脚本，并为脚本中需要配置的变量赋值
</br>
</br>
7.定义CURRENT_PATH变量，配置脚本所在的目录位置
</br>
</br>
8.定义NDKROOT_PATH变量，配置NDK所在的目录位置
</br>
</br>
9.定义PLATFORM_\*\_API变量(\*代表ARM、ARMV7A、ARM64V8A、X86、X86_64、MIPS、MIPS64)，配置对应各平台的ANDROID API级别，降低API级别可使本软件支持低版本的ANDROID系统
</br>
</br>
10.定义PLATFORM_NDK_TOOLCHAIN_VERSION变量，配置对应的TOOLCHAIN版本，默认为4.9，一般无需修改
</br>
</br>
11.配置完成后使用root用户运行对应各平台的编译脚本即可，编译完成后在freya_sdk_build_finished目录会生成相应的库文件
</br>
</br>
六、DEMO使用说明
</br>
</br>
1.如需测试功能，可去freya_apk目录中下载APK文件并安装
</br>
</br>
2.在界面中自定义H264编码PROFILE，H264编码模式，AAC编码PROFILE的格式："H264编码PROFILE代码:H264编码模式代码:AAC编码PROFILE代码"   例子1->"B:SUPERFAST:L"   例子2->"M:SUPERFAST:H"
</br>
</br>
3.H264编码PROFILE对应代码：baseline->B  main->M  high->H  high10->H10  high422->H422  high444->H444
</br>
</br>
4.H264编码模式代码：ULTRAFAST  SUPERFAST  VERYFAST  FASTER  FAST  MEDIUM  SLOW  SLOWER  VERYSLOW  PLACEBO 自左向右编码速度从快到慢，编码质量从低到高
</br>
</br>
5.AAC编码PROFILE对应代码：aac_lc->L  aac_he->H  aac_he_v2->H2
</br>
</br>
6.在网络正常且带宽足够的情况下，如果画面出现马赛克，或延迟较高，则可能是GOP容量值设置过高，降低GOP容量值即可明显改善
</br>
</br>
7.如果出现声画不同步现象，则说明CPU占用率过高，降低分辨率或选择更快的H264编码模式即可明显改善
</br>
</br>
8.音频采样率推荐使用兼容性最好的44100HZ，部分移动设备不支持44100HZ外的其他采样率
</br>
</br>
七、其他事项
</br>
</br>
1.由于包含了编译JNI层所需的静态库文件与头文件，因此项目较大，请耐心下载
</br>
</br>
2.本软件遵守GPL协议，旨在回馈开源社区，任何人均可免费使用本软件代码，进行软件开发或修改，同时本软件也不接受任何形式的捐赠
</br>
</br>
八、致谢与协议
</br>
</br>
本软件参考使用了以下软件的代码，向这些软件的作者致以最高的敬意：
</br>
</br>
1.[MOLiveStreamSDK](https://github.com/MOLiveStreamSDK/MOLiveStreamSDK)  (遵守[GPL协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE)，代码使用已获作者授权，再次感谢作者无私的共享精神)
</br>
2.[FFMPEG](https://github.com/FFmpeg/FFmpeg)  (遵守[GPL协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE))
</br>
3.[X264](http://www.videolan.org/developers/x264.html)  (遵守[GPL协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE))
</br>
4.[FDKAAC](https://github.com/mstorsjo/fdk-aac)  (遵守[FDK协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE_FDKAAC))
</br>
5.[LIBRTMP(RTMPDUMP)](http://rtmpdump.mplayerhq.hu)  (遵守[GPL协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE))
</br>
6.[POLARSSL](https://tls.mbed.org)  (遵守[GPL协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE))
</br>
7.[LIBYUV](https://code.google.com/p/libyuv)  (遵守[BSD协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE_LIBYUV)，第三方组件遵守[BSD协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE_LIBYUV_THIRD_PARTY))
</br>
8.[NavigationTabStrip](https://github.com/Devlight/NavigationTabStrip)  (遵守[MIT/Apache协议](https://github.com/jkkj93/FREYA-STREAM-CASTER-SDK-FOR-ANDROID/blob/master/LICENSE_NAVIGATIONTABSTRIP))
</br>
</br>
作者:jkkj93
