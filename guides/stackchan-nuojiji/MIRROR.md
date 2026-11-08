# 第三方教程镜像：StackChan 接入糯叽机

| 项 | 内容 |
| --- | --- |
| 原作者 | 浅默（GitHub: [chainbow524-ai](https://github.com/chainbow524-ai)） |
| 原仓库 | <https://github.com/chainbow524-ai/stackchan-nuojiji-guide> |
| 镜像时间 | 2026-11-08 |
| 上游版本 | `main` @ `3f4f3c7`（2026-10-24 最后推送） |
| 文档许可 | 见本目录 [LICENSE-DOCS.md](LICENSE-DOCS.md)：允许非商业性免费分享、修改、公开发布二改版本，**须保留署名与原仓库链接**，未经授权不得商用 |
| 代码许可 | 见本目录 [LICENSE](LICENSE) 与 [firmware/LICENSE-GEOMETRIC-AVATAR-MIT.txt](firmware/LICENSE-GEOMETRIC-AVATAR-MIT.txt) |
| 来源与致谢 | 见本目录 [CREDITS.md](CREDITS.md) |

## 这是什么

一份可操作的教程：把桌面的 StackChan（M5Stack CoreS3）接进**糯叽机**，让角色能拍照看图、在屏幕上显示字幕、切表情、连接后自动眨眼。包含网关部署（Ubuntu VPS + HTTPS）、设备联网与固件准备、直接接收相机图片、显示修复、自动眨眼、人设工具规则、可选外部识图、头像素材，以及常见问题。

它不是 M5Stack、糯叽机或上游 `stackchan-mcp` 作者的官方说明，是作者个人的实测记录。

## 镜像范围

- ✅ `README.md`、`docs/`、`config/`、`scripts/`、`images/`、`licenses/`、`firmware/README.md` 与各许可/致谢文件
- ❌ `firmware/xiaozhi-public.bin`（应用固件二进制，约 3.5 MB）——按体积不重复入库，请到原仓库或上游 Release `v2.2.6-qianmo.1` 下载，并按上游 `SHA256SUMS.txt` 校验
- ❌ 上游 Release 中约 343 MB 的 `stackchan-public-v2.2.6-qianmo.1-source.tar.gz` 同样不入库

## 和本仓库的关系

本仓库（`stackchan-mcp`）与这份教程是两条并列的路：本仓库是 MCP server + 固件源码，教程是「把 StackChan 接到某一款具体客户端（糯叽机）」的实践记录。教程里的网关版本号 `stackchan-mcp 0.18.0` 与教程自带的固件（应用内显示 `2.2.6`）请以教程正文为准，不要和本仓库当前提交混用。

想看原始 `stackchan-mcp` 的部署方式，回到仓库根目录的 [README](../README.md)。

## 同步上游

```bash
git clone https://github.com/chainbow524-ai/stackchan-nuojiji-guide.git /tmp/nuojiji
git -C /tmp/nuojiji log -1 --format=%h
# 用 /tmp/nuojiji 的内容覆盖本目录（保留 MIRROR.md），再提交
```

## 免责声明

按第三方教程操作存在刷机、配置与网络风险，请先备份固件与配置；镜像仅做长期留存与离线查阅，内容解释权归原作者浅默。
