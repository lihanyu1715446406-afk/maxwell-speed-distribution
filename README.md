# 麦克斯韦速率分布 · 交互式拓展

> 从一张思维导图，到一个可以动手操作的物理实验室。

一个基于纯 HTML / CSS / JavaScript 的交互式物理课件，用来演示**麦克斯韦速率分布**随温度、分子质量的变化。无需安装、无需联网，单个文件即可运行。

[![在线预览](https://img.shields.io/badge/在线预览-GitHub%20Pages-1f6feb?style=flat-square)](https://lihanyu1715446406-afk.github.io/maxwell-speed-distribution/)
[![License: MIT](https://img.shields.io/badge/License-MIT-0ca678?style=flat-square)](LICENSE)
[![单文件](https://img.shields.io/badge/单文件-零依赖-7c4dff?style=flat-square)](index.html)

## 在线预览

**https://lihanyu1715446406-afk.github.io/maxwell-speed-distribution/**

手机、平板、电脑的现代浏览器都可以直接打开。

## 这是什么

原思维导图用两张静态曲线说明了「温度越高，分子速率越大」「分子越轻，速率越大」两个结论。这个页面把这些静态结论做成了可以亲手验证的实验：

- 拖动温度滑块，实时看曲线怎么移动、怎么变宽；
- 换一种气体，比较轻分子与重分子的分布差异；
- 打开分子模拟，看 320 个分子的运动如何「长成」理论曲线；
- 开启能量阈值，读出超过活化能的分子占比。

## 功能

### 01 · 交互实验
- 温度范围 20 K – 1500 K，实时重绘分布曲线
- 内置 H₂、He、H₂O、N₂、O₂、CO₂、UF₆ 七种气体，并支持 1 – 400 g/mol 的自定义摩尔质量
- 单条 / 温度对比 / 质量对比三种显示模式
- 自动标注最概然速率 $v_p$、平均速率 $\bar v$、方均根速率 $v_{rms}$，并实时给出数值
- 鼠标悬停读取任意速率处的概率密度
- 能量阈值模式：拖动阈值，实时计算速率超过阈值的分子占比
- 一键自动演示、恢复初始状态

### 02 · 分子模拟
- 320 个分子的二维运动模拟，速度分量按麦克斯韦分布抽样
- 随时间累积的速率直方图，叠加理论曲线
- 直观展示「统计规律需要足够大的样本」这一结论

### 03 · 公式推导
- 6 步可点击推导：为什么出现指数、常数从哪来、为什么多出 $v^2$、峰值在哪
- 速度空间球壳示意图与形状分解图
- 完整公式 $f(v)=4\pi\left(\dfrac{m}{2\pi kT}\right)^{3/2} v^2 e^{-mv^2/2kT}$

### 04 · 三种速率
- $v_p : \bar v : v_{rms} = 1 : 1.128 : 1.225$
- 与温度、摩尔质量的关系，并给出常用气体在常温下的参考值

### 05 · 真实应用
- 大气逃逸、蒸发与沸腾、化学反应速率、同位素分离、低温物理、玻尔兹曼分布的入口
- 每个场景都可以一键把参数载入实验区

### 06 · 过程留痕
- 五轮修订记录：每轮的问题、修改、结果
- AI 提示词节选，说明 AI 在每一步做了什么

## 技术实现

- **单文件**：所有样式、脚本、图形都内联在 `index.html` 中，无任何外部依赖与 CDN
- **Canvas 绘制**：主曲线、模拟、直方图、示意图均为 Canvas / SVG 实时绘制，并适配 `devicePixelRatio` 高清显示
- **响应式布局**：从 390 px 手机宽度到桌面宽屏均可正常使用
- **可访问性**：控件带 `aria-label`，支持键盘操作，遵循减少动画偏好
- **零网络请求**：页面不加载任何外部资源，不上报任何数据

## 本地运行

```bash
git clone git@github.com:lihanyu1715446406-afk/maxwell-speed-distribution.git
cd maxwell-speed-distribution
```

双击 `index.html`，或用任意静态服务器打开：

```bash
python -m http.server 8000
# 然后访问 http://localhost:8000
```

## 项目结构

```
.
├── index.html   # 全部内容：页面、样式、交互逻辑
├── README.md    # 项目说明
└── LICENSE      # MIT 许可证
```

## 部署

仓库已开启 GitHub Pages，从 `main` 分支根目录发布。每次推送到 `main`，约半分钟后线上自动更新。

## 隐私说明

页面是纯前端静态文件：

- 不含任何个人信息、账号、密钥或令牌；
- 不发起任何网络请求，不使用 Cookie、localStorage 或第三方统计；
- 所有计算都在浏览器本地完成。

## 许可证

本项目采用 [MIT License](LICENSE)。
