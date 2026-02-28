---
name: chinese-to-japanese-translator
description: Translate Chinese text to Japanese. Use this skill whenever the user asks to translate Chinese to Japanese, mentions "日语", "日文", "Japanese translation", or wants to convert Chinese content into Japanese. Also trigger when the user provides Chinese text and asks for translation without specifying the target language but context suggests Japanese.
---

# Chinese to Japanese Translator

Translate Chinese text into natural, accurate Japanese.

## When to Use This Skill

Use this skill when:
- User explicitly asks to translate Chinese to Japanese
- User mentions keywords like "翻译成日语", "日文翻译", "translate to Japanese"
- User provides Chinese text and context suggests they want Japanese translation
- User wants to translate Chinese files (.txt, .md, .docx, etc.) to Japanese

## Translation Principles

**Accuracy First**: Ensure the translation conveys the original meaning accurately. Don't add or omit information.

**Natural Japanese**: Produce Japanese that sounds natural to native speakers, not word-for-word translation. Consider:
- Appropriate use of particles (は、が、を、に、で、etc.)
- Natural sentence structure (Japanese SOV vs Chinese SVO)
- Idiomatic expressions that match the Chinese intent
- Cultural context and nuance

**Tone and Formality**:
- Default to polite form (です・ます体) for general content
- Use casual form (だ・である体) for informal contexts like personal messages or casual conversation
- Match the formality level of the source text
- For business documents, use appropriate keigo (敬語) where needed

**Proper Nouns**:
- Keep personal names in original Chinese characters when they're also used in Japanese
- Add katakana reading for Chinese names if helpful for pronunciation
- Use standard Japanese names for well-known places (北京 → 東京 for Beijing, etc.)
- Keep company names and brand names as they officially appear in Japanese market

## Output Format

Present translations in a clear, easy-to-review format:

**For short text (1-3 sentences):**
```
【原文】
[Original Chinese text]

【日本語訳】
[Japanese translation]
```

**For longer text:**
```
【原文】
[Original Chinese text - first paragraph]

【日本語訳】
[Japanese translation - first paragraph]

---

【原文】
[Original Chinese text - second paragraph]

【日本語訳】
[Japanese translation - second paragraph]

[Continue for remaining paragraphs...]
```

**For files:**
- Create a new file with suffix `_ja` (e.g., `document.txt` → `document_ja.txt`)
- Maintain the original formatting, structure, and markdown/formatting tags
- Add a header comment indicating it's a translation

## Special Cases

**Technical Terms**:
- Use standard Japanese technical vocabulary where it exists (计算机 → コンピュータ)
- Keep English technical terms in English when that's standard in Japanese (API, HTML, etc.)
- Add explanations in parentheses for uncommon specialized terms if needed

**Numbers and Units**:
- Keep Arabic numerals (1, 2, 3) for most numbers
- Use appropriate Japanese counters (個、枚、本、etc.)
- Convert units if needed (市斤 → キログラム), noting the conversion

**Mixed Content**:
- Preserve English words/phrases that appear in the Chinese text
- Keep URLs, code snippets, and technical identifiers unchanged
- Maintain formatting like bullet points, headings, and emphasis

## Quality Checklist

Before presenting the translation, verify:
- [ ] Meaning is accurately preserved
- [ ] Japanese grammar is correct
- [ ] Formality level is appropriate
- [ ] Proper nouns are handled correctly
- [ ] No Chinese characters remain that should be converted (unless intentionally kept)
- [ ] Particles and verb forms are natural
- [ ] Reading flows smoothly in Japanese

## Examples

**Example 1 - Simple Sentence:**
```
【原文】
今天天气很好，我们去公园散步吧。

【日本語訳】
今日はとてもいい天気ですね。公園に散歩に行きましょう。
```

**Example 2 - Business Context:**
```
【原文】
感谢您对我们产品的关注。我们将在三个工作日内回复您的询问。

【日本語訳】
弊社製品にご関心をお寄せいただき、誠にありがとうございます。お問い合わせにつきましては、3営業日以内にご返信申し上げます。
```

**Example 3 - Technical Content:**
```
【原文】
这个API支持JSON格式的数据传输，最大文件大小为10MB。

【日本語訳】
このAPIはJSON形式のデータ転送に対応しており、最大ファイルサイズは10MBです。
```

## Notes

- If the source text quality is poor (typos, unclear meaning), note this and provide the best possible translation
- If multiple interpretations are possible, choose the most likely one based on context, or ask the user for clarification
- For very long texts (>500 words), consider asking if the user wants the full translation or a summary
- If the user requests specific terminology or style preferences, prioritize those over the defaults
