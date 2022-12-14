---
layout: default
title: 数字模式指南
nav_order: 53
---

**空中公园® 数字模式指南**

![](/assets/images/pota-256x256.png)

版权所有 2022

原作者：W8MSC


**目录**
1. 目录
{:toc}

# 使用数字模式激活空中公园

本指南包含使用数字模式激活空中公园的一些最佳实践和提示。


# 在开始之前

请记住使用数字模式激活空中公园增加了你的便携电台的复杂性。

这里有些进行激活空中公园前的准备工作的一般建议：

* 更新你的计算机软件并使它们保持最新状态。
* 使用带有PPS（每秒脉冲）信号的GPS dongle设备用来获取当前准确的时间。 当使用WSJT-X时，这点特别重要。 [BktTimeSync](https://www.maniaradio.it/en/bkttimesync.html) 软件能够从GPS卫星信号中读取当前准确时间，并同步你的计算机时间。
* 在阴影中操作你电脑或者使用防眩目屏幕来降低你的笔记本电脑或屏幕的眩目程度。
* 在开始新的激活前，存档并清空你的旧通联日志。
* [JTSync](http://www.dxshell.com/jtsync.html) 软件是一个与WSJT-X配套使用的程序，用来设置你电脑的时间，以使其和空中的另一个电台同步。


# WSJT-X

## 在WSJT-X中创建一个新日志

前往公园之前，在 WSJT-X 中设置一个新日志可以帮助简化你的激活过程。 通过重命名现有日志文件，WSJT-X将不再将任何已记录的QSO视为"之前已工作"状态。 这将使你能够看到追逐者或其他公园是否已经在当前 UTC 日的日志中。

你可以通过重命名日志文件来记录每个公园和日期的日志。

* 如果WSJT-X正在运行，请关闭
* 将已有的 wsjtx_log.adif 重命名为一个归档名称。 文件名应该遵守每个空中公园日志建议的命名规则。
* 重新启动 WSJT-X。 一旦你开始记录，软件将创建一个新的 wsjtx_log.adif 文件。


# 使用 WSJTX-X 配置来管理每个公园的设置

如果你在多个位置之间旅行，你可以使用 WSJT-X 配置来设置公园或位置。 当你有一个正在工作的电台控制之类的配置项，你可以将默认配置项复制到公园的特定配置中。

* 配置 > 默认> 克隆
* 将新克隆配置重命名为你的公园名称或另一个短名。
* 配置 > (新名称) > 切换到
* 设置 > 常规 > 我的呼号(如果与你的默认呼号不同，则设置为正确的呼号)
* 设置 > 常规 > 我的网格(设置为正确的网格）
* 设置 > 自定义文字：添加一个新文字，例如：CQ POTA BH4FCY PM01。 这将在标准信息的 "发射 5" 字段中可用。

根据你的呼号长度，你可能没有足够的字符来发送网格信息。 如果是，则可以省略网格信息。

# 记录你的QSOs

当你开始记录追逐者时，你可以使用“记录通联”窗口的备注栏来存储你的公园信息。 选择“Retain”复选框，这样你就不必为每个QSO重新输入此信息。

# 其他数码模式

别忘了，还有除了FT8以外的其他数字模式可以使用。 只要每个QSO模式都是独一无二的，和同一个追逐者的通联都可以算作独立的 QSO。 例如，激活空中公园可以在在同一个 UTC 日，在同一波段多次和同一个猎人通联，但使用不同的数字模式， 例如：PSK31、RTTY、FT8、FT4 等模式。

## 意见反馈

如果你对此文档有任何建议 [请发送电子邮件至 help@parksonthair.com。](mailto:help@parksonthair.com)

## 致谢

感谢参与该程序的所有激活者和追逐者。
