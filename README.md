# N1 OpenWrt 轻量固件--旁路专用 每周五早8点自动更新

**集成**
- 晶晨宝盒：安装 OpenWrt 至 EMMC、在线下载更新——>完整更新全系统；
- 插件SSR+、passwall、passwall2、nps、zerotier、kms、timectrol
  - 新增openclash(4月3日）


**旁路网关模式**
- DHCP关
- 默认IP 192.168.1.200，网关192.168.1.1，关闭桥接，开启IPV6
- 后续如有更改可保留配置升级
- 个人目前改单臂主路由模式使用，加VLAN交换机或参考本人文章设置AP https://www.ymschh.top/2023/04/04/小米路由ax1800开启vlan实现n1单线复用/

**参考设置**
- 推荐使用passwall2，完美兼容IPV6，自带DNS管理，使用TPROXY模式可完全防止DNS泄露（openclash做不到），也不再需要smartDns和AdguadeHome
- 节点选择xray分流 （直接选择节点相当于全局代理）
- 默认分流策略为白名单模式，可按以下排序自行调整成PAC(gfw)模式：
   - AD (geosite:category-ads-all)
   - BT
   - Proxy (geosite:gfw geosite:greatfire)
   - Direct
- 国内dns自动(建议手动选择alidns)，国外自由选择。如需代理IPV6选择useIP

**如遇+版有IPV6问题，可选择+o版**

* 源码来源： Lean 的 Openwrt 源码仓库 https://github.com/coolsnowwolf/lede
- 脚本参考： https://github.com/huangqian8/Cloud-N1-OpenWrt | https://github.com/P3TERX/Actions-OpenWrt
