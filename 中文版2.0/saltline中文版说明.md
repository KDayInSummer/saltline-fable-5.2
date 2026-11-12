# Saltline — Fable 5.2 FPS（简体中文）

一款小型浏览器第一人称射击游戏：一个下雨的集装箱码头关卡。在无人机（“海鸥”）与机器狗（“猎犬”）的追猎下，切断三条上行中继。

<img width="1685" height="906" alt="image" src="https://github.com/user-attachments/assets/8dd32149-90f4-4d69-a573-4411a49a9ba9" />

## 在线试玩

https://realcodebear.github.io/saltline-fable-5.2/

## 简体中文版

本仓库额外提供 `saltline中文版.html`：游戏内所有可见文本（界面、无线电、字幕、场景标牌）均已汉化。

- 体积：`index.html` 1,429,762 字节 → `saltline中文版.html` 1,430,856 字节，增加 1,094 字节（+0.08%）
- 中文使用系统字体回退（微软雅黑 / 苹方 / 思源黑体），不额外下载任何字体
- 场景标牌的中文会自动关闭“军用模板断笔”效果，避免笔画被竖缝切断
- 以下内容保留英文：启动页与标题卡的大字 logo `SALTLINE`、罗盘方位（N / NE / E …）、键位名、集装箱编号与国际危险品编号（UN 1202）、枪身毫米级微刻字

## 来历

- 由 **Claude Fable 5.2** 生成。该次运行由 Felix Rieseberg（Anthropic）搭建，并于 2026-11-09 发布在 X 上：
  https://x.com/felixrieseberg/status/2119925633564463609
- 原始可玩作品：https://claude.ai/artifact/BGY1SztrAYcJQHSsnHHGmp
- 据其原帖：一条提示词、无人工反馈、约 8 小时、约 270 万输出 token 与 4.45 亿输入 token（大量命中缓存），按 API 价格约 550 美元。模型、音效与贴图全部由代码生成。以上数字来自作者本人，本仓库未加核实。

游戏的所有功劳归原作者。本仓库只是一个镜像，方便大家本地运行。若作者希望下架，请开 issue。

## 相对原始作品改了什么

游戏代码没有任何改动。仅从 `<head>` 中移除了 claude.ai 的 frame-runtime 脚本，并补上 doctype、charset 与 viewport 标签，使文件能作为普通网页运行。

## 运行

```sh
python3 -m http.server 8731
```

然后打开 http://localhost:8731 ，点击页面以捕获鼠标并开启声音。

中文版请打开 http://localhost:8731/saltline中文版.html 。

整个游戏就是一个文件（约 1.4 MB），内联打包了 three.js，并从 Google Fonts 加载字体，除此之外没有任何外部资源。
