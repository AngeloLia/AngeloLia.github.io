# WordPress 迁移对照表

- 来源：`WordPress.2025-05-12.xml`（WordPress 6.8.1 导出，2025-05-12，旧站 https://exayktwt.us-east-1.clawcloudrun.com）
- 导出文件共 51 个条目；已发布文章 6 篇，全部导入；其余条目均未导入（见下表）。
- 迁移日期：2026-11-12
- 转换方式：Gutenberg HTML（`<p>`、`<figure><img>`、`<blockquote>`、链接）转为干净 Markdown，正文内容未改写。

## 已导入的文章

| WordPress 标题 | WordPress 日期 | WordPress 状态 | Hugo 文件 | 图片 |
| --- | --- | --- | --- | --- |
| 尝试表达 | 2025-04-24 | 已发布，分类：杂谈 | `content/posts/2025-04-24-chang-shi-biao-da.md` | 无图片 |
| 故事 | 2025-04-26 | 已发布，分类：杂谈 | `content/posts/2025-04-26-gu-shi.md` | 无图片 |
| 音谋笔记（整理） | 2025-05-01 | 已发布，分类：音谋笔记，标签：音谋笔记 | `content/posts/2025-05-01-yin-mou-bi-ji-zheng-li.md` | 无图片 |
| 音乐设备记录 | 2025-05-08 | 已发布，分类：音谋笔记，标签：音谋笔记 | `content/posts/2025-05-08-yin-yue-she-bei-ji-lu.md` | 2 张，未下载（见下） |
| 读书笔记-阿德勒《理解生命》 | 2025-05-10 | 已发布，分类：读书笔记 | `content/posts/2025-05-10-du-shu-bi-ji-a-de-le-li-jie-sheng-ming.md` | 无图片 |
| 白佛山记游 | 2025-05-11 | 已发布，分类：杂谈，标签：游记 | `content/posts/2025-05-11-bai-fo-shan-ji-you.md` | 2 张，未下载（见下） |

每篇导入文章都在头信息里保留了旧站链接别名（`aliases`），例如 `/2025/05/11/白佛山记游/`，旧链接访问时会重定向到新地址。

## 图片状态：未下载

旧站图片主机 `exayktwt.us-east-1.clawcloudrun.com` 在迁移时不可达：2026-11-12 用 curl 测试 `https://exayktwt.us-east-1.clawcloudrun.com/wp-content/uploads/2025/05/img_0228-1.jpg`，15 秒超时，0 字节，curl exit 28。因此**没有下载任何图片**，也没有使用占位图。

4 张被文章引用的图片仍保留原始 URL，待旧站恢复或从本地备份取回后再下载到仓库并替换链接：

| 图片 | 用在哪篇 | 状态 |
| --- | --- | --- |
| `wp-content/uploads/2025/05/img_0179-1-1-1024x982.jpg` | 音乐设备记录 | 未下载，保留原始 URL |
| `wp-content/uploads/2025/05/img_0203-1-1024x768.jpg` | 音乐设备记录 | 未下载，保留原始 URL |
| `wp-content/uploads/2025/05/img_0228-1-768x1024.jpg` | 白佛山记游 | 未下载，保留原始 URL |
| `wp-content/uploads/2025/05/img_0231-1-768x1024.jpg` | 白佛山记游 | 未下载，保留原始 URL |

导出文件中另有 12 个附件条目未被这 6 篇文章引用，也未下载；全站共 23 个不同的图片 URL（含各尺寸变体），均指向同一旧站域名。

## 未导入的内容

| 内容 | 数量 | 处理 |
| --- | --- | --- |
| 回收站文章 | 2 篇（About me、《芒格之道》读书笔记） | 跳过 |
| 回收站页面 | 7 个（示例页面、隐私政策、应许之地、About me、笔记、写点什么、读书） | 跳过 |
| 私密文章《写点什么》（2025-04-29） | 1 篇 | 跳过，未发布 |
| 草稿导航菜单项 | 1 个 | 跳过 |
| 已发布导航菜单项 | 7 个 | 跳过（新站菜单在 `hugo.yaml` 里重建） |
| 附件 | 16 个 | 跳过（见图片状态） |
| `wp_template` / `wp_template_part` / `wp_global_styles` / `wp_navigation` / `custom_css` | 11 个 | 跳过（主题相关，新站用 PaperMod） |

合计：51 个条目中导入 6 篇文章，其余 45 个条目均未导入。
