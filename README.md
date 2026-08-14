#Aonself v1.0.0

## 功能

| 功能 | 实现方式 | 架构 |
|------|----------|------|
| 隐藏 root 痕迹 | Zygisk 注入
| 隐藏 BL 解锁状态 
| TEE 状态伪装为完好
| keybox密钥

## 低功耗设计

- 无常驻 daemon、无轮询、无周期任务
- 属性伪装为开机一次性设置，完成后零开销
- Zygisk hook 为事件驱动：仅在系统调用发生时触发，正常运行时无额外耗电

## 安装

1. 设备需已 root（Magisk 或 KernelSU）
2. 直接刷入本 zip
3. 重启生效

## 替换 keybox

1. 用你的 keybox 内容替换 `/data/adb/Aonself_Stealth/keybox.xml`
2. 重启

## 卸载

直接卸载模块即可；Zygisk Next 为独立模块，如需一并卸载请单独操作。

## 说明与边界

- Zygisk Next为内置
- 本模块整体以 GPL-3.0 开源：修改分发须保持同协议、标记原作者并附源码
- 真正的硬件级（物理 TEE 损坏）无法通过软件修复，本模块为软件层伪装

## 协议

GPL-3.0
