# AirCard 🎴

**简体中文** | [English](README.en.md)

> **适用于 iOS 18+ 的 Apple 钱包卡片皮肤与锁屏密码主题工具，无需越狱。**
> **原项目标注已在 iOS 27 正式版上测试。**
> 基于 `airlift` AirTraffic 同步漏洞实现。

<p align="left">
  <a href="https://www.paypal.com/donate/?hosted_button_id=98QRTC2HFRA4Y"><img src="https://img.shields.io/badge/Donate-PayPal-00457C?style=flat-square&logo=paypal" alt="通过 PayPal 支持原作者" /></a>
</p>

---

## 功能特点

- 🎨 **自定义卡片皮肤：** 为 Apple Pay 和钱包卡片设置图片、纹理或银行标志。
- 🔢 **锁屏密码主题（.passthm）：** 将 `.passthm` 主题中的自定义按键图片应用到 iOS 18+ 锁屏密码键盘。
- 🧩 **密码主题编辑器：** 使用一张壁纸生成无缝海报切片，或为每个按键单独设置图片。
- 🔍 **交互式图片取景：** 在按键中平移、缩放图片，并实时预览 iPhone 锁屏效果。
- ✏️ **编辑现有 .passthm 主题：** 在编辑器中打开 Cowabunga 或 Nugget 主题包，修改按键图片和取景位置，然后重新导出或写入手机。
- ⚡ **单卡与批量设置：** 为每张卡片设置不同皮肤，或一键为选中卡片设置同一张图片。
- 📱 **实时检测卡片：** 在 iPhone 上轻点钱包卡片，即可扫描对应的卡片哈希值。
- 🏷️ **卡片重命名：** 点击卡片名称旁的铅笔设置本地名称，重启后保留，方便区分卡片。
- 🖼️ **保留写入预览：** 保存本应用成功写入的皮肤，重启后显示“上次写入的皮肤”；新选择的图片显示为“待写入的皮肤”。预览是本地记录，不是实时读取的手机卡面。
- 🇨🇳 **默认简体中文：** 界面、操作提示和主要日志使用简体中文；日志支持选中复制和一键复制全部。
- 🚀 **通用 macOS 应用：** 原生支持 **Apple Silicon** 和 **Intel（x86_64）** Mac，应用内附带设备通信辅助工具和图片处理功能。
- 📦 **无需额外配置：** 使用打包好的应用，无需安装 Homebrew、额外 Python 包或手动配置终端环境。

---

## 安装

### macOS 通用 DMG

1. 可从[原项目发布页面](https://github.com/mak5er/AirCard/releases)下载 `AirCard.dmg`；本仓库的修改版可按下方步骤从源码构建，安装包位于 `build/AirCard.dmg`。
2. 打开 `AirCard.dmg`，将 **AirCard.app** 拖入**应用程序**文件夹。
3. 安装包同时包含 Apple Silicon 和 Intel Mac 版本。

> [!NOTE]
> **macOS 首次启动提示（Gatekeeper）：**
> 如果首次启动时提示无法验证开发者，可尝试以下方法：
> - **图形界面：** 在“应用程序”中右键点击（或按住 Control 点击）`AirCard.app`，选择**打开**，再确认打开。
> - **终端：**
>   ```sh
>   sudo xattr -cr /Applications/AirCard.app
>   ```

---

## 自定义 Apple 钱包卡片

1. 将 iPhone 连接到 Mac，解锁手机，并在出现提示时信任此电脑。
2. 在 AirCard 的**钱包卡片**页面点击**扫描卡片**。
3. 在 iPhone 上双击侧边按钮打开 Apple Pay，通过面容 ID 验证后轻点卡片；如未检测到，可再点一次。
4. 点击卡片名称旁的铅笔，为卡片设置便于识别的名称，例如“招商银行储蓄卡”。名称仅保存在本地，不会修改手机中的卡片；留空保存可恢复默认名称。
5. 点击卡片预览选择图片，或直接将图片拖到卡片上。也可使用**批量设置皮肤**。
6. 选中需要更新的卡片，点击**写入皮肤**。
7. 写入成功后，在 iPhone 上彻底关闭钱包 App 并重新打开（或重启手机），查看新皮肤。

> [!TIP]
> 成功写入的图片会保存为本地预览，重启 AirCard 后仍可查看。旧版未保存的皮肤记录，需要重新选择图片并成功写入一次。取消待写入的图片后，会恢复显示已有的上次写入预览。

如果操作失败，请展开**日志**，点击**复制全部**，将完整日志用于排查。

---

## 应用锁屏密码主题（.passthm）

1. 切换到顶部的**密码主题（.passthm）**页面。
2. 将 `.passthm` 文件拖入应用，或点击**选择 .passthm 文件**。
3. AirCard 会解析主题，并显示密码键盘的交互预览。
4. 根据手机系统选择目标版本、语言和字体样式，然后点击**写入密码主题**。
5. 重启 iPhone，重新加载锁屏缓存后查看自定义密码按键。

> [!TIP]
> **多语言与粗体支持：**
> AirCard 可生成不同系统语言及常规、粗体样式对应的按键缓存图片（`--white` 和 `--white-bold`）。通用模式会写入较多文件；选择手机实际使用的语言和字体样式可缩短写入时间。

## 制作与编辑密码主题

1. 在密码主题页面切换到**主题编辑器**。
2. 选择海报图片进行切片，或为独立按键分别添加图标。
3. 在预览中拖动图片调整位置，使用滑块缩放，并选择无缝海报或圆形按键样式。
4. 点击**导出 .passthm**保存主题包，或点击**写入 iPhone**应用主题。

已加载的主题也可以通过**在编辑器中修改**继续编辑。

---

## 从源码构建

在 macOS 上安装 Xcode 或 Command Line Tools，然后进入本仓库目录运行：

```sh
chmod +x build.sh
./build.sh
```

如需获取原项目源码：

```sh
git clone https://github.com/mak5er/AirCard.git
cd AirCard
```

构建脚本会编译 `arm64` 和 `x86_64` 通用二进制文件，将依赖打包到 `build/AirCard.app`，并生成 `build/AirCard.dmg`。原项目仓库不一定包含本仓库新增的中文界面等修改。

---

## 贡献者

- **[@mak5er](https://github.com/mak5er)**：开发者 — [GitHub](https://github.com/mak5er) · [Twitter / X](https://x.com/mak5er)
- **[@Lumid-Off](https://github.com/Lumid-Off)**：贡献者与开发者 — [GitHub](https://github.com/Lumid-Off) · [Twitter / X](https://x.com/LumidOff)
- **[wizzer](https://wizzer.cn)**：本仓库改进与简体中文版本 — [个人主页](https://wizzer.cn)
- **[AirLift](https://github.com/0xjohnnydev/airlift)**，作者 **[0xjohnny（@0xjohnnydev）](https://github.com/0xjohnnydev)**：提供原始 AirTraffic / ATAirlock 沙盒逃逸技术与概念验证，是 `AirliftFFI` 的基础。

## 致谢

核心技术基于 `airlift`（AirTraffic 同步沙盒逃逸）。

---

## 支持原作者

如果你觉得 AirCard 有用，可以通过以下方式支持原作者继续开发：

- **PayPal：** [通过 PayPal 捐赠](https://www.paypal.com/donate/?hosted_button_id=98QRTC2HFRA4Y)
- **TON：** `UQBm9KPhtMw-XVVjirUoa09wzrlyWsbeZhKfefl1Uw-qNZ-r`
- **USDT（TRC20）：** `TDkDMCyjYxgvkWUnQiF5Erk2RyPQMT6G1n`
- **USDT / BNB（BEP20）：** `0x0954dc491c502849d04956ef74634aa5931a08e8`
