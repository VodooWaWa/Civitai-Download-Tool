![LOGO](Example%20image/LOGO.png)
# 🧸 Civitai 下载解析工具｜超全使用指南
AI 模型下载/管理/整理 一站式神器✨
为[视图选择器](https://github.com/VodooWaWa/Comfyui-Visual-Select)插件量身定制配套组合。

本软件专门用来解析 Civitai / HuggingFace 模型链接
批量下载➕断点续传➕自动封面➕哈希校验，解决你大模型下载容易失败的问题。
本地模型整理 + 离线HTML查看 + 提示词/工作流解析
一键复制参考，新手也能轻松上手～

**很奇怪，360会误报我的工具有毒。[Virscan扫描链接](https://www.virscan.org/report/44443db50ca33f078ac1ba3f6d9d3082ba6255377d681755814d6d86b5f6e5ad)，这是VirScan的扫描记录，全过。不放心的自己扫描一遍。**
![Virscan](Example%20image/VirScan.png)

工具使用视频教程B站链接：https://www.bilibili.com/video/BV1kcDMBHELM/

## ​​✨v 1.1.0 版本更新
- 新版本我懒的再扫Virscan了，不放心的自己扫一下。
- 新增图片视频元数据反向解析功能（原本这个功能只用在html生成），现在可以自由扔图和视频进去解析。
  ![Parsing and Translation](Example%20imageParsing and Translation.png.png)

---

## 🚀 如何运行
- 因为解析视频图片工作流需要调用[exiftool](https://exiftool.org/)和[ffmpeg](https://ffmpeg.org/download.html#build-windows)，本仓库没有内置，请自行下载解压，或者去[百度网盘](https://pan.baidu.com/s/1R2q6ZoO7Axf2nw5Jx3LRsw?pwd=dw9e)直接下载ALL版本。

- 通过网盘分享的文件：Civitai下载助手
链接: https://pan.baidu.com/s/1R2q6ZoO7Axf2nw5Jx3LRsw?pwd=dw9e 提取码: dw9e

- 解压后按CivitaiDownloader.exe | ffmpeg\bin\ffmpeg.exe（以及可选 ffprobe.exe、ffplay.exe） | exiftool\exiftool.exe结构将程序放到同一根目录。
- 打开运行：`CivitaiDownloader.exe`
- 默认模型下载：`程序目录\downloads\models`
- 默认封面缓存：`程序目录\downloads\images`

---

## ⚙️ 配置文件位置
配置存在 程序主目录`user_config.json`
记住下载路径、代理、并发数、API Key 等

---

## 📌 主界面 4 大功能
✅ 批量下载Civitai模型：粘贴链接 → 自动解析 → 一键下载（Civitai的CDN地址因网络环境问题需要科学）<br>
✅ 批量下载Huggingface模型：粘贴链接 → 自动解析 → 复制CND地址 → 粘贴到迅雷（Huggingface的CDN地址可以直接访问）<br>
✅ 下载管理：暂停/继续/重试/哈希校验<br>

**✅ 模型管理（捐赠版解锁）：**
 - 🌟扫描本地模型 → 全自动补全封面和info信息<br>
 - 🌟全自动按模型类型整理分类到子目录<br>
 - 🌟检查模型是否存在更新<br>
 - 🌟模型哈希校验，避免存在损坏模型<br>
 - 🌟离线HTML生成：无网也能看模型详情 + 基于图片视频元数据进行提示词解析 + 工作流解析复制<br>

---

## 📸 示例截图
- 软件截图
  
![主界面](Example%20image/1.png)
![下载管理](Example%20image/2.png)
![模型管理](Example%20image/3.png)

- 模型管理生成离线模型详情
  
![离线HTML](Example%20image/4.png)

---

## 📥 批量下载教程
1. 粘贴多行链接（每行一个）
2. 支持：Civitai模型页 / 版本页 / API下载链接
3. 点【解析】→ 勾选文件 → 【加入下载】
自动识别：模型名、版本、精度、格式、大小

---

## 📊 下载管理功能
▪ 下载中：等待/下载/暂停/校验/失败
▪ 已完成：查看文件路径+封面+信息
▪ 重试：自动重新获取地址 + 断点续传
▪ 哈希校验：确保模型完整不损坏

---

## 🖼️ 封面自动获取规则
1. 本地已有封面 → 优先显示
2. 模型同名图片（png/jpg/webp）→ 自动加载
3. 网络下载封面 / 视频提取第一帧
重启软件也能快速显示封面图～

---

## 🔧 必看设置建议
- API Key：必填！用于 Civitai 下载权限
- 代理：网络不好一定要开
- 最大任务数：太高容易失败，适中即可
- 下载目录：下载完之后可以用模型管理里的一键整理功能分类各种模型，然后剪切到comfyui目录。

---

## ❌ 常见问题&.注意事项
- 下载失败 / 403？
检查：网络 → 代理 → API Key → 降低并发重试
- 当网络波动剧烈，多次尝试重连，可能会遇到CDN地址切换断点续传请求到新地址返回值异常的情况。下载会从0%开始，程序会备份前一份downloading为backup,可以尝试删除当前分片重命名backup再次断点续传。可是下载完成之后的哈希检测一般无法通过。这个看运气了。
- 扫描模型开启多线程，因为会计算模型哈希值去匹配，可能遇到程序未响应的问题。不要做任何事，静静等待即可。

---

## 💝 解锁完整版
淘宝店铺：铠宝电脑
捐赠即可解锁 模型管理 + 离线HTML 功能

![QR](QR/淘宝-铠宝电脑.png)

