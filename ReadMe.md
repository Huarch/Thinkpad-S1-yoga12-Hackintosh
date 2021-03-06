# Thinkpad S1 yoga 12 Hackintosh

## Update
修复接力功能。EFI仍使用itlwm配置Wi-Fi。若要使用接力，需使用Hackintool安装airportitlwm，放入Library/Extensions文件夹，并重建缓存，同时需删除EFI中itlwm文件，即可使用系统Wi-Fi功能。

修复睡眠功能。需使用Hackintool电源页，使用“扳手”按钮修复标记红色条目，即可正常睡眠。

## 设备信息

| 类型      | 型号                                |
| --------- | ----------------------------------- |
| CPU       | i5--5300u                           |
| GPU       | hd5500                              |
| Wi-Fi     | Intel(R) Dual Band Wireless AC 7265 |
| Blueteeth | 原装Intel蓝牙（型号不重要）         |
| 声卡      | Conexant CX20751                    |
| ROM       | 8G                                  |
| RAN       | 256G                                |

## Hackintosh说明

| 类型       | 状态                                       |
| ---------- | ------------------------------------------ |
| macOS版本  | Catalina 10.15.7                           |
| 显示       | 正常                                       |
| 声音       | 正常                                       |
| 蓝牙       | 正常（部分设备连接存在问题，具体见下文1*） |
| Wi-Fi      | 正常（使用见下文2*）                       |
| 有线网卡   | 未安装（具体见下文3*）                     |
| HDMI       | 正常                                       |
| 触摸板     | 部分正常（三金刚键异常）                   |
| 小红点     | 失效                                       |
| 键盘       | 部分正常（功能快捷键大部分失效）               |
| 屏幕背光   | 正常                                       |
| 电池       | 正常                                       |
| 摄像头     | 正常                                       |
| 麦克风     | 正常                                       |
| 隔空投送   | 正常                                       |
| 电磁笔     | 正常                                       |
| 随航、接力 | 部分正常（随航不可用）                                       |
| 触摸屏     | 失效                                       |
| 睡眠       | 正常                                       |

1. 罗技k380正常连接，Airpods Pro正常连接，MX Key连接失败，M590连接失败。后两者支持Unifying连接，使用后连接正常。Airpods Pro播放音频时频繁卡顿，似乎是与Wi-Fi冲突问题，关闭Wi-Fi有大幅改善。此外可以尝试打开终端分别执行3条命令：

   `defaults write com.apple.BluetoothAudioAgent "Apple Bitpool Min (editable)" 35`

   `defaults write com.apple.BluetoothAudioAgent "Apple Initial Bitpool Min (editable)" 53`

   `defaults write com.apple.BluetoothAudioAgent "Apple Initial Bitpool (editable)" 35`

   命令旨在提高蓝牙传输比特率。若仍出现卡顿，逐次提高后三条命令中的数值。*注意：比特率不要一次性调太高，不是越高越好的。*

2. Wi-Fi必须使用`itlwm.kext`，配合`HeliPort`软件才能正常使用。

3. 有线需转换器，从来不用。

## 使用说明

1. 使用黑果小兵网站Catalina 10.15.7 双引导镜像制作USB启动
2. 使用磁盘工具，删除所有EFI文件，使用本EFI文件进行替换
3. 安装与设置
4. 进入系统后，使用`Hackintool`或`Hackintool`注入三码（配置中已清空三码）
5. 安装`HeliPort`，设置Wi-Fi
6. 登陆账号，拥有9成白苹果的体验

## 其他事项

非本机型请谨慎使用。已关闭啰嗦模式。Clover版本为5126，支持Big Sur升级。

