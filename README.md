# Kaggle-Ollama-Ngrok
Vibe coded jupyter notebook and a html that mimics claude's interface 

## Steps to configure 
1. Import the notebook on kaggle set accelerator to T4 x 2 [Requires phone number verified account]
2. Setup Ngrok account and generate an access token
3. Execute all the cells of notebook and replace ngrok token with your token

## Running Agentic coding tool
The following steps are for claude code 
1. Install it via any pkg manager
example - `brew install claude`
2. Configure claude code
```
export ANTHROPIC_BASE_URL=<url-given-by-ngrok-in-notebook-session>
export ANTHROPIC_AUTH_TOKEN="ollama"          
export ANTHROPIC_API_KEY="ollama"
```
3. Run `claude --model qwen3.8:27b` (replace qwen3.8:27b with any model available in ollama)

## Using the html 
1. Open the html file with any IDE, search for http to find the url and replace it with your ngrok url
2. Search and find qwen to replace it with the model you use, incase of qwen3.8:27b you can ignore this step

## HTTP POST Requests 
Refer to ollama api docs for more info
```
curl <ngrok-url>/api/chat \
  -H "Content-Type: application/json" \
  -d '{
    "model": "qwen3.8:27b",
    "messages": [
      {
        "role": "user",
        "content": "Write a tagline for a coffee shop."
      }
    ],
    "stream": false
  }'

```

## Note
1. Please experiment with other agentic coding tools, I haven't used any of them so cannot really comment on the performance, but based on observation I found claude code to be very slow.
2. Ollama and ngrok are simple to setup, which is why I am using them as part of this pipeline, I am aware that this is not a SOTA production level strategy, this is just for experimental and personal use. I don't want to complicate things for no reason.
3. Kaggle provides 30hours a week, using this approach is far better than free LLM API who rate limit or require billing setup.
4. I will add LangGraph support soon
   






