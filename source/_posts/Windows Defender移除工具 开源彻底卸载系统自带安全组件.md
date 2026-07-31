---
title: Windows Defender移除工具 开源彻底卸载系统自带安全组件
tags:
  - 软件工具
  - 系统优化
  - 开源软件
categories: 电脑软件
keywords: 'Windows Defender移除工具, Defender卸载, windows-defender-remover, 系统优化'
description: >-
  Windows Defender移除工具是一款开源脚本工具，可彻底移除或禁用 Windows 8.x/10/11 中内置的 Windows Defender
  及相关安全组件，释放系统资源、提升性能。
cover: /img/dnrj_fm.jpg
top_img: /img/rjgj_fm.png
comments: true
abbrlink: 1643503912
date: 2026-07-28 08:00:00
---

## 🛠️ 工具简介

Windows Defender 移除工具（项目名 windows-defender-remover）是开发者 ionuttbara 在 GitHub 上开源维护的一款脚本工具，专门用于在 Windows 8.x、Windows 10（各版本）以及 Windows 11 中彻底移除或禁用 Windows Defender 及其相关安全组件。它通过模块化的注册表修改、服务停止与系统策略调整，把那些微软设计为"无法卸载"的深度集成组件从系统中剥离出来，并支持将 Defender 移除功能集成进自定义 Windows 安装镜像，实现装系统时一步到位。

它要解决的核心问题是：Windows Defender 深度嵌入系统，常规的"设置—应用"路径无法卸载，而它又时常以高 CPU 占用、实时扫描拖慢磁盘、误报破解补丁或激活工具等形式成为日常使用的负担。对于一些已经部署第三方安全方案、或在受控/离线环境中工作的用户，Defender 的存在反而是一种干扰。这款工具把移除过程封装成可执行脚本，并提供"完全移除/临时禁用/恢复还原"三种模式，让原本需要手工编辑注册表、停服务的复杂操作变得可控且可逆。

适合的用户群体也比较明确：希望释放系统资源、提升性能的游戏玩家与工作站用户；与 Defender 实时保护产生冲突的专业软件使用者；需要批量部署精简版 Windows 的运维或装机人员；以及对系统完全控制权有需求的技术爱好者。需要强调的是，移除安全组件会降低系统防护等级，建议在已有其他安全措施的前提下使用，并在操作前创建系统还原点。

### ✨ 核心功能

*   **模块化移除设计**：分为 Remove_SecurityComp（安全组件移除）、Remove_Defender（防病毒组件移除）与 ISO_Maker（安装镜像定制）三大模块，可针对性禁用 VBS、SmartScreen、UAC、Pluton、Spectre/Meltdown 缓解措施等，在老旧 Intel CPU 上可获得约 30% 的性能提升。
*   **三种操作模式**：通过 Script_Run.bat 或命令行参数支持完全移除（/r）、临时禁用（/d）、恢复还原（/u）三种模式，既能彻底卸载，也能在需要时回退到原始状态。
*   **防病毒核心清理**：强制停止 Antivirus Service、移除 Windows Defender 病毒库更新列表、SpyNet 遥测、上下文菜单扫描项，并隐藏 Windows 安全中心中的防病毒区域，让 Defender 真正"消失"。
*   **ISO 镜像定制**：ISO_Maker 模块支持将无人应答文件（autounattend.xml / unattend.xml）集成进 Windows 安装镜像，实现装机时即预禁用 Defender，适合批量部署精简系统。
*   **全版本兼容**：支持 Windows 8.x、Windows 10 全部版本（专业版/企业版/教育版/LTSC 等）以及 Windows 11 各版本，覆盖 32/64 位，要求管理员权限运行。

## 🎬 视频介绍

{% iframe //player.bilibili.com/player.html?bvid=BV1NUMqz9EZs&page=1 800 450 %}

## 💡 适用场景

**性能敏感的游戏与工作站**：在老旧 Intel CPU 上关闭 Spectre/Meltdown 缓解可恢复约 30% 性能，对追求帧率稳定或大型软件响应速度的玩家、设计师、视频剪辑师而言，是减少后台扰动的实用手段。

**专业软件冲突排查**：部分行业软件、激活工具、破解补丁会被 Defender 误判为威胁而无法运行，使用该工具彻底移除相关组件可解除干扰，适合调试环境与开发测试使用。

**批量装机与系统精简**：运维人员可借助 ISO_Maker 模块把 Defender 移除逻辑预置进安装镜像，为新机器统一交付一套精简、低占用的 Windows，减少后期维护工作。

**已部署第三方安全方案的环境**：若已安装火绒、卡巴斯基等第三方杀毒，Defender 处于被动/禁用状态仍占用资源，可通过此工具彻底清理，避免两套防护共存造成的冲突与浪费。

**受控/离线测试环境**：虚拟机、实验环境、隔离网络中的设备不联网也不会感染外部威胁，移除 Defender 可获得更纯净的测试环境，便于复现问题与对照实验。

## 🖼️ 工具预览

![预览图1](https://img5.de5.net/file/260728083513.png)
![预览图2](https://img5.de5.net/file/260728084705.png)

## 🔗 资源地址

*   **GitHub 仓库**：[GitHub](https://github.com/ionuttbara/windows-defender-remover)
*   **官网/下载地址**：[Releases](https://github.com/ionuttbara/windows-defender-remover/releases)

## 📥 下载地址

*   **下载地址①**：[百度网盘](https://pan.baidu.com/s/1uparkEL8RgOMdmUMr3gRhg?pwd=f5bh)
*   **下载地址②**：[夸克网盘](https://pan.quark.cn/s/fd060cb73aa6)
*   **下载地址③**：[迅雷网盘](https://pan.xunlei.com/s/VOyaBH1hefZ6hNWLkiA2Ak6GA1?pwd=u4da#)

---

## 📝 更新日志

*   **2026-07-28**：首次发布，收录该工具。
---
