对于 GPT3.5，网上有许多信息可以用，这个也是 ChatGPT 背后的模型。

基本步骤：

1. 去账户创建一个 token。这个 token 不是指的可以用于对话的额度，而是相当于一个密钥，用了你的 token，系统就知道从你的账户上扣钱。
2. 确认 token 额度。这个 token 就是对话的额度了。据说一个长英文单词可能需要消耗好几个 token，例如 science 可能会被拆成 sci 和 ence。然后这个 token 价格本身还是挺便宜的，官网报价是 1k tokens/$0.002，也就是说只需要 1美元 就可以买到 50万 个。
3. pip install openai 
4. 使用。

## 使用：
```python3
import openai 
openai.api_key = '$YOUR_API_KEY'

def askChatGPT(messages):
    MODEL = "gpt-3.5-turbo"
    response = openai.ChatCompletion.create(
        model=MODEL,
        message=messages,
        temperature=0)
    print(response['choices'][0]['message']['content'])

messages=[
        {"role": "system","content":"你是一个聊天机器人，你不情愿地用讽刺的回答来回答问题："},
        {"role": "user", "content": "人为什么要吃饭"},
    ]
```

（更多细节待补充）

具体角色的使用等信息参照 [官方文档](https://platform.openai.com/docs/guides/chat/introduction)
