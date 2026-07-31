# Travel-Stories 工作流 · 中英双语文章发布流程

## 目录结构

```
Travel-Stories/
├── README.md                    # 项目主页，列所有文章链接
├── _archived-obsidian-source/   # Obsidian 英文源文件备份（用完即移出 Obsidian）
└── essays/
    └── NN-slug/                 # 每篇文章一个目录
        ├── index.zh.md          # 中文版
        ├── index.en.md          # 英文版
        └── images/              # 图片（按文章出现顺序编号）
            ├── 001.jpg
            ├── 002.gif
            └── ...
```

## 新增一篇文章的步骤

### 前置条件
- 中文版：微信文章已通过 WeChat-Article-Archive 导出到 `50-平台导出/微信/WeChat-Article-Archive/justgo/articles/`
- 英文版：Medium 上已发布，或 Obsidian 中有英文草稿

### 步骤

1. **找对应**
   - 在微信存档中找到中文版 `article.md` 和 `images/` 目录
   - 匹配对应的英文版（Medium 或 Obsidian 草稿）

2. **创建目录**
   ```bash
   mkdir -p essays/NN-slug/images
   ```
   - `NN` 为递增编号（01, 02, 03...）
   - `slug` 为英文短标识（如 `london-24-hours`）

3. **复制图片**（从微信存档的 images/ 目录）
   ```bash
   cp "微信存档路径/images/*" "essays/NN-slug/images/"
   ```

4. **写中文版 `index.zh.md`**
   - 标题格式：`# 中文标题`
   - 第二行：`*Geng Yue · Travel Stories*`
   - 图片引用改为 `![描述](images/XXX.ext)`
   - 删除微信尾部（预告、二维码、ABOUT YUE 等）

5. **写英文版 `index.en.md`**
   - 标题格式：`# English Title`
   - 第二行：`*Geng Yue · Travel Stories*`
   - 图片引用与中文版一一对应
   - 英文来源：Medium 原文（朋友手工翻译）或自行翻译

6. **更新 README.md**
   - 在表格中新增一行

7. **清理**
   - 如有 Obsidian 英文草稿，复制到 `_archived-obsidian-source/` 备份后，从 Obsidian 删除原文件
   - 图片不使用 Obsidian 存储（太大）

## 文章命名规范

| 项目 | 规范 | 示例 |
|------|------|------|
| 目录名 | 全小写英文+连字符 | `03-gypsy-in-my-soul` |
| 中文文件 | `index.zh.md` | 固定 |
| 英文文件 | `index.en.md` | 固定 |
| 图片 | 三位数字编号，保留原始扩展名 | `001.jpg`, `002.gif` |

## 约束

- 单张图片 ≤ 25MB（GitHub 限制），超过需压缩
- 不含 `.DS_Store` 等系统缓存文件
- 中文版不保留微信尾部（预告/二维码/ABOUT YUE 等营销内容）
- 英文版保留朋友手工翻译的原文风味，不做机器翻译式改写

## 已发布文章清单

| # | Slug | 中文标题 | 日期 |
|---|------|---------|------|
| 01 | the-right-clothes | 穿对了衣服，旅行照片想不美都难 | 2018-06-18 |
| 02 | the-right-dress | 穿对了裙子，旅行照片想不美都难 | 2018-06-23 |
| 03 | gypsy-in-my-soul | 我的灵魂里有一个吉普赛人 | 2017-06-23 |
| 04 | old-shanghai | 老灵额里弄时光，住进不一样的上海 | 2018-04-16 |
| 05 | london-24-hours | 伦敦24小时清单 · 英伦韵味 | 2016-01-04 |
| 06 | overtime-daydreams | 我在加班深夜里的每一个白日梦 | 2017-02-25 |
| 07 | truffle-hunters-florence | 美食 · 和松露猎人穿越佛罗伦萨 | 2017-05-23 |