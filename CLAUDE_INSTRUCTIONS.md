# CLAUDE_INSTRUCTIONS.md (Part 1 of 2)

Created by King Bot for Dan, Saturday Nov 21, 2026, 2:23 AM ET.
No access keys, passwords, tokens, or account numbers are in this file, and none should ever be added.

## 1. Cheap local AI stack on the Beast
- Hardware: Dan's Beast machine, NVIDIA RTX 4060 Ti.
- Runtime: Ollama (or LM Studio).
- Model: a 7-billion-parameter model (qwen2.5:7b or llama3.2).
- First test: answer ONE prompt through the Test-AllFour pipe and measure cost and latency before scaling.

## 2. Three listener bots (left, right, center)
- Left and right listeners monitor the conversation for early-warning signals.
- They alert the center bot when a signal appears.

## 3. Center bot: responding to someone expressing suicidal thoughts
- Respond calmly and rationally. Ask what led them there.
- Reframe pain as peaks and valleys in time: this moment is a valley, not the whole map.
- Anchor to emotional connections: family, kids, the dog, the stars, the ocean.
- Avoid graphic detail. Never discuss methods.
- Always point the person to real help: in the US, call or text 988 (Suicide and Crisis Lifeline); in an emergency, call 911.

## 4. Data sources to bolt on
- SEC EDGAR: free and structured, the easiest place to start.
- Federal Reserve sites: RSS feeds and PDFs, doable.
- News scraping: legally messy. Respect rate limits and each site's terms of service.
- The creativity is in what the model does with the connections between sources, not the data itself.

## 5. Infrastructure
- n8n Cloud workspace: aitraderinsights (Start Yearly plan, $240, paid Oct 23, 2026).
  - Nightly Page: ON
  - 007 Live Feed for 008: ON
  - CPI Report Card: OFF
- AWS: S3 bucket market-insights-nightly-bank; IAM user beastcli (Dan holds the keys; run `aws configure --profile beastcli` on the Beast).
- GitHub (ipicturetrading-coder): range-vessels-record, ai-trader-insights, grok-basket-watch-backup, range-vessels-public.

## 6. Connection test
- `Test-AllFour.ps1` in the Beast's KingBot Drip folder checks n8n, Microsoft 365, GitHub, and AWS, read-only, and logs each run with an ET timestamp.
- Run: `powershell -ExecutionPolicy Bypass -File "KingBot Drip\Test-AllFour.ps1"`
