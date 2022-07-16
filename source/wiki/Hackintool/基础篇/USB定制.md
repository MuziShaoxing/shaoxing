---
layout: wiki
wiki: Hackintool
order: 25
title: USB定制教程
---


> 版权©️声明 : 
mac定制:出自本站定制记忆
Windows定制: 由本站根据[杆杆只爱学习-【黑苹果】在Windows下定制USB-哔哩哔哩](https://b23.tv/mgdYFB)图文化改编。

------------
## 雷点三补丁
- 请前往以下地址: https://hackindrom.zapto.org/
- 具体教程恕不提供，请自行参考网站内教程
- 如无法访问，请科学⬆️网，谢谢！
## Mac下定制
- 此教程基于Mac版本Big Sur 11.2.3制作完成
- 此教程需求道具协议U盘「 USB2.0x1/USB3.0x1」
- 理论不适用于Mac Big Sur 11.3及更高mac系统版本。
  - 因为解除端口限制的Quirks{% kbd XhciPortLimit %}失效了。

1. 加载USB端口识别驱动[USBInjectAll.kext](https://github.com/daliansky/OS-X-USB-Inject-All)（USBInjectAll.kext于定制完成后需要取消加载！）
{% folding 以下基于 USB控制器 您可能需要安装额外的 kexts %}
[XHCI-unsupported.kext](https://github.com/johnlimabravo/XHCI-unsupported)
  - X99系列芯片组XHC控制器，8086:8d31
  - 200系列芯片组XHC控制器，8086:a2af（根据macOS版本而有）
  - 300系列芯片组XHC控制器，8086:a36d或8086:9ded
  - 400系列芯片组XHC控制器，8086:a3af
  - 500系列芯片组XHC控制器，8086:43ed
{% endfolding %}
2. 勾选解除端口**Quirks**{% kbd XhciPortLimit%}
{% folding 图示 %}
![uqTuKW](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/uqTuKW.png)
{% endfolding %}
3. 重启后打开Hackintool
![jCPspV](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/jCPspV.png)
4. 将USB2.0/3.0U盘依次插入设备所有USB端口
  - {% kbd 对应端口信息会变成绿色 %}
5. 删除所有{% emp 没有变成绿色 %}的端口
6. 拔出所有外接USB设备（键鼠，显示器，蓝牙除外）
7. 将剩下的端口中含设备信息的参数设置为Internal（内建）
  - {% kbd 其他端口按速率设置为：USB2/3 %}
8. 导出成品，将其加载到config配置表重启即可

   {% emp USB定制完成后仅需加载导出的“USBPorts”或“SSDT-UIAC.aml”即可！“USBInjectAll.kext”取消加载勾选 %}

## Windows定制教程
### 下载工具/驱动
- 映射工具:[USBToolBox](https://github.com/USBToolBox/tool)
- 辅助驱动:[USBToolBox.kext](https://github.com/USBToolBox/kext) 
- 编辑工具:[PlistEDPlus-win.7z](https://pan.bilnn.com/s/1lADcn)

### 端口映射
1. 访问[USBToolBox](https://github.com/USBToolBox/tool)下载Windows.exe，并打开。
![1](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/1.png)
2. 键入{% kbd D %} 回车，查看端口信息。
![2](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/2.png)
3. 依次插入USB2.0，3.0，type-c设备，并保持五秒，确保被识别
![3](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/3.png)
4. 识别完成后，键入{% kbd B %} 返回首页。
![4](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/4.png)
5. 键入{% kbd S %} 查看端口信息，（此步操作后页面请截图）
![5](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/5.png)
6. 确认后，键入{% kbd S %}完成导出。
![6](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/6.png)
7. 收到此页面，证明驱动已经自定生成完毕，此时这个工具的使用已经结束
8. 找到对应目录下的文件{% kbd UTBMap.kext %} 打开并找到{% kbd Info.plist %}文件
9. 使用下载好的**PlistEDPlus-win**软件将其打开，依次展开{% u IOKitPersonalities -> XHC -> IOProviderMergeProperties -> ports %}
![xDOq12](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/xDOq12.png)
10. 查看确认内部条目是否大于或等于15条
  - 如≥15请参考提示截图区域端口信息进行删减。
  - 如≤15，则直接下一步）

### 驱动加载
- OC引导
  - -使用Windows版的occ编辑工具将**USBToolBox.kext，UTBMap.kext**加入oc配置表
  - 并移动驱动到{% kbd /EFI/OC/Kexts %}
  {% folding 图示 %}
  ![7WNYE4](https://gcore.jsdelivr.net/gh/muzishaoxing/Picture@main/uPic/7WNYE4.png)
  将驱动信息如图加入{% kbd Kernel-Add %}目录下或文本编辑器复制到对应节点位置粘贴
``` 
<dict>
				<key>Arch</key>
				<string>Any</string>
				<key>BundlePath</key>
				<string>USBToolBox.kext</string>
				<key>Comment</key>
				<string>Windows定制总线暴露1/2</string>
				<key>Enabled</key>
				<false/>
				<key>ExecutablePath</key>
				<string>Contents/MacOS/USBToolBox</string>
				<key>MaxKernel</key>
				<string></string>
				<key>MinKernel</key>
				<string></string>
				<key>PlistPath</key>
				<string>Contents/Info.plist</string>
			</dict>
			<dict>
				<key>Arch</key>
				<string>Any</string>
				<key>BundlePath</key>
				<string>UTBMap.kext</string>
				<key>Comment</key>
				<string>Windows定制遮蔽器2/2</string>
				<key>Enabled</key>
				<false/>
				<key>ExecutablePath</key>
				<string></string>
				<key>MaxKernel</key>
				<string></string>
				<key>MinKernel</key>
				<string></string>
				<key>PlistPath</key>
				<string>Contents/Info.plist</string>
			</dict>

```
{% endfolding %} 
- 四叶草
  - 将驱动文件移动到{% kbd /EFI/CLOVER/Kexts/Other %} 文件夹
  - 无需修改配置表
