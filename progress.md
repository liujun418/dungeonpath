# 开发日志

## Session 1 — 2026-05-08

### 项目启动
- 阅读需求分析文档 `dungeonpath需求分析.md`
- 确认用户需求：Hugo + PaperMod + GitHub + Vercel 部署
- 用户反馈：Hugo 不熟悉、内容需 AI 生成、域名已购、无截图

### 关键讨论
1. **游戏选择**：确认 Fisch + Pressure 为 P0，Doors 降为 P2，RIVALS 加入 P1 候选
2. **内容策略**：混合策略（新手攻略长文 + 专题短文）
3. **Google 风险**：三源交叉验证（AI 数据 + 游戏验证 + 社区来源）
4. **内容结构**：单篇长文 + 内部链接，不做 Tab 切换

### 环境检查
- Hugo v0.161.1 extended ✅
- Git 2.54.0 ✅
- Node.js v25.2.1 ✅
- GitHub CLI 未登录 ❌（用户后完成 `gh auth login`）

### 市场研究
- Roblox 各梯队游戏数据分析（详见 findings.md）
- Pressure 3月2026大更新确认
- Doors 4月2026新内容确认

---

## Session 2 — 2026-05-09

### Phase 1: 环境准备与项目初始化 ✅

- [x] GitHub CLI 已登录 `liujun418`
- [x] 仓库 `liujun418/dungeonpath` 已存在，直接初始化
- [x] Hugo 项目初始化（`hugo new site`）
- [x] PaperMod 主题添加（git submodule，commit c4ca7ca）
- [x] hugo.yaml 配置完成：
  - 站点信息（baseURL、title、description）
  - 导航菜单（Guides、Categories、Search、About）
  - SEO 关键词
  - Profile Mode 首页
  - Social Icons
  - 自定义 CSS
- [x] 自定义 CSS（`assets/css/custom.css`）
- [x] 解决配置问题：
  - 删除了冲突的 `hugo.toml`
  - 合并了重复的 `params` 块
  - 移除了无效的 `Search` output 格式
  - 修复弃用的 `languageName` → `label`

### Phase 2: 站点结构搭建 ✅

- [x] 创建内容目录：`content/posts/fisch/`、`content/posts/pressure/`
- [x] 创建 About 页面
- [x] 创建 Search 页面（PaperMod 内置布局）
- [x] 创建 Archives 页面（PaperMod 内置布局）
- [x] URL 结构规划确认：`/posts/游戏名/主题/`
- [x] 创建占位攻略内容：
  - Fisch Beginner Guide
  - Pressure Beginner Guide
- [x] Hugo 本地构建成功（33 pages，71ms）
- [x] 本地服务正常，首页渲染正确

### Phase 6: GitHub 推送 ✅

- [x] 配置 git user identity
- [x] 初始提交：10 文件
- [x] 推送到 `origin/master`
- [x] GitHub 仓库：https://github.com/liujun418/dungeonpath

---

## Session 3 — 2026-05-09

### Phase 5 + 6: 部署上线 ✅

- [x] 添加 vercel.json（Hugo 框架配置）
- [x] 设置 HUGO_VERSION=0.161.1 环境变量
- [x] Vercel 部署成功，Hugo 构建 33 pages
- [x] dungeonpath.com 域名绑定完成
- [x] SSL 证书生效
- [x] 线上验证：
  - https://dungeonpath.com/ → 200 OK
  - /posts/fisch/beginner-guide/ → 正常
  - /posts/pressure/beginner-guide/ → 正常
  - /posts/ → 正常

---

## Session 4 — 2026-05-09

### Neon Gaming 视觉重设计 ✅

- [x] Google Fonts（Orbitron + Inter）引入
- [x] 全局暗色主题 CSS 变量体系
- [x] 导航栏：深色背景 + 模糊 + 渐变底边 + Orbitron 霓虹 Logo
- [x] 首页：Orbitron 渐变标题 + 渐变按钮 + 分割线
- [x] 攻略卡片：深色背景 + hover 发光 + 紫色标签
- [x] 文章内页：紫色链接 + TOC 紫边 + 表格/引用样式
- [x] 搜索页：暗色输入框 + 紫色聚焦
- [x] 标签/归档页：霓虹风格
- [x] 页脚：暗色 + 渐变分割线
- [x] 移动端适配（标题缩放）
- [x] 生产构建 + Vercel 部署

---

## Session 5 — 2026-05-09

### Phase 3: Fisch 内容 ✅

- [x] Fisch Beginner Guide（重写，3,071 字，10 表格）
- [x] Fisch Best Rods Tier List（2,532 字，14 表格）
- [x] Fisch Fish Location Map（2,320 字，8 个主要地点）

### Phase 4: Pressure 内容 ✅

- [x] Pressure Beginner Guide（重写，2,425 字，13 表格）
- [x] Pressure Entities Guide（complete bestiary with survival strategies）

---

## Session 6 — 2026-05-09

### RIVALS 内容 ✅

- [x] RIVALS Beginner Guide — comprehensive new player walkthrough
- [x] RIVALS Weapon Tier List — all weapons ranked for Season 3

### Sailor Piece 内容 ✅

- [x] Sailor Piece Beginner Guide — comprehensive new player walkthrough

### DOORS 内容 ✅

- [x] DOORS Beginner Guide — Hotel, Mines, Rush Mode walkthrough

---

## 站点总览

### 已发布页面（80 pages）

| 游戏 | 页面 | URL |
|------|------|-----|
| **Fisch** | Beginner Guide | `/posts/fisch/beginner-guide/` |
| | Best Rods Tier List | `/posts/fisch/best-rods-tier-list/` |
| | Fish Location Map | `/posts/fisch/fish-location-map/` |
| **Pressure** | Beginner Guide | `/posts/pressure/beginner-guide/` |
| | Entities Guide | `/posts/pressure/entities-guide/` |
| **RIVALS** | Beginner Guide | `/posts/rivals/beginner-guide/` |
| | Weapon Tier List | `/posts/rivals/weapon-tier-list/` |
| **Sailor Piece** | Beginner Guide | `/posts/sailor-piece/beginner-guide/` |
| **DOORS** | Beginner Guide | `/posts/doors/beginner-guide/` |

### 待办

- [ ] Phase 7: SEO 基础设置（Google Search Console, sitemap, robots.txt）
- [ ] 更多游戏内容（根据搜索量决定优先级）
- [ ] 用户验证内容准确性

---

## Session 7 — 2026-05-10

### Google AdSense 合规 + 法律声明 ✅

- [x] 创建 Privacy Policy（Google AdSense、Analytics、Cookie 声明）
- [x] 创建 Terms of Service（内容免责声明、版权声明、责任限制）
- [x] 创建 Ad Disclosure（广告透明度声明、用户选择权）
- [x] 页脚添加法律页面链接（Hugo footer menu）
- [x] 删除 GitHub 地址（首页 socialIcons、About 页面）
- [x] 联系方式更新为 jzerov@live.com

### 导航栏修复 ✅

- [x] 修复导航文字太靠顶部（padding + flex 垂直居中）

---

## Session 8 — 2026-05-10

### 新分类扩展：Mobile Games + PC Games ✅

根据 `game.md` 市场分析策略，从"只有一个 Roblox Guides 分类"扩展到三个内容分类：

#### Monster Legends（Mobile Games）✅
- [x] Beginner Guide — 核心机制、前期优先级、常见错误
- [x] Breeding Guide — 所有传说/神话怪物繁殖配方，元素对照表
- [x] Monster Tier List — S-D Tier PvP/War/Adventure 排名
- [x] Gold and Food Farming Guide — 金币/食物最佳农场节点
- [x] Events and Dungeons Guide — Maze/Race/Puzzle/Team Dungeon 全攻略
- [x] Battle Strategy Guide — 回合制战斗、队伍构建、状态效果连招
- [x] Island and Habitat Layout Guide — 12 岛屿解锁顺序、栖息地布局优化
- [x] Codes and Rewards Guide — 全部可用兑换码、每日奖励、F2P 宝石获取

#### My Singing Monsters（Mobile Games）✅
- [x] Beginner Guide — 岛屿系统、货币、升级、前期优先事项
- [x] Breeding Guide — 各岛繁殖组合、Ethereal/Seasonal/Rare 繁殖规则
- [x] Rare and Epic Monsters Guide — 稀有/史诗怪物繁殖窗口与收集策略
- [x] Wublin Island Guide — Wublin 激活机制、全部 20 种 Wublin、Zynth 农场法
- [x] Seasonal Events Guide — 6 大季节性活动（Spooktacle, Festival of Yay 等）
- [x] Gold and Diamond Farming Guide — 金币/钻石/碎片/点心优化
- [x] Shugabush Island Guide — Shugabush 家族全成员繁殖、歌曲完成
- [x] Ethereal Island Guide — 5 种 Ethereal 繁殖、传送成本、碎片生产

#### Palworld（PC Games）✅
- [x] Beginner Guide — 生存基础、首批 Pal、基地建设、科技树
- [x] Pal Locations Guide — 全生物群系 Pal 分布、稀有刷新、Alpha Pal 位置
- [x] Best Pals Tier List — 战斗/坐骑/工作 S-C Tier 排名
- [x] Breeding Guide — 繁殖机制、蛋糕生产线、Anubis/Frostallion 等繁殖配方
- [x] Base Building Guide — 基地位置排名、15 Pal 阵容、自动化布局
- [x] Boss and Tower Guide — 5 塔主、4 传说 Pal、Alpha 首领攻略
- [x] Resources and Materials Guide — 全部资源类型、最佳农场路线
- [x] Technology and Progression Guide — 1-50 级逐级解锁优先事项

#### Lethal Company（PC Games）✅
- [x] Beginner Guide — 核心玩法循环、扫描仪、终端基础、常见错误
- [x] Moon Guide — 全部 8 卫星（Experimentation 到 Titan）难度/收益分析
- [x] Monster Bestiary — 全部实体（Bracken, Coil-Head, Jester 等）行为与对策
- [x] Equipment Guide — 商店物品成本/价值分析、队伍装备分配
- [x] Advanced Strategies Guide — 配额数学、恶劣天气、晚局战术
- [x] Co-op Team Roles Guide — 4 人角色（Ship Operator/Scout/Hauler/Support）
- [x] Scrap and Loot Guide — 全部废料物品、价值与重量、背包优化
- [x] Terminal Commands Guide — 完整终端命令参考、隐藏命令

### 站点总览更新

| 指标 | 变化 |
|------|------|
| 内容文件 | 61 → 93 (+32) |
| 游戏覆盖 | 8 → 12 (+4) |
| 分类 | 1 (Roblox Guides) → 3 (+Mobile Games, +PC Games) |
| Hugo 构建 | 80 pages → 517 pages |
