# GOOGLE工具：上线后 SEO 发布与 Google AdSense 接入指南

当前线上地址：https://jsonchanger.com/

## 你现在已经完成了什么

- 已部署上线（Vercel）
- 已配置基础 SEO（title/description/keywords、Open Graph、JSON-LD）
- 已生成并上线必要文件（robots.txt、sitemap.xml、ads.txt）
- 已添加隐私政策与使用条款页面
- 页面已预留广告位，并支持响应式广告脚本加载

## 1. 上线后 SEO 发布（必须做）

### 1.1 自检：这些地址必须能在公网直接打开

- https://jsonchanger.com/
- https://jsonchanger.com/robots.txt
- https://jsonchanger.com/sitemap.xml
- https://jsonchanger.com/privacy.html
- https://jsonchanger.com/terms.html

如果任意一个打不开，先修复再做下一步（Search Console/AdSense 都依赖这些页面可访问）。

### 1.2 Google Search Console 提交收录

1. 打开 Google Search Console → 添加资源
2. **选择资源类型（根据你的需求填写）：**

   - **左侧：网域 (Domain)**
     - **怎么写**：只填根域名 `jsonchanger.com`（不要带 `https://`，不要带 `/`）
     - **优点**：一次验证即可覆盖所有子域名（www, m. 等）和 http/https。
     - **验证**：**必须**去域名商那里添加 DNS TXT 记录（生效较慢）。

   - **右侧：网址前缀 (URL prefix)** —— **【推荐现在使用】**
     - **怎么写**：必须带协议 `https://jsonchanger.com/`（建议以 `/` 结尾）
     - **优点**：支持多种验证方式，**HTML 标签验证**通常秒级生效。
     - **验证**：选择「HTML 标记」，获取代码填入 `index.html`。

3. **获取验证码并填入：**
   - 如果选了「网址前缀」，请复制形如 `<meta name="google-site-verification" content="XXXXXXXXX" />` 的代码。
   - 将代码发送给 AI，或直接粘贴到 `index.html` 的第 23 行。
4. 部署代码后，点击「验证」。
5. 进入「站点地图」提交：
   - `https://jsonchanger.com/sitemap.xml`
6. 进入「网址检查」输入：
   - `https://jsonchanger.com/`
   - 点「请求编入索引」

## 2. Google AdSense 接入（已完成配置）

目前项目中已成功配置了你的 AdSense 信息，包括 3 个广告位：**顶部、侧边栏、底部**。

### 已配置的关键信息：
- **发布商 ID (Publisher ID)**: `pub-8564695674329026`
- **广告位 ID (Ad Slot IDs)**:
  - 顶部 (Top): `1577431502`
  - 侧边栏 (Sidebar): `8114919696`
  - 底部 (Bottom): `7805996182`

### 已自动更新的文件：
1. **index.html**: 填入了 `ca-pub-8564695674329026` 和对应的广告位 ID。
2. **ads.txt**: 更新了授权记录，确保广告投放合法。

---

## 3. 最后上线步骤（重要）

完成上述代码修改后，请务必执行以下操作：

### 3.1 推送代码并部署
- 将当前修改提交并推送至 GitHub/Vercel。
- 确保部署成功后，访问 `https://jsonchanger.com/` 确认页面正常加载。

### 3.2 Google Search Console 验证
- 在 GSC 后台点击 **「验证」**。
- 验证通过后，在 **「站点地图」** 菜单提交 `https://jsonchanger.com/sitemap.xml`。

### 3.3 Google AdSense 站点审核
- 登录 [Google AdSense](https://adsense.google.com/)。
- 进入 **「站点」** 菜单，选择 `jsonchanger.com`。
- 点击 **「申请审核」**。
- **注意**：审核通常需要 3-14 天。在审核通过前，广告位会显示为空白。

---

## 4. 后续维护指南

- **更换域名**：需同步更新 `index.html` 的 canonical/og:url、`robots.txt`、`sitemap.xml`。
- **添加新工具**：建议在 `index.html` 中保持一致的 UI 风格和广告位布局。

