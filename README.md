# MSI-B360M-MORTAR-Firepro-W5100-OpenCore

## 因更换rx550显卡，此项目今日起不再维护。22.5.19


> 此项目efi基于：https://github.com/SuperNG6/MSI-B360-Big-Sur-EFI  AMD GPU+IGPU修改适配 AMD Firepro W5100 


# 硬件介绍
| 类型 | 品牌 | 型号 |
|-----|-----|-----|
| 处理器 | 英特尔| i5-8500 
| 主板 | 微星 | B360M MORTAR |
| 核显 | / | UHD630 |
| 显卡 | AMD | Firepro W5100 4G |
| 硬盘 | 三星 | 970evo 250G |
| 网卡 | 博通 | BCM94360CS2 |
| 显示器 |明基 | BenQ EW3270U 4k60hz 	|
| OS |	macOS Monterey 12.3.1 |
| OpenCorePkg | 0.8.0 |



![](Images/关于本机.png)



# BIOS设置

确认主板使用的 BIOS 版本为`7B23v16` ，之后拔掉电源线并扣掉主板电池等十分钟后进行下面bios设置：

`SETTINGS`->`高级`->`内建显示配置`->`设置第一显卡 [PEG]`

`SETTINGS`->`高级`->`内建显示配置`->`集显共享内存 [64M]`

`SETTINGS`->`高级`->`内建显示配置`->`集成显卡多显示器 [允许]`



# 使用方法
> 保留啰嗦模式以便排查问题。

下载整包后，使用 Clover Configurator 选择iMac19,1机型生成新的`三码` + `ROM`。
如果用 ProperTree 打开`/EFI/OC/config.plist`文件，填入到 `PlatformInfo` -> `Generic` 位置中

开机黑屏等待休眠后唤醒正常的，可以试试在`NVRAM`-`Add`-`7C436110-AB2A-4BBB-A880-FE41995C9F82`-`boot-args`添加`-igfxblr`参数能不能解决

开机跑码如果在
```
‹Notice>: Doing boot task: cache-start
‹Notice>: Doing boot task: bootroot 
```
卡半分钟左右，将config.plist中`SetApfsTrimTimeout`的值`-1`更改为`0`即可解决。




# 截图
![概览](Images/概览.png)

![显卡信息](Images/显卡信息.png)

![核显调用](Images/核显调用.png)

![硬解](Images/硬解.png)


# 其他啥的后面有空继续补充。