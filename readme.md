# GOOGLE工具：上线后 SEO 发布与 Google AdSense 接入指南

当前线上地址：https://json-gamma-three.vercel.app/

## 你现在已经完成了什么

- 已部署上线（Vercel）
- 已配置基础 SEO（title/description/keywords、Open Graph、JSON-LD）
- 已生成并上线必要文件（robots.txt、sitemap.xml、ads.txt）
- 已添加隐私政策与使用条款页面
- 页面已预留广告位，并支持响应式广告脚本加载

## 1. 上线后 SEO 发布（必须做）

### 1.1 自检：这些地址必须能在公网直接打开

- https://json-gamma-three.vercel.app/
- https://json-gamma-three.vercel.app/robots.txt
- https://json-gamma-three.vercel.app/sitemap.xml
- https://json-gamma-three.vercel.app/privacy.html
- https://json-gamma-three.vercel.app/terms.html

如果任意一个打不开，先修复再做下一步（Search Console/AdSense 都依赖这些页面可访问）。

### 1.2 Google Search Console 提交收录

1. 打开 Google Search Console → 添加资源
2. **选择资源类型（目前推荐）：**

   - **右侧：网址前缀 (URL prefix)**
     - **怎么写**：必须带协议 `https://json-gamma-three.vercel.app/`
     - **优点**：支持 HTML 标记验证，秒级生效。

3. **获取验证码并填入：**
   - 如果选了「网址前缀」，请复制形如 `<meta name="google-site-verification" content="XXXXXXXXX" />` 的代码。
   - 目前已填入：`bOrXy7_sYc-b0dgPdr3660uuyFYofkg1DekzWHlx-LA`。
4. 部署代码后，点击「验证」。
5. 进入「站点地图」提交：
   - `https://json-gamma-three.vercel.app/sitemap.xml`
6. 进入「网址检查」输入：
   - `https://json-gamma-three.vercel.app/`
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
- 确保部署成功后，访问 `https://json-gamma-three.vercel.app/` 确认页面正常加载。

### 3.2 Google Search Console 验证
- 在 GSC 后台输入 `https://json-gamma-three.vercel.app/`。
- 点击 **「验证」**。
- 验证通过后，在 **「站点地图」** 菜单提交 `https://json-gamma-three.vercel.app/sitemap.xml`。

### 3.3 Google AdSense 站点审核（详细流程）

1. **添加站点**：
   - 登录 [Google AdSense](https://adsense.google.com/)。
   - 点击左侧菜单 **「站点 (Sites)」** -> **「新建站点 (New site)」**。
   - 输入域名：`json-gamma-three.vercel.app`。
2. **确认验证**：
   - 系统会询问你如何验证。由于我们已经在 `<head>` 中加入了 `google-adsense-account` 标签，你可以直接选择 **「已放置代码」** 或 **「通过 Meta 标签验证」**。
3. **点击申请审核**：
   - 按照页面提示，点击最后的 **「申请审核 (Request review)」** 按钮。
4. **审核要点（提高通过率）**：
   - **内容充实度**：确保首页有足够的文字描述（目前的工具说明、FAQ 已提供基础内容）。
   - **合规页面**：必须有「隐私政策」和「使用条款」链接（项目中已包含且已更新链接）。
   - **广告位显示**：审核通过前，代码中预留的广告位（顶部、侧边栏、底部）会显示为空白，这是正常现象，不要删除代码。
   - **审核周期**：通常需要 **3 到 14 天**，请耐心等待邮件通知。

## 4. 如何查看收益与账号状态

配置完成后，你可以通过以下方式监控你的 AdSense 账号：

### 4.1 确认广告是否开始展示
- **审核中**：在 AdSense 后台显示 "Getting ready" 期间，网站上的广告位会显示为空白。
- **审核通过**：你会收到 Google 的邮件通知，此时访问网站，你应该能看到真实的广告内容。
- **实时检查**：在 AdSense 后台点击 **「报告 (Reports)」** -> **「广告单元 (Ad units)」**，查看是否有“展示次数 (Impressions)”。

### 4.2 查看收入数据
1. **首页概览 (Home)**：
   - **Estimated earnings (预估收入)**：显示今天、昨天、本月至今的收入。
   - **Balance (余额)**：显示已结算的金额（通常每月 3 号更新上月结算金额）。
2. **性能指标 (Performance)**：
   - **Page views (页面浏览量)**：有多少人看了你的工具。
   - **Clicks (点击次数)**：有多少人点击了广告（这是主要收入来源）。
   - **CPC (单次点击价格)**：平均每次点击你赚多少钱。
   - **Page RPM (每千次展示收入)**：衡量网站变现效率的关键指标。

### 4.3 关键阈值（收钱流程）
- **$10 (验证身份)**：当你的收入达到 10 美元时，Google 会寄一封包含 **PIN 码** 的纸质信件到你的地址，用于验证。
- **$100 (付款起付金额)**：当你的余额达到 100 美元时，Google 会在下个月的 21-26 号左右通过电汇将钱打入你的银行卡。

### 4.4 浏览量与收入估算 (Page RPM)
这是一个非常实际的问题。在 Google AdSense 中，浏览量（Page Views）和收入（Earnings）之间的关系通常用 **Page RPM（每千次展示收入）** 来衡量。

对于一个像你这样的 **JSON 工具类网站**，收入主要受以下几个因素影响：

**1. 估算公式**
平均而言，工具类网站的 Page RPM 通常在 **$1 - $5** 之间（取决于用户来自哪里）。
- **如果你的用户主要来自中国：**
  - Page RPM 大约在 **$0.5 - $2**。
  - 也就是说：**1,000 次浏览 ≈ 3.5 - 14 元人民币**。
- **如果你的用户主要来自美国/欧洲：**
  - Page RPM 大约在 **$5 - $15**。
  - 也就是说：**1,000 次浏览 ≈ 35 - 100 元人民币**。

**2. 钱是怎么算的？（两个来源）**
- **展示次数 (Impressions)**：只要用户看到广告，你就有一点点钱（非常少）。
- **点击次数 (Clicks)**：这是大头。一次点击可能价值 **$0.1 - $1.0**。
  - 如果 1,000 个人里有 10 个人点了广告（点击率 1%），你就赚了约 $1 - $10。

**3. 为什么工具类网站赚钱？**
- **重复使用率高**：程序员每天都要格式化 JSON，这会带来稳定的流量。
- **广告匹配度高**：Google 会给你的用户展示云服务器（AWS/阿里云）、编程课程、开发工具等高价值广告，这些广告的点击单价（CPC）通常比较高。

**4. 如何赚得更多？**
- **增加广告位**：我已经帮你配置了 **顶部、侧边栏、底部** 3 个广告位，这能最大化你的展示量。
- **吸引海外流量**：如果你的工具支持英文界面，吸引美国用户，收入会翻 5-10 倍。
- **增加新工具**：页面越多，被搜索到的概率越大，总浏览量就越高。

---

**总结：你的收入小目标**
- **初期**：每天 100 人访问，一个月可能只有几块钱（买个冰激凌）。
- **中期**：每天 1,000 人访问，一个月能赚 **150 - 500 元**（够付服务器和域名费了）。
- **后期**：每天 10,000 人访问，一个月能赚 **1,500 - 5,000 元**（甚至更多，这已经是一份不错的副业收入了）。

现在的关键就是：多上线实用的工具，把流量做起来！

---

## 5. 后续维护与新工具上线指南

### 5.1 上线新工具（无需再次审核）
Google AdSense 是**按域名审核**的。只要你的 `json-gamma-three.vercel.app` 通过了审核，后续添加新页面（如 `/xml-to-json`）只需执行以下操作：
1. **复用代码**：直接复制首页的广告位 HTML 和 `<script>` 标签。
2. **更新 Sitemap**：在 `sitemap.xml` 中加入新链接。
3. **无需申请**：新工具会自动显示广告并开始计费。

### 5.2 维护建议
- **不要点击自己的广告**：这是被封号的最常见原因，Google 的反作弊系统非常严格。
- **保持内容合规**：不要上线含有版权争议或违规内容的工具。
- **更换域名**：当 `jsonchanger.com` 调通后，需同步更新 `index.html` 的 canonical/og:url、`robots.txt`、`sitemap.xml`。

