# Clash / Mihomo Developer Config

一份面向开发者、AI 工具用户和局域网多设备共享场景的 Clash / Mihomo 配置模板。

支持客户端 / 内核：

- Mihomo
- Clash Meta
- Clash Verge / Clash Verge Rev
- OpenClash Meta

> 说明：旧版 Clash Core 不保证完整兼容。

---

## Features

- AI 服务分流优化  
  OpenAI / ChatGPT / Claude / Perplexity / OpenRouter / Hugging Face / Gemini API

- 开发下载链路优化  
  GitHub / Docker / npm / pip

- 常用服务分流  
  Apple / Google / YouTube / Telegram / Twitter / 游戏平台

- 国内流量直连  
  ChinaMax + ChinaIP + GEOIP(CN)

- DNS 与网络增强  
  Fake-IP + DoH / 自动测速 / 自动故障切换 / 手动节点选择

- 局域网共享支持  
  默认开启 `allow-lan: true`

---

## File

- `clash_config.yaml`：主配置文件

---

## Quick Start

### 1. 下载配置文件
下载仓库中的 `clash_config.yaml`。

### 2. 导入客户端
将该 YAML 文件导入到你的 Clash / Mihomo 客户端中。

### 3. 替换订阅地址
找到下面这一段：

```yaml
proxy-providers:
  Sub:
    <<: *provider
    url: 订阅地址
    path: ./proxy_providers/sub.yaml
```

把：

```yaml
url: 订阅地址
```

替换为你自己的订阅链接。

---

## Default Policy

### 🤖 AI 专线
以下服务默认走 `🤖 AI专线`：

- OpenAI
- Claude
- Perplexity
- OpenRouter
- Hugging Face
- Gemini API

### 🧑‍💻 开发下载
以下链路默认走 `🧑‍💻 开发下载`：

- GitHub
- Docker
- npm
- pip

### 🇨🇳 国内流量
默认通过国内规则集与 `GEOIP(CN)` 直连。

---

## LAN Sharing

本配置默认启用：

```yaml
allow-lan: true
```

这表示局域网中的其他设备（如手机、平板、其他电脑）可以连接当前机器的代理端口使用网络代理。

适合场景：
- 手机 / iPad 共用代理
- 家庭多设备共享
- 局域网统一走代理

如果你只希望当前机器自己使用，请改成：

```yaml
allow-lan: false
```

> 使用 `allow-lan: true` 时，请确认你的防火墙设置、监听地址和局域网环境是可信的。

---

## Recommended Mode

- TUN + Rule

---

## Notes

- 本仓库提供的是**模板配置**，不包含私人订阅、账号或节点信息
- 使用前请自行替换订阅地址
- 不同客户端 / 内核对部分增强特性的支持程度可能不同
- 如果你不需要局域网共享，请手动关闭 `allow-lan`

---

## Suitable For

这份配置更适合：

- 开发者
- AI 工具重度用户
- 需要优化 GitHub / Docker / npm / pip 下载链路的人
- 需要局域网多设备共享代理的人
