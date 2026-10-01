# Distribution and verification status

This public Git repository distributes **documentation-only, read-only**
instructions. Developers install them with their own Claude, OpenAI, or Google
accounts. It does not distribute Connexease credentials, source code, or the
private Gem used in an earlier chat test.

| Surface | Distribution path | Verified boundary |
| --- | --- | --- |
| Claude Code | GitHub marketplace; commands in [README](README.md) | Local manifest and one live answer passed. Remote-repo installation still needs a clean-machine test. |
| Claude chat | Customize → Plugins → Add marketplace from GitHub | Supported by Anthropic; not tested with this repo/account. Organization policy may restrict it. |
| Codex CLI | GitHub marketplace; commands in [README](README.md) | Local marketplace and one live answer passed. Remote-repo installation still needs a clean-machine test. |
| ChatGPT desktop | Install from this marketplace in the Plugins Directory | Not yet tested in the desktop UI. |
| ChatGPT web | Separate workspace publication or public directory submission/review | Not published there. A GitHub push alone does not install it for web users. |
| Gemini CLI | Install the repo subdirectory as a skill; command in [README](README.md) | Skill discovery passed locally. Live answer blocked by `UNSUPPORTED_CLIENT` on the pilot machine. |
| Gemini web/app chat | Separate chat Skill/Gem creation or sharing | CLI skill does not auto-import. [Manual instructions](guides/gemini-chat-instructions.md) are a pilot, not a verified universal install link. |

The assistant needs a web/URL-reading tool and access to
`docs.gateway.connexease.com` for current answers. Packaging and installation
do not guarantee the model will follow the skill correctly. Check citations,
credential type, and exact API parameters before relying on a response.

Repository publishing is **not** a submission to Anthropic's or OpenAI's
public plugin directories. Those are separate review and publication steps.
