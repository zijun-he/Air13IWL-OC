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