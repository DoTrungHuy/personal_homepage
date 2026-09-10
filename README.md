# Trung Huy — Personal Digital Garden

东方水墨风格的个人数字花园，展示 Agent 工具、自动化项目、交互视觉与技术文章。

## Production

- Website: <https://zzk.trunghuy.top>
- Hosting: Cloudflare Workers
- Release branch: `main`
- Output: Astro static HTML, CSS and JavaScript with Pagefind search assets

生产站点由 Cloudflare 监听 `main` 分支并发布仓库根目录。根目录内容是经过类型检查、浏览器测试和生产构建后的静态发布产物。

## Experience

- 3.6 秒水墨 Z 开场，支持跳过与菜单重播
- CSS、SVG、Canvas 与 GSAP 组成的四段程序化背景
- 五个精选项目在同一视口位置逐张覆盖
- 深浅主题、触屏、键盘与 `prefers-reduced-motion` 支持
- 项目详情、搜索索引、RSS 与站点地图

## Release verification

发布前在本地 Astro 工程中执行：

```powershell
npm run check
npm run build
npm test
```

Cloudflare 构建通过后，再验证首页、`/_astro/` 资源、项目详情和站点地图均能从正式域名访问。
