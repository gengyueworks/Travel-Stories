# Travel-Stories 工作流 · 中英双语文章发布流程

## 目录结构

```
Travel-Stories/
├── README.md                    # 项目主页，按专题列所有文章链接
├── collaborations/              # 品牌合作
│   └── airbnb/                  # Airbnb 合作专题
│       └── slug/                # 每篇文章一个目录
│           ├── index.zh.md
│           ├── index.en.md
│           └── images/
├── guides/                      # 旅行攻略专题（24h/72h 城市清单等）
│   └── slug/
│       ├── index.zh.md
│       ├── index.en.md
│       └── images/
└── stories/                     # 旅行故事专题（默认分类）
    └── slug/
        ├── index.zh.md
        ├── index.en.md
        └── images/              # 图片（按文章出现顺序编号）
            ├── 001.jpg
            ├── 002.gif
            └── ...
```

## 命名规范（重要）

- **目录名禁止加序号**（不要写 `01-slug`、`02-slug`）。文章还会持续上传，加序号会导致后续排序混乱。
- `slug` 为英文短标识，全小写+连字符（如 `london-24-hours`）。
- 中文文件固定为 `index.zh.md`，英文文件固定为 `index.en.md`。
- 图片三位数字编号，保留原始扩展名（`001.jpg`, `002.gif`）。

## 专题分类规则

| 专题 | 目录 | 放入条件 |
|------|------|---------|
| Airbnb 合作 | `collaborations/airbnb/` | 与 Airbnb 合作的文章（住宿体验、民宿合作、Airbnb 官方号发布文），已有 12 篇（上海弄堂、重庆、布拉格、佛罗伦萨、巴黎、旧金山、维也纳、冲绳、民宿清单、杭州、北京、布拉格船屋） |
| 旅行攻略 | `guides/` | 城市清单、24h/72h 攻略等实用向文章，如伦敦24小时、普吉岛72小时 |
| 旅行故事 | `stories/` | 默认分类，其余所有旅行故事 |

新增专题时（如奢华酒店合作），在 `collaborations/` 下新建对应子目录即可。

## 新增一篇文章的步骤

### 前置条件
- 中文版：微信文章已通过 WeChat-Article-Archive 导出到 `50-平台导出/微信/WeChat-Article-Archive/justgo/articles/`
- 英文版：Medium 上已发布，或 Obsidian 中有英文草稿

### 步骤

1. **找对应**
   - 在微信存档中找到中文版 `article.md` 和 `images/` 目录
   - 匹配对应的英文版（Medium 或 Obsidian 草稿）

2. **判断专题**：按上方规则确定放 `collaborations/airbnb/`、`guides/` 还是 `stories/`

3. **创建目录**（无序号）
   ```bash
   mkdir -p <专题>/<slug>/images
   ```
   - `slug` 为英文短标识（如 `london-24-hours`）

4. **复制图片**（从微信存档的 images/ 目录）
   ```bash
   cp "微信存档路径/images/*" "<专题>/<slug>/images/"
   ```

5. **写中文版 `index.zh.md`**
   - 标题格式：`# 中文标题`
   - 第二行：`*Geng Yue · Travel Stories*`
   - 图片引用改为 `![描述](images/XXX.ext)`
   - 删除微信尾部（预告、二维码、ABOUT YUE 等）

6. **写英文版 `index.en.md`**
   - 标题格式：`# English Title`
   - 第二行：`*Geng Yue · Travel Stories*`
   - 图片引用与中文版一一对应
   - 英文来源：Medium 原文（朋友手工翻译）或自行翻译

7. **更新 README.md**
   - 在对应专题的表格中新增一行

## 约束

- 单张图片 ≤ 25MB（GitHub 限制），超过需压缩
- 不含 `.DS_Store` 等系统缓存文件
- 中文版不保留微信尾部（预告/二维码/ABOUT YUE 等营销内容）
- 英文版保留朋友手工翻译的原文风味，不做机器翻译式改写

## 已发布文章清单

> README.md 是唯一权威清单，按专题更新，不再在本文档维护表格。
