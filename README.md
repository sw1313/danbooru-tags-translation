# Danbooru / Yande.re 标签中文翻译库

收录 Danbooru 体系图站（yande.re、konachan 等）标签的中文翻译，供浏览器插件、客户端 App 等项目直接引用。

## 数据概览

| 项目 | 数量 |
|------|------|
| 标签总数 | 184,861 |
| 已翻译 | 184,690 (99.9%) |
| general (一般) | 27,815 |
| artist (画师) | 68,158 |
| copyright (作品) | 13,609 |
| character (角色) | 60,194 |
| circle (社团) | 15,053 |
| meta (元标签) | 32 |

## 文件格式

`tags.json` — JSON 数组，每个元素：

```json
{
  "name": "thighhighs",
  "type": 0,
  "zh": "过膝袜"
}
```

| 字段 | 说明 |
|------|------|
| `name` | 标签英文原名 |
| `type` | 标签类型：`0` 一般、`1` 画师、`3` 版权/作品、`4` 角色、`5` 社团、`6` 元标签 |
| `zh` | 中文翻译（为空字符串表示暂未翻译） |

## 数据来源

- **基础翻译**：[DominikDoom/a1111-sd-webui-tagcomplete](https://github.com/DominikDoom/a1111-sd-webui-tagcomplete/issues/23) 社区贡献的中文翻译
- **标签补全**：通过 yande.re Tag API (`/tag.json?limit=0`) 拉取全站标签，确保覆盖所有在用标签
- **AI 翻译**：未覆盖的标签使用 DeepSeek V3 按标签类型分批翻译
- **人工校对**：部分标签经过手动修正

## 如何使用

### 直接下载

```
https://raw.githubusercontent.com/sw1313/danbooru-tags-translation/main/tags.json
```

### 在代码中引用

```python
import json, urllib.request

url = "https://raw.githubusercontent.com/sw1313/danbooru-tags-translation/main/tags.json"
tags = json.loads(urllib.request.urlopen(url).read())
lookup = {t["name"]: t["zh"] for t in tags if t["zh"]}
print(lookup.get("thighhighs"))  # 过膝袜
```

## 贡献翻译

欢迎通过 Issue 或 Pull Request 提交翻译修正。

## License

公共领域，自由使用。
