---
title: Remove-MS-Edge 开源彻底卸载微软Edge浏览器与WebView组件
tags:
  - 软件工具
  - 系统优化
  - 开源软件
categories: 电脑软件
keywords: 'Remove-MS-Edge, Edge卸载, WebView2移除, 系统优化'
description: >-
  Remove-MS-Edge 是一款开源的 Windows 工具，可彻底卸载 Microsoft Edge 浏览器及可选的 WebView2
  运行时，清理注册表、文件与服务残留，支持 GUI 与批处理两种方式。
cover: /img/dnrj_fm.jpg
top_img: /img/rjgj_fm.png
comments: true
abbrlink: 1713767770
date: 2026-07-28 08:00:00
---

## 🛠️ 工具简介

Remove-MS-Edge 是开发者 ShadowWhisperer 在 GitHub 上开源维护的一款 Windows 工具，专门用于彻底卸载 Microsoft Edge 浏览器及其相关组件。它基于 Python 开发，代码完全开源，通过调用 Edge 官方卸载程序并配合注册表、文件、服务和计划任务的深度清理，把那些微软设计为"不可卸载"的系统级组件干净地剥离出来。工具提供图形界面（EXE）与批处理脚本（BAT）两种形态，可满足普通用户一键操作与运维人员自动化部署的不同需求。

它要解决的核心问题是：自 Windows 10 2004 及 Windows 11 起，Microsoft Edge 被深度集成进系统，控制面板里只有"更改"没有"卸载"，常规手段根本删不掉；即便手动删除安装目录，系统更新后又会自动恢复，还会触发 SFC 修复甚至影响 Windows Update。Remove-MS-Edge 把这套繁琐的移除流程封装成一次点击：先跑官方卸载器、再清理 Appx 包、注册表项、残留文件夹、edgeupdate 服务与计划任务，确保 Edge 不会在更新后悄悄回来。

适合的用户群体比较明确：习惯使用 Chrome、Firefox 等第三方浏览器、不愿被 Edge 接管 PDF 与链接打开方式的用户；希望释放系统资源、追求系统纯净度的性能爱好者；需要批量部署精简版 Windows 的运维与装机人员；以及对系统完全控制权有需求的技术玩家。需要提醒的是，移除 Edge 后部分依赖 WebView2 的功能（如小组件、天气、Windows 邮件、Xbox App 等）可能受影响，建议按需保留 WebView2。

### ✨ 核心功能

*   **一键彻底卸载**：调用 Edge 官方卸载程序完成主体移除，再清理 Appx 版 Edge、注册表项、残留文件、edgeupdate 服务与计划任务，避免系统更新后自动恢复。
*   **多版本形态可选**：提供 GUI 图形界面版（Remove-Edge.exe，无需终端，适合普通用户）与批处理脚本版（Edge.bat / Edge-Appx.bat / Both.bat），分别对应仅卸载 Edge、仅卸载 Appx 版、同时卸载 Edge 与 WebView 三种方案，满足高级用户与自动化场景需求。
*   **WebView2 可选保留**：默认勾选同时移除 WebView2，但工具允许取消勾选只卸载 Edge 浏览器本体，保留 WebView2 运行时以兼容依赖它的小组件、Microsoft Photos 编辑、Roblox、Xbox App 等应用。
*   **自动化部署友好**：EXE 版无界面运行，可配合任务计划程序在系统更新后自动重新移除 Edge，适合长期维护精简系统的运维场景。
*   **全版本兼容与权限检查**：支持 Windows 10 与 Windows 11 各版本，覆盖 x86 与 x64 架构；运行时自动检测管理员权限，权限不足会提示提升，避免半途失败。

## 🎬 视频介绍

{% iframe //player.bilibili.com/player.html?bvid=BV1zMNYz9Eo5&page=1 800 450 %}

## 💡 适用场景

**替换默认浏览器后的清理**：已长期使用 Chrome、Firefox 或其他浏览器，却总被 Edge 接管 PDF、HTML 等文件打开方式的用户，可用该工具彻底移除 Edge，让系统不再被强行"推荐"使用它。

**系统纯净度与性能优化**：追求精简系统、减少后台服务与磁盘占用的性能爱好者，移除 Edge 后可释放相关进程、更新服务与缓存空间，让系统更轻快。

**批量装机与镜像定制**：运维人员可借助批处理脚本将 Edge 移除集成进装机流程或无人值守脚本，为新机器统一交付一套不含 Edge 的精简 Windows，减少后期维护。

**自动化更新后维护**：Windows 更新后 Edge 常被悄悄装回，可把 EXE 版加入任务计划程序，在每次更新后自动重新清理，保持系统长期处于无 Edge 状态。

**WebView2 依赖权衡场景**：需要保留小组件、Microsoft Photos 编辑、Xbox App 等 WebView2 依赖功能的用户，可选择只卸载 Edge 浏览器、保留 WebView2 运行时，兼顾干净与可用。

## 🖼️ 工具预览

![预览图1](https://img5.de5.net/file/260728085606.png)
![预览图2](https://img5.de5.net/file/260728085646.png)

## 🔗 资源地址

*   **GitHub 仓库**：[GitHub](https://github.com/ShadowWhisperer/Remove-MS-Edge)
*   **官网/下载地址**：[Releases](https://github.com/ShadowWhisperer/Remove-MS-Edge/releases)

## 📥 下载地址

*   **下载地址①**：[百度网盘](https://pan.baidu.com/s/1dHkYurSGpbl_sHy07Ezswg?pwd=f7tc)
*   **下载地址②**：[夸克网盘](https://pan.quark.cn/s/04230071a014)
*   **下载地址③**：[迅雷网盘](https://pan.xunlei.com/s/VOyaDWhfWiITDRebkYI6cWoNA1?pwd=j6cy#)

---

## 📝 更新日志

*   **2026-07-28**：首次发布，收录该工具。
---
