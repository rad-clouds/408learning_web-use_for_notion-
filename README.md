[README.md](https://github.com/rad-clouds/408learning_web-use_for_notion-/edit/main/README.md)
# 📚 408 考研动态笔记

交互式知识点可视化，每个知识点一个独立 HTML 页面，嵌入 Notion 使用。

## 🎯 设计思路

- **每个知识点 = 一个独立 HTML 文件** → 分别嵌入到 Notion 对应笔记
- **动态交互可视化** → 算法动画、状态变化、步骤演示
- **自包含** → 每个文件完全独立，无外部依赖（CDN 可选）
- **GitHub Pages 部署** → 免费、稳定、HTTPS

## 📂 文件结构

```
408-notes/
├── index.html                    # 导航首页（可选）
├── template.html                 # 创建新知识点的模板
├── red-black-tree.html           # 🌳 红黑树 — 插入/修复/旋转可视化
├── direct-insertion-sort.html    # 📌 直接插入排序 — 逐元素插入动画
├── binary-insertion-sort.html    # 🔍 折半插入排序 — 二分查找+插入动画
└── README.md
```

## 🚀 部署（3 步）

### 1. 创建 GitHub 仓库

新建 **Public** 仓库，如 `408-notes`

### 2. 上传所有 HTML 文件

```bash
git init
git add *.html README.md
git commit -m "408 动态笔记初始化"
git branch -M main
git remote add origin https://github.com/你的用户名/408-notes.git
git push -u origin main
```

### 3. 启用 GitHub Pages

Settings → Pages → Source: `Deploy from a branch` → Branch: `main` → Save

等 1-2 分钟，访问：`https://你的用户名.github.io/408-notes/`

## 📥 嵌入 Notion

在 Notion 页面输入 `/embed`，粘贴对应页面的 URL：

```
https://rad-clouds.github.io/408learning_web-use_for_notion/red-black-tree.html
https://rad-clouds.github.io/408learning_web-use_for_notion/direct-insertion-sort.html
https://rad-clouds.github.io/408learning_web-use_for_notion/binary-insertion-sort.html
```

## ✏️ 添加新知识点

1. 复制 `template.html` → 重命名为 `新知识点.html`
2. 修改页面标题、标签、理论知识区
3. 在 `<script>` 标签中实现算法可视化（参考现有页面）
4. `git push` 自动上线

## 📊 已完成的页面

| 页面 | 交互功能 | 适合章节 |
|------|---------|---------|
| 红黑树 | 插入节点、Case1/2/3可视化、性质检查 | 查找 → 平衡二叉树 |
| 直接插入排序 | 逐帧动画、比较/移动计数、速度调节 | 排序 → 插入排序 |
| 折半插入排序 | 二分查找可视化、L/M/H区间展示 | 排序 → 插入排序 |

## 🎨 每个页面都包含

- 🎮 **交互控制** — 播放/暂停/单步/后退/速度调节
- 📊 **实时统计** — 比较次数、移动次数、节点数等
- 📝 **操作日志** — 每步操作的详细记录
- 📖 **理论知识** — 算法思想、步骤、复杂度、代码
- 🌓 **适配暗色模式** — 浏览器级别支持
- 📱 **响应式** — 手机也能看
