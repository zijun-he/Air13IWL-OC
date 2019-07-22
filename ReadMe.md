2019-07-17

1⃣️添加GPRW更名,0D/6D补丁,暂时性解决睡眠秒醒问题.

2⃣️更新配置文件:默认打开所有设备引导扫描,如需关闭修改Config.plist-Misc-Security-ScanPolicy为983299

2019-07-16

OpenCore-0.0.3-Releases

1⃣️使用前先补全Config.plist - PlatformInfo - Generic下的空白内容.

2⃣️已更换DW1820A蓝牙ID为0a5c,6412的补全1⃣️之后可以直接使用(仍需配合虚拟机大法).

3⃣️目前已知问题:插入USB设备时会有睡眠秒醒问题,添加0d/6d补丁可解决!

4⃣️整合SSDT-OCOS.aml , SSDT-XCPM.aml , SSDT-PNLF.aml , SSDT-SBUS.aml , SSDT-EC.aml , SSDT-Q11Q12.aml 合并为Air13IWL.aml

5⃣️整合CPUFriendProvider.kext , FakePCIID_Intel_HDMI_Audio.kext , XHCI-unsupported.kext , USBPorts.kext , BrcmBluetoothInjector.kext 合并为Air13IWL.kext



