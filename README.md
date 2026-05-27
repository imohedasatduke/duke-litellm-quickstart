# Duke AI Gateway — Student Quickstart

A one-paste setup for students to start making AI API calls through Duke's
[AI Gateway](https://litellm.oit.duke.edu) (a LiteLLM proxy) using
[Claude Code](https://claude.com/claude-code) — no prior terminal, Python, or git
experience required. Works whether you're **starting fresh or adding Gateway access
to an existing project** (it merges into your existing `.env`, dependencies, etc.).

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
- If I'm already inside an existing project, adapt to it — merge into my existing files (.env, .gitignore, dependencies, CLAUDE.md) instead of recreating or overwriting them.
- We are NOT done until you've run a real test call to the Gateway and shown me the model's actual reply.
- If anything errors, stop, explain it in plain language, and walk me through the fix before continuing.
```

That's it — Claude pulls the full [`SETUP.md`](SETUP.md) and walks the student through
the rest.

## What the setup produces

- The OpenAI SDK added to the project's environment (a new venv on a fresh start, or
  the project's **existing** environment/dependency setup if there already is one).
- The student's API key stored safely in `.env` (created, or **appended** to an existing
  one) and `.env` confirmed in `.gitignore`.
- A working test script that makes a **real** call to the Gateway and prints the reply.
- A `CLAUDE.md` section (created or **appended**) so future Claude Code sessions already
  know the Gateway, the available models, and their costs.

It defaults to the **free, on-prem `Mistral on-site`** model so students can
experiment without spending anything.

## For instructors

- Edit [`SETUP.md`](SETUP.md) to change the flow — students always fetch the latest
  version, so you never re-distribute the prompt.
- The model/cost cheat-sheet in `SETUP.md` is generated from the live `/v1/models`
  list; refresh it if Duke adds or reprices models.
- Key acquisition, conventions (`LITELLM_TOKEN`, base URL, `uv`), and examples follow
  Duke OIT's official [aigateway-quickstart](https://gitlab.oit.duke.edu/ai-tech/aigateway-quickstart).
