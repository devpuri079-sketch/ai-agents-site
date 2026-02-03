---
title: AIエージェント環境構築
type: docs
prev: docs/aiagent
next: docs/aiagent/ai-agent-agno-chatapp
weight: 1
---

## 仮想環境作成
```bash
python -m venv .venv_ai  
.\.venv_ai\Scripts\activate   
```

## GeminiAPIの使用

python ライブラリ
``` bash
pip install python-dotenv
pip install -q -U google-genai
```

[サンプルコート参考サイト](https://ai.google.dev/gemini-api/docs/quickstart?hl=ja)

.envファイル用意
apiキーの取得方法はこちら
[Gemini API取得手順]({{< relref "../gemini-setup/gemini-setup" >}})
```
GEMINI_API_KEY=*your_api_key*
```

```python
from dotenv import load_dotenv
from google import genai

load_dotenv()

# The client gets the API key from the environment variable `GEMINI_API_KEY`.
client = genai.Client()

response = client.models.generate_content(
	model="gemini-2.5-flash", contents="日本における京都の価値は？"
)
print(response.text)

```
