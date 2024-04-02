this docs is for what changes i made

Added GPT 4 in FlowGPT

Fix Liaobots to use same format as others and system meSsage fix

fix deepinfra to support json format as output format

some free best models you can use without selenium , edit:-> some deepinfra not working fix soon

```json

    "DeepInfra":["DeepInfra/pygmalion-13b-4bit-128g","cognitivecomputations/dolphin-2.6-mixtral-8x7b",
                  "mistralai/Mixtral-8x7B-Instruct-v0.1","lizpreciatior/lzlv_70b_fp16_hf","jondurbin/airoboros-l2-70b-gpt4-1.4.1"],

    "Liaobots":["gpt-3.5-turbo","gpt-4-turbo-preview","gpt-4-plus","claude-3-sonnet-20240229","gpt-4-0613","claude-2.1"],

    "HuggingChat":["mistralai/Mixtral-8x7B-Instruct-v0.1","NousResearch/Nous-Hermes-2-Mixtral-8x7B-DPO","meta-llama/Llama-2-70b-chat-hf"],

    "FlowGpt":["gpt-3.5-long","gpt-4","claude-v2","gpt-3.5-turbo"]

    
```


To getting started 
```
pip install g4f@git+https://github.com/IsNoobgrammer/gpt4free.git
```

Setting up 
```python
from g4f.client import Client
import g4f

import nest_asyncio as na
na.apply()

client = Client()
response = client.chat.completions.create(
    model="gpt-4",
    messages=[{"role": "user", "content": "write a long multiturn discussion between user and assistant in json"} ... ],
    provider=g4f.Provider.Liaobots,
    max_tokens=1234,
    # format="json", # only for deepinfra , output is always in json
    ##supports temprature
)
print(response.choices[0].message.content)
```
