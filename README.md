# GW-LINK L510 固件更新

GW-LINK L510（MediaTek MT7986A、2 GiB RAM、128 GB eMMC）的公开固件发布与 OTA 更新渠道。

**[下载正式版](https://github.com/hongheshan-svg/gw-link-l510-firmware/releases/latest)**

选择 `gw-link-l510-…-sysupgrade.bin`，先备份配置，再从路由器后台“系统 → 备份与更新”上传。
从 **20261031.2-ota** 起，可以在“系统 → OTA 在线升级”检查新版本、下载校验并确认安装。
后台只自动检查，不自动安装；安装会保留配置并重启。请保持供电。

## OTA 校验

`ota.json` 和 `ota.json.sig` 是签名更新清单；仅正式 Latest 版本用于在线更新。
公钥指纹：`6247692bc85368ec`。路由器校验签名、SHA256、文件大小、设备型号、平台和版本，并执行标准 sysupgrade 兼容性检查。
不需要 GitHub 令牌。下载需能访问 GitHub 及 Releases 资产域名，系统时间需正确。
此设备未配置 A/B 自动回滚。发布在隔离环境编译与验证，实机结果应由使用者确认。

## 源码和许可

基于 [OpenWrt](https://github.com/openwrt/openwrt) 25.12.6，使用发布附件中的固定 feeds 和本地补丁构建。
每个正式版本附带配置、源代码版本、`local-build-sources.tar.gz` 和验证报告；它们与上游公开源码共同描述相应构建。
遵循 OpenWrt 及每个软件包各自的许可证。此仓库仅作为公开固件和对应构建资料的发布渠道。
固件不包含发布签名私钥或 GitHub 访问令牌。

本型号的新安装默认双频 SSID 为 `GW-LINK`，无线密码为 `12345677`；请在部署时修改无线和管理员密码。
