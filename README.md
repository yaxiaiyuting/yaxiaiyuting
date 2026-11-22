### 呀小ii · yaxiaiyuting

写 Android 音乐播放器，也折腾 Linux 桌面上跑 Android 的那点事。

- 🎵 **Arris** —— 开源（GPLv3）Android 音乐播放器：网易云 / QQ / B站 三音源、双语逐字歌词、离线缓存、听歌识曲、一起听 · 主线 `4.1.8-gpl` / LTS `3.7.38-gpl`
- 🐧 **Droidloom 贡献者** —— 在 NVIDIA + KWin 上跑 Android 的 presenter，负责真机验证与输入/窗口问题定位（#23 / #24 / #38）
- 🗂 **开发看板**：[Arris 路线图](https://github.com/users/yaxiaiyuting/projects/1)

---

## Arris — Android 音乐播放器

[Ncrust](https://github.com/GuitaristRin/Ncrust) 的 GPLv3 fork，自建网易云 / QQ 音乐双源播放体验。
主线追新，LTS 求稳，两条线并行维护。

| 线 | 版本 | 定位 |
|---|---|---|
| 主线 | `4.1.8-gpl` | 双源播放、歌单多选、离线缓存、实时通知、一起听 |
| LTS | `3.7.38-gpl` | 老设备与保守用户的长期支持线 |

- 仓库：[yaxiaiyuting/Arris](https://github.com/yaxiaiyuting/Arris)
- 下载：[GitHub Releases](https://github.com/yaxiaiyuting/Arris/releases) · [官网](https://arris.de5.net) · [Gitee 镜像](https://gitee.com/yaxiaiyuting/arris)
- 做过的事：歌单详情长按多选、离线 URL 可播状态、点击反馈不排队、生日祝福视觉重构、后台播放保护引导（按 OEM 自动跳转）、播放卡顿服务侧自愈、上游夹具一致性测试

## Droidloom 贡献者

[Droidloom](https://github.com/denialwm/droidloom) 是把 Android 跑在 Linux 桌面（Denial / KWin + NVIDIA）上的方案。
我在 NVIDIA 独显 + KWin 的机器上做真机验证，把踩到的坑整理成可复现的问题与补丁草案：

| Issue | 问题 | 结果 |
|---|---|---|
| [#23](https://github.com/denialwm/droidloom/issues/23) | 窗口没有标题栏、无法拖动（`WindowDecorations::None`） | 上游 `166b5b89` 修复 |
| [#24](https://github.com/denialwm/droidloom/issues/24) | 滚轮与触控板完全无法滚动（轴事件被丢、合成拖拽零时长、触控板 `axis_source=finger`） | 上游 `7eae524f` 用 wire ABI 8 原生 `ACTION_SCROLL` 修复 |
| [#38](https://github.com/denialwm/droidloom/issues/38) | Android 弹窗之后宿主全场轴事件失效（疑似 pointer grab 未释放） | 进行中 |

> 说明：这些 issue 里我给的是定位、复现步骤和补丁草案，最终实现由上游作者完成并合入主线。

---

<sub>Kotlin / Jetpack Compose / Media3 · Rust / Wayland · 一点 GPLv3 的坚持</sub>
