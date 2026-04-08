# Translation Agent Skill

> AI-powered multi-language translation with context awareness

## 功能

- **高质量翻译** - 支持50+语言互译
- **上下文感知** - 根据语境选择最佳译法
- **术语管理** - 行业术语一致性
- **批量翻译** - 文档级批量处理
- **格式保留** - Markdown/HTML/JSON格式保持

## 使用场景

```
用户: 把这份技术文档翻译成英文
Agent: [调用translation skill，保持技术术语和格式]
```

## 工具函数

### `translate(text, source_lang, target_lang, context=None)`

翻译文本。

**参数:**
- `text` (str): 待翻译文本
- `source_lang` (str): 源语言 (zh, en, ja等)
- `target_lang` (str): 目标语言
- `context` (str): 上下文说明

**返回:**
```python
{
    "translation": "Hello World",
    "confidence": 0.98,
    "alternatives": ["Hi World", "Hello Universe"]
}
```

### `translate_document(file_path, target_lang, preserve_format=True)`

翻译文档。

### `batch_translate(texts, target_lang)`

批量翻译。

### `detect_language(text)`

检测语言。

## 配置

```json
{
    "default_provider": "openai",
    "providers": {
        "openai": {
            "model": "gpt-4o",
            "api_key": "${OPENAI_API_KEY}"
        },
        "deepl": {
            "api_key": "${DEEPL_API_KEY}"
        }
    },
    "terminology": {
        "AI": "人工智能",
        "LLM": "大语言模型"
    }
}
```

## 示例

```python
# 翻译句子
result = translate("Hello World", "en", "zh")
# -> "你好世界"

# 翻译文档
translate_document("report.md", "en", preserve_format=True)
```

## 安装

```bash
clawhub install SKY-lv/translation
```

## License

MIT
