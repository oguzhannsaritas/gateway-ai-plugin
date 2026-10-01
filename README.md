# Connexease Gateway Docs AI plugin (pilot)

This is a read-only documentation assistant for
<https://docs.gateway.connexease.com/>. It answers Gateway questions with links
to the public pages it checks. It does **not** include Connexease source code,
credentials, an MCP server, or tools for sending messages or creating accounts.
It needs the host AI's web/URL-reading capability and access to the docs site;
it cannot guarantee an answer when those are unavailable.

This repository contains a Claude Code marketplace, a portable skills-only
plugin for Codex/ChatGPT desktop, and an equivalent Gemini CLI skill. There is
no single install command shared by all three products.

## Install from this repository

Run only the commands for the product you use. Sign in to that product with
your own account; no Connexease or AI-provider API key is supplied here.

### Claude Code

```sh
claude plugin marketplace add oguzhannsaritas/gateway-ai-plugin
claude plugin install connexease-gateway-docs@connexease-gateway
claude plugin list
```

Start a new Claude Code session. Ask a Gateway question normally, or invoke
`/connexease-gateway-docs:ask` explicitly. Claude's chat app can also add a
GitHub marketplace through **Customize → Plugins → Add marketplace**, subject
to the account or organization's plugin policy.

### Codex CLI / ChatGPT desktop

```sh
codex plugin marketplace add oguzhannsaritas/gateway-ai-plugin
codex plugin list --marketplace connexease-gateway --available
codex plugin add connexease-gateway-docs@connexease-gateway
```

Start a new Codex session and ask a Gateway question normally. In the ChatGPT
desktop app, install from the `Connexease Gateway` marketplace in the Plugins
Directory and start a new chat. GitHub installation alone does **not** publish
this plugin to the public ChatGPT web directory; that requires a separate
OpenAI submission and review.

### Gemini CLI

```sh
gemini skills install https://github.com/oguzhannsaritas/gateway-ai-plugin.git --path gemini-cli/connexease-gateway-docs
gemini skills list
```

Start Gemini CLI, approve skill activation if prompted, and ask a Gateway
question. Gemini web/app chat does not automatically import a CLI skill from
this repo; see [the manual chat draft](guides/gemini-chat-instructions.md).

## Try a question

> Gateway sandbox'ta gerçek WhatsApp mesajı göndermeden API isteğini nasıl test
> ederim? Resmî doküman linkini de ver.

The assistant should verify the current Quickstart page, explain that
`is_fake=true` is a query parameter, and cite the documentation. It must not
send an API request on your behalf. See [test prompts](guides/test-prompts.md).

## Scope and verification

The URLs in the skill are **entry points**, not a complete local copy or
index of every documentation page. The assistant should follow official
same-site navigation and check relevant content at question time.

Before this GitHub publication, Claude Code manifest validation and a live
read-only answer passed. Codex CLI local marketplace installation and a live
read-only answer passed. Gemini CLI discovered the skill, but this test
machine's Google OAuth returned `UNSUPPORTED_CLIENT`, so a live Gemini CLI
answer is not yet verified. ChatGPT desktop/web and repository-based installs
still require separate end-to-end testing. See [distribution status](DISTRIBUTION.md).

Only the files in this repository are distributed. The local test machine's
temporary runtime, archives, and private Gemini Gem are not included.
