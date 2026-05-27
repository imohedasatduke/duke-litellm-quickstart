# Duke AI Gateway — Student Quickstart

A one-paste setup for students to start making AI API calls through Duke's
[AI Gateway](https://litellm.oit.duke.edu) (a LiteLLM proxy) using
[Claude Code](https://claude.com/claude-code) — no prior terminal, Python, or git
experience required.

## How students use this

**Prerequisites:** a Duke NetID, and [Claude Code](https://docs.claude.com/en/docs/claude-code/quickstart)
installed and open in a folder (`claude` in a terminal, or the VS Code extension).

Then **paste this prompt into Claude Code** and follow along:

```text
You are helping a Duke University student — a beginner who may have never used a
terminal, Python, or git — set up their own computer to make AI calls through
Duke's AI Gateway (the LiteLLM proxy at https://litellm.oit.duke.edu).

Step 1 — Download the setup guide and follow it exactly, top to bottom:
  https://raw.githubusercontent.com/imohedasatduke/duke-litellm-quickstart/main/SETUP.md
Fetch it (e.g. `curl -fsSL <url> -o SETUP.md`) and READ it fully before doing
anything — do not guess its contents.

How to work with me for this whole session:
- Assume nothing is installed. Check before you use any tool; install or explain if it's missing.
- Before each command, tell me in one plain sentence what it does and what I should expect to see.
- NEVER put my API key in code or any file that gets committed. Use a .env file and confirm .env is in .gitignore.
- We are NOT done until you've run a real test call to the Gateway and shown me the model's actual reply.
- If anything errors, stop, explain it in plain language, and walk me through the fix before continuing.
```

That's it — Claude pulls the full [`SETUP.md`](SETUP.md) and walks the student through
the rest.

## What the setup produces

- A project folder with a Python virtual environment and the OpenAI SDK installed.
- The student's API key stored safely in a `.env` file (and `.gitignore`d).
- A working `hello.py` that makes a **real** call to the Gateway and prints the reply.
- A project `CLAUDE.md` so future Claude Code sessions already know the Gateway,
  the available models, and their costs.

It defaults to the **free, on-prem `Mistral on-site`** model so students can
experiment without spending anything.

## For instructors

- Edit [`SETUP.md`](SETUP.md) to change the flow — students always fetch the latest
  version, so you never re-distribute the prompt.
- The model/cost cheat-sheet in `SETUP.md` is generated from the live `/v1/models`
  list; refresh it if Duke adds or reprices models.
- Key acquisition, conventions (`LITELLM_TOKEN`, base URL, `uv`), and examples follow
  Duke OIT's official [aigateway-quickstart](https://gitlab.oit.duke.edu/ai-tech/aigateway-quickstart).
