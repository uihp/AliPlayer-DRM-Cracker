# AliPlayer-DRM-Cracker
A decryptor of AliPlayer encrypted TS file

## 阿里云 Web 播放器 HLS (M3U8.TS) 视频解密脚本

### **本项目属于学习使用，不可用于侵权行为**

参考文章：

**吾爱破解** 搜索 aliplayer m3u8 了解 AliPlayer 的 DRM 技术细节

**Billsmiless**（重要指导）：

[吾爱破解](https://www.52pojie.cn/thread-1501397-1-1.html) 详细介绍了逆向全过程并附源码（文章已失效，此项目目前正是这篇文章的源码功能再现）

[吾爱破解](https://www.52pojie.cn/thread-1630846-1-1.html) 补档，介绍了 HLS TS 文件数据结构

### 技术细节
AliPlayer 的 .m3u8 文件的链接获取较为简单，复杂的是**加密过的.ts视频文件**

不同于通常的 HLS 加密（M3U8 内置 Key，通常是 AES-128-CBC）

阿里采用**手动（标准之外）**解密 TS 文件，这也是 M3U8 的 KEY 字段指定解密方法为‘MEATHOD’而不是‘METHOD‘的原因

**并且** 加密只加密 TS 文件的 PES 包，这导致不可以通过内置 KEY 来用播放器正常解码

**并且** 采用 AES 加密方法不是通常的 CBC 模式，而是 ECB 模式

### 使用方法

TS 文件可通过 .m3u8 正常地获取加密的 TS 文件

AES Key 通过浏览器抓包获得

在目前的版本，打开 index.html，选择 TS 文件并输入 Base64 编码的 AES Key 后即可解密

### TODOs
- 脚本解耦，脱离浏览器运行
- 。。。
