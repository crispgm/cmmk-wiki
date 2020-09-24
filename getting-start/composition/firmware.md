---
description: Firmware
---

# 固件/改键位

固件本身是键盘底层功能能够正常使用所需要的嵌入式程序。

对于用户来说，我们只需要用固件相关的配套软件或者网站配置键位。

## QMK

QMK 是一个客制化固件生态，基于 TMK 固件，是客制化圈的事实标准。

QMK 生态包括 QMK Firmware（固件）、QMK Toolbox（固件烧录工具）、QMK Configurator（在线配置工具，部分情况下会用 QMKeyboard.cn）。QMK Firmware 入门成本比较高，对于键盘开发者来说才需要接触。

## 键值

QMK 支持的键置非常多，分为基础、Quantum、键盘设置、多媒体/鼠标。

### 基础

基础键值就是我们平时最常用最熟悉的那些按键，包括字母、数字、功能键、修饰键等，涵盖所有 ANSI/ISO/JIS 标准键值。

### Quantum

Quantum 是量子，暂没想好怎么翻译，直译又比较奇怪。

Quantum 类都是一些高级玩法。首先是控制 PCB 进入刷机模式就属于 Quantum。其次是最常用的切层（fn），当然 QMK 支持的切层姿势有很多。

还有一类比较容易忽视但很好用的功能，就是长短触输出不同键值。比如：`LSFT(KC)` 是单点一下输出配置的基础键值 kc，和别的键组合按就还是正常 shift 的效果。

最后就是一些特殊键在 shift 时有特别的搭配，比如 ESC/波浪，平时 ESC，和 shift 组合后变成波浪号。这类按键在60%以下的小配列键盘上非常实用。

### 键盘配置

用于配置键盘功能的按键，主要是类似 DIP 的配置类功能，还有灯光控制（RGB 和底灯）。

### 应用/多媒体/鼠标

应用主要是Windows 系统和 macOS 系统定义的一些跟操作系统相关的功能键。Windows 上打开我的电脑、邮件、计算器、控制浏览器等，而 macOS 上可以调节亮度等。

多媒体类键比较实用，用于调节音量和控制多媒体播放器。

鼠标类就是类似 Windows 中的鼠标键功能，通过键盘来操作鼠标。

QMK 支持的全部键值请参考：

{% embed url="https://docs.qmk.fm/\#/keycodes" %}

## 配置程序

### QMK Configurator

对于一般玩家，我们会主要跟 QMK Toolbox 和 QMK Configurator 打交道。这些软件操作不是很复杂，并且作者们一般也会提供教程，这里我就不再单独介绍使用方法。

QMK Configurator 是 QMK 官方推出的在线键位配置和触发测试工具。

{% embed url="https://config.qmk.fm/" %}

同时，部分作者固件配置工具使用的是豆仔的 QMKeyboard.cn，作用等同于 QMK Configurator。这块我不清楚历史原因，但两者功能是不同的。

{% embed url="http://qmkeyboard.cn/" %}

对于基本的键位配置和编译生成 hex 文件是一致的。

两者主要区别是：

* QMK Configurator 支持多语言，但目前没有中文（本人已经提交 Merge Request 暂无得到通过）；QMKeyboard.cn 只支持中文
* QMK Configurator 预置了大量国外键盘键位；QMKeyboard.cn 只有少量国内套件
* QMKeyboard.cn 支持阵列、针脚、宏录制、自定义程式等开发者功能或高级功能
* QMK Configurator 自带按键触发测试界面

整体结论就是，两者都是配置 QMK 固件的在线配置器，生成的目标文件都是符合 QMK 要求的。但中间的配置文件（JSON 格式）并不兼容。

默认情况下，对于常见的套件尤其是国外的基本要使用 QMK Configurator，部分国内套件使用 QMKeyboard.cn。

### VIA

VIA 是基于 QMK 固件开发的改键软件，用户只需要刷一次支持 VIA 的 QMK 固件，就可以获得实时改键的能力，极大的减少了改键成本。因此广受欢迎，成为了新套件的 PCB 标准配置。

VIA 带有大部分 QMK 的核心功能，但不支持非基础键值（比如：`LSFT(kc)`），原因不明。但 VIA 又支持 QMK Configurator 没有的宏定义功能。

由于是 Olivia 设计的，因此软件界面配色同 GMK Olivia。

![VIA](../../.gitbook/assets/image%20%2814%29.png)

相关链接：

* 官网
  *  [https://caniusevia.com/](https://caniusevia.com/)
* 所支持的键盘固件下载
  * [https://caniusevia.com/docs/download\_firmware](https://caniusevia.com/docs/download_firmware)

> ps：部分键盘支持 VIA，但作者没有把 hex 文件提交给 VIA 官方（比如：Vespa.CR），这种情况请向作者索取 hex 文件和配列文件（JSON 格式）。刷入 hex 后，打开 VIA，然后手动导入配列 JSON 文件即可使用。个人不是很推荐这样，流程不太正规的同时，也增加了用户的使用成本。

