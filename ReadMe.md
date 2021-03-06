##  Lenovo 小新 Air13IWL OpenCore `(xlivans)`
### 感谢 宪武 小兵 各位群友 大佬们 为此机型的辛苦付出

##### 如何安装系统请跳跃至小兵大佬教程 : https://github.com/daliansky/Lenovo-Air13-IWL

##### 配置说明 : https://github.com/xlivans/Air13IWL

##### 自用 OpenCore : https://github.com/xlivans/Air13IWL-OC

##### 自用 Clover : https://github.com/xlivans/Air13IWL-Clover

##### 微云 : https://share.weiyun.com/5yMO9jB

----

#### 2019-08-20

+ 移除操作系统更名,移除亮度快捷键更名及其相关补丁

+ 使用`SSDT-RMCFMap.aml`定制PS2键盘,屏蔽无用键,新增功能键

    + Fn+F4=上一曲
    + Fn+F7=下一曲
    + PrtSc=播放/暂停
+ 由于移除操作系统更名,使用`SSDT-TPXX.aml`驱动触摸板

#### 2019-08-13

+ 更新`宪武`大佬最新`GPRW`补丁,合并至`SSDT-Air13IWL.aml`

#### 2019-08-12

+ 更新`Acidanthera`所有引导,驱动,工具至Releases版

#### 2019-08-10

+ 更新OpenCore至0.0.4版本,更新对应版本`Config.plist`
+ 更新`EFI`-`OC`-`Drivers`驱动,移除`AptioMemoryFix.efi`,增加`FwRuntimeServices.efi`
+ 更新`EFI`-`OC`-`Tools`工具
+ 定制`AppleALC.kext`,默认使用ID：98（62000000）无需使用`ALCPlugFix`和`CodecCommander.kext` ,3.5mm麦克风需要手动切换；可选原版ID：99（63000000）需安装 `ALCPlugFix` 并打开 `CodecCommander.kext` 驱动
+ 默认打开 `BrcmFirmwareData.kext` , `BrcmPatchRAM2.kext`（`DW1820A`蓝牙驱动）,此驱动经过修改只适合ID：`0a5c_6412`使用

#### 2019-08-06

+ `Acidanthera`原版`AppleALC.kext` + `ALCPlugFix` + `CodecCommander.kext` 能使3.5mm耳麦正常切换,但目前在睡眠唤醒的时候大概率会出现人声丢失,重新插拔可恢复正常!
+ `子骏`定制的`AppleALC.kext`无需使用`ALCPlugFix`和`CodecCommander.kext` ,耳机正常,睡眠唤醒正常,但目前麦克风部分需要手动切换！
+ 默认关闭下列驱动,有需要的请至`Config.plist` - `Kernel` - `Add` 下找到对应驱动的参数`Enabled`改为为`YES`
    + `CodecCommander.kext`
    + `BrcmBluetoothInjector.kext`
    + `BrcmFirmwareData.kext`
    + `BrcmPatchRAM2.kext`
+ 默认使用`子骏`定制版`AppleALC.kext`,如需使用`Acidanthera`原版,请至`EFI` - `OC` - `Kexts`中删除`AppleALC.kext` 修改`AppleALC-Acidanthera.kext`文件名为`AppleALC.kext`,希望大家多多试用反馈,有条件的可以联系`子骏`帮忙提交相关部分给`Acidanthera`

#### 2019-08-05

+ 移除所有更名的限制查找条件以保证不同版本BIOS的通用性

#### 2019-08-04

+ 移除`SSDT-Air13IWL.aml`中的`OCOS`补丁
+ 添加`宪武`大佬最新`Windows 2018 to Darwin`更名补丁

#### 2019-08-03

+ 移除声卡注入`device-id`，修改`Air13IWL.kext`，声卡驱动`AppleALC.kext`可单独使用不在受`FakePCIID.kext`和`FakePCIID_Intel_HDMI_Audio.kext`影响，使用HDMI音频仍需`FakePCIID.kext`
+ 参考`宪武`大佬关于`AptioMemoryFix.efi`正确使用方式，默认打开`Config.plist`-`Kernel`-`Quirks`-`DisableIoMapper`，同时建议在隐藏BIOS禁用`CFG Lock`
+ 添加启动项`Verify MsrE2`可查看MsrE2(CFG Lock)锁定解锁状态
+ 移除部分驱动内的非必要文件，移除`Config.plist`-`NVRAM`-`LegacySchema`下内容

#### 2019-07-27

+ 合并更新`SSDT-Air13IWL.aml`、`SSDT-GPRW.aml`
+ 从`Air13IWL.kext`中分离`BrcmBluetoothInjector.kext `
+ 补全部分更名参数
+ 添加启动工具`UEFI Shell`和`Clean Nvram`
+ 补全部分NVRAM为OC官方推荐项

#### 2019-07-25

+ 添加部分NVRAM参数
+ 上传完整EFI目录方便单系统用户直接替换

#### 2019-07-17

+ 添加`GPRW to XPRW`更名,`0D/6D`补丁,暂时性解决睡眠秒醒问题.
+ 更新配置文件:默认打开所有设备引导扫描,如需关闭修改`Config.plist`-`Misc`-`Security`-`ScanPolicy`为`983299`

#### 2019-07-15
+ 使用OpenCore-0.0.3-Releases .
+ 使用前先补全`Config.plist` - `PlatformInfo` - `Generic`下的空白内容.
+ 已更换`DW1820A`蓝牙ID为`0a5c`,`6412`的可以直接使用(仍需配合虚拟机大法).
+ 目前已知问题:插入USB设备时会有睡眠秒醒问题,添加`0d/6d`补丁可解决!
+ 整合`SSDT-OCOS.aml` , `SSDT-XCPM.aml` , `SSDT-PNLF.aml` , `SSDT-SBUS.aml` , `SSDT-EC.aml` , `SSDT-Q11Q12.aml` 合并为`SSDT-Air13IWL.aml`
+ 整合`CPUFriendProvider.kext` , `FakePCIID_Intel_HDMI_Audio.kext` , `XHCI-unsupported.kext` , `USBPorts.kext` , `BrcmBluetoothInjector.kext` 合并为`Air13IWL.kext`