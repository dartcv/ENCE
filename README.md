<div align="center">

# ✨ ENCE

### 少一点等待，更快进入应用

**Android 广告跳过 · 无障碍服务 · 自定义规则**

![Android](https://img.shields.io/badge/Android-8.1%2B-3DDC84?style=for-the-badge&logo=android&logoColor=white) ![No root](https://img.shields.io/badge/ROOT-NOT_REQUIRED-2563EB?style=for-the-badge) ![Closed source](https://img.shields.io/badge/SOURCE-CLOSED-334155?style=for-the-badge)

[![Stars](https://img.shields.io/github/stars/dartcv/ENCE?style=flat-square&logo=github&label=Stars&color=f59e0b)](https://github.com/dartcv/ENCE/stargazers) [![Downloads](https://img.shields.io/badge/Downloads-pending%20release-64748b?style=flat-square&logo=github)](https://github.com/dartcv/ENCE/releases)

**[📦 发布页面](https://github.com/dartcv/ENCE/releases) · [✨ 功能概览](#-功能概览) · [🚀 开始使用](#-开始使用) · [🛠️ 规则管理](#-规则管理) · [❓ 常见问题](#-常见问题)**

</div>

<!-- 首次发布带附件的 Release 后，可将 Downloads 徽章替换为：
[![Downloads](https://img.shields.io/github/downloads/dartcv/ENCE/total?style=flat-square&logo=github&label=Downloads&color=22c55e)](https://github.com/dartcv/ENCE/releases)
-->

---

**ENCE 是一款通过 Android 无障碍服务识别并尝试跳过应用启动广告的工具。** 支持通用跳过识别、按应用配置规则和排除应用，帮助减少打开应用时的等待。

无需 Root，无需 Xposed 框架。安装后，由你手动开启无障碍服务和广告跳过开关。

> [!IMPORTANT]
> **ENCE 为闭源项目。** 本仓库仅用于项目介绍，不公开项目源代码。

## ✨ 功能概览

| 功能 | 说明 |
| --- | --- |
| ⏩ 通用广告跳过 | 在应用启动期间识别跳过目标并尝试执行操作 |
| 🎯 应用专用规则 | 按包名配置匹配条件与动作，适应不同应用的页面结构 |
| 🛠️ 自定义匹配 | 支持节点 ID、文字、描述、树路径、前置条件与节点排除 |
| 👆 多种执行动作 | 支持节点点击、返回、手势及受节点范围约束的坐标后备动作 |
| 📋 规则管理 | 支持规则开关、编辑、版本迁移与弹窗规则子集导入 |
| 🚫 排除应用 | 按应用名称或包名搜索，多选排除，勾选后立即保存 |
| 🧾 日志与诊断 | 支持日志级别筛选、清空、ZIP 导出和诊断信息复制 |
| 🎨 外观与导航 | 支持跟随系统、浅色与深色主题，提供浮空导航和左右滑动翻页 |
| 🔔 后台运行设置 | 提供电池优化设置入口与可选的常驻通知保活 |

> [!NOTE]
> 项目持续开发中，规则能否生效取决于应用版本、页面结构与设备环境。部分新增功能仍待真机验证，不能保证跳过所有广告。

## 🚀 开始使用

运行环境为 **Android 8.1 及以上**。

1. 安装并打开 ENCE。
2. 在主页点击 **打开无障碍设置**。
3. 在系统设置中手动启用 **ENCE 广告跳过** 服务。
4. 返回 ENCE，打开 **启用广告跳过** 开关。
5. 打开需要处理的应用，观察实际跳过效果。

> [!TIP]
> 广告跳过开关默认关闭。无障碍服务连接与功能开关都启用后，ENCE 才会开始处理目标应用。

<details>
<summary><strong>🚫 不想处理某个应用？</strong></summary>

进入 **设置 → 排除应用**，搜索应用名称或包名并勾选目标应用。

勾选后立即保存，取消勾选即可恢复处理。列表支持多选、仅查看已排除项和手动刷新。

</details>

<details>
<summary><strong>🔔 如何减少后台被系统回收？</strong></summary>

在后台运行设置中，按需调整电池优化配置或开启通知保活。通知保活需要允许 ENCE 发送通知。

常驻通知可减少后台回收，但不能保证进程始终运行，也不能代替无障碍授权。

</details>

## 🛠️ 规则管理

通用识别无法处理的页面，可在 **设置 → 应用规则** 中配置专用规则。

- 按应用包名确定规则作用范围。
- 使用 ID、文字、描述或树路径匹配目标节点。
- 配置前置条件与排除条件，缩小匹配范围。
- 按需选择点击、返回或手势等动作。
- 配置执行时间窗、匹配后延迟与尝试上限。

**新建规则默认停用。** 请核对匹配条件和动作后，再手动启用。

<details>
<summary><strong>📦 内置规则草稿与高级管理</strong></summary>

内置目录提供 **161 个应用、197 条停用规则草稿**，可按需导入与启用。草稿数量不代表已经验证支持的应用数量。

已导入过的应用可选择仅补充缺失草稿，保留已有修改与顺序。高级管理入口提供规则 JSON 管理。

内置部分青少年模式提醒关闭草稿，仅针对匹配的提醒按钮，不改变青少年模式设置。

</details>

## 🧾 日志与诊断

日志页提供带毫秒的本地时间、事件与操作详情，并支持 `DEBUG`、`INFO`、`WARN`、`ERROR` 级别筛选。

- 本机保留最近 **1,000 条**日志。
- 支持自动换行与单行横向滚动。
- 导出 ZIP 时，由你选择保存位置，导出全部保留记录。
- 压缩包包含 `logs.txt`、`logs.jsonl` 与格式说明。
- 在 **设置 → 帮助与诊断** 中可复制诊断信息。

日志仅记录预定义事件和脱敏元数据，不保存屏幕文字、输入内容、目标包名、规则原文或异常消息；日志不参与系统备份。

## ❓ 常见问题

<details>
<summary><strong>启用后为什么没有跳过广告？</strong></summary>

请检查主页的服务连接状态、广告跳过开关，以及目标应用是否被排除。对于专用规则，还需确认规则已启用、包名正确且匹配条件适用于当前页面。

部分广告不提供可识别的无障碍节点，或在应用更新后改变了页面结构，因此可能无法处理。

</details>

<details>
<summary><strong>更新安装后，主页显示服务未连接怎么办？</strong></summary>

在系统无障碍设置中，手动关闭再重新开启 **ENCE 广告跳过** 服务，然后返回主页检查连接状态。

</details>

<details>
<summary><strong>日志显示操作被接受，为什么广告还在？</strong></summary>

操作被系统接受，只表示请求已发送或受理，不代表广告已经关闭。请结合实际页面结果判断，并检查规则匹配条件与执行动作。

</details>

<details>
<summary><strong>ENCE 会一直点击屏幕吗？</strong></summary>

ENCE 在有限的启动时间窗内处理目标，并设有去重与尝试上限。默认时间窗为 **8 秒**；显式规则可配置 **1–30 秒**。

屏幕锁定、ENCE 自身界面、桌面、系统授权界面及排除应用不处理。关闭功能或修改规则会取消当前任务。

坐标动作要求匹配可见节点，且坐标位于节点范围内；执行前会再次检查节点与活动窗口。

</details>

## ☕ 支持 ENCE

如果 ENCE 帮你减少了等待，欢迎扫码赞赏，支持项目持续维护。

<div align="center">

<img src="assets/reward-qrcode.png" alt="ENCE 赞赏码" width="280">

**感谢你的支持 ❤️**

</div>

---

<div align="center">

**更少等待 · 按需配置 · 自主控制**<br>
<sub>ENCE · Android Ad Skip</sub>

</div>

