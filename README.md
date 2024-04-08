
# WinXray 
WinXray[:loud_sound:](http://dict.youdao.com/dictvoice?audio=winxray&type=2) 是最简洁轻快的 V2Ray、XRay、Trojan、Trojan-go、Shadowsocks、SSR(ShadowsocksR)、SSRoT、NaïveProxy，SOCKS，HTTP,HTTPS 全能通用客户端（Windows系统），支持并发检测大量服务器并迅速找到当前最快的服务器，服务器连接异常时可自动寻找其他速度最快的服务器 - 切换速度快如闪电，自订阅源获取的服务器异常时可自动刷新订阅，并且自带一键自动部署服务端工具。



# 本项目说明
项目克隆自 [https://github.com/TheMRLL/WinXray](https://github.com/TheMRLL/WinXray)  
很显然，我克隆的这个项目就是上面所说的抄袭版，加了很多广告。   

### 为什么选择在这个“抄袭版”的基础上改进
这个版本是我接触`winxray`的第一个版本，用了很久，代理上没有什么问题，且这个版本较其他版本改进了些内容，比如  
- 将首选`core`由`v2ray`替换为更好的`xray`
- 添加二维码识别功能
- 其他优化（可能吧...）

### 改进计划
虽然这个版本较原版有些优化，但仍然值得改进。  
- [x] 删除所有广告
- [x] 优化系统托盘显示与交互
- [x] github直连下载改为github加速下载
- [x] 调整配置目录为和应用同级的config目录，方便打包拷走
- [x] 移除检查更新用的大文件
- [x] 节点测速方式更新
- [x] 默认pac规则更新

# 设置系统代理失败怎么办
如果设置代理以后不能正常生效：请首先右键点击 winXray 任务栏的托盘图标，在弹出的右键菜单中点击【查看 Internet 代理设置】，并检查代理设置是否正常。如果 winXray 不能修改代理设置，但是可以手动修改成功，这一般是被安全软件错误地拦截了( 而且安全软件没有正常弹出确认对话框，或者误点了阻止设置 ）。这时候请到安全软件的相关设置中将 winXray 添加到信任列表即可。

如果不是上面的原因，请按下【Win + R】组合键打开系统运行对话框，输入 regedit 点击确定打开注册表路径 
<span style="color:green">HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings\Connections</span>
然后将“Connections”项删除，注销一下系统即可正常使用代理了。

如果上面的方法仍然不行，请在注册表中打开打开路径
<span style="color:green">Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\WinHttpAutoProxySvc</span>
将 start 的值改为 2， 也就是将 WinHttpAutoProxySvc 服务改为自动启动，然后重启计算机即可。
