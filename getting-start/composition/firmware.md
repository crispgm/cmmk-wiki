---
description: Firmware
---

# 固件

固件本身是键盘底层功能能够正常使用所需要的嵌入式程序。

对于用户来说，我们只需要用固件相关的配套软件或者网站配置键位。

## QMK

QMK 是一个客制化固件生态，基于 TMK 固件，是客制化圈的事实标准。

QMK 生态包括 QMK Firmware（固件）、QMK Toolbox（固件烧录工具）、QMK Configurator（在线配置工具）。QMK Firmware 入门成本比较高，对于键盘开发者来说才需要接触。

对于一般玩家，我们会主要跟 QMK Toolbox 和 QMK Configurator 打交道。

{% embed url="https://config.qmk.fm/" %}

## VIA

VIA 是基于 QMK 固件开发的改键软件，用户只需要刷一次支持 VIA 的 QMK 固件，就可以获得实时改键的能力，极大的减少了改键成本。因此广受欢迎，成为了新套件的 PCB 标准配置。

由于是 Olivia 设计的，因此软件界面配色同 GMK Olivia。

![VIA](../../.gitbook/assets/image%20%2814%29.png)

相关链接：

* 官网
  *  [https://caniusevia.com/](https://caniusevia.com/)
* 所支持的键盘固件下载
  * [https://caniusevia.com/docs/download\_firmware](https://caniusevia.com/docs/download_firmware)

ps：部分键盘支持 VIA，但作者没有把 hex 文件提交给 VIA 官方（比如：Vespa.CR），这种情况请向作者索取 hex 文件和配列文件（JSON 格式）。刷入 hex 后，打开 VIA，然后手动导入配列 JSON 文件即可使用。个人不是很推荐这样，流程不太正规的同时，也增加了用户的使用成本。

