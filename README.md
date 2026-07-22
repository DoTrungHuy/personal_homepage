# Trung Huy Do — Personal Homepage

单文件个人主页:`index.html` 即整站,无构建、无外部依赖,可直接部署到 GitHub Pages 或任何静态托管。

## 技术

- **GSAP 3.15 + ScrollTrigger**(已内嵌):入场逐字动画、滚动浮现、数字滚动、技能条联动
- **自研 WebGL 水系统**(替代原 Three.js 粒子,文件从 750KB 瘦身到 156KB):
  - 电影开场:泪滴光滴坠入夜色海面 → 涟漪荡开 → 镜头俯转 → 色彩晕染成流体背景(约 4 秒,每会话播一次,可跳过)
  - 波动方程高度场涟漪模拟(借鉴 evanw/webgl-water、jquery.ripples,MIT)+ Gerstner 涌浪 + bloom/ACES filmic 后期
  - 常态背景 = **真实流体模拟**(简化 stable fluids,借鉴 PavelDoGreat/WebGL-Fluid-Simulation,MIT):**鼠标划过直接搅动色彩**,颜料被卷成烟雾状漩涡;点击空白处迸出一团品牌色 + 涟漪滴落;染料场持续向品牌配色自愈,不会搅成灰色
- 降级链:`prefers-reduced-motion` 直接呈现成品静帧;WebGL/浮点纹理不可用回退到 CSS 光斑背景;上下文丢失自动重建;移动端自动降分辨率
- 测试钩子:URL 加 `?t=秒数` 可冻结开场任意时刻(如 `?t=1.9`)

## 本地预览

```powershell
python -m http.server 5173 --bind 127.0.0.1
```

打开 <http://127.0.0.1:5173/>。也可以直接双击 `index.html`(全部资源内嵌,file:// 也能正常显示)。

## 内容修改

内容全部在 `index.html` 中:

- 项目卡片:搜索 `Projects` 区块,当前为 Vendor Pulse、PolyPilot 和 X Daily Digest
- 技能与数字:搜索 `data-pct`(技能百分比)和 `data-count`(统计数字)
- 联系方式:GitHub 已指向 <https://github.com/DoTrungHuy>

## 仓库范围

远端仓库只保留当前发布所需的 `index.html`、`README.md` 和 `.gitignore`。旧版工程、设计验收素材及本地工具配置仅保留在本机,不纳入提交或部署。
