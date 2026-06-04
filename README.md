<div align="center">

# gemini-wrapped

**Your year in Gemini CLI, beautifully visualized.**

> [!IMPORTANT]
> **This fork fixes support for the latest Gemini CLI (JSONL format)** and adds custom period support with the `--days` option.

Generate a personalized "Wrapped"-style summary of your [Gemini CLI](https://geminicli.com) usage.

Credit: Built on top of [opencode-wrapped](https://github.com/moddi3/opencode-wrapped) by moddi3 ([@moddi3io](https://x.com/moddi3io)) and [cc-wrapped](https://github.com/numman-ali/cc-wrapped) by [@nummanali](https://x.com/nummanali).

[![Gemini CLI](https://img.shields.io/badge/Gemini%20CLI-%231E1E2E?logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNTQ4IiBoZWlnaHQ9IjU0OCIgdmlld0JveD0iMCAwIDU0OCA1NDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CiAgICA8ZyBjbGlwLXBhdGg9InVybCgjY2xpcDBfMTcyXzEyMikiPgogICAgICAgIDxyZWN0IHdpZHRoPSI1NDgiIGhlaWdodD0iNTQ4IiByeD0iMTAwIiBmaWxsPSIjMUUxRTJFIiAvPgogICAgICAgIDxwYXRoCiAgICAgICAgICAgIGQ9Ik00NDkuMjkyIDAuMDA3ODEyNUM1MDMuOTI1IDAuNjk5NTY0IDU0OCA0NS4yMDI4IDU0OCAxMDBWNDQ4TDU0Ny45OTIgNDQ5LjI5MkM1NDcuMyA1MDMuOTI1IDUwMi43OTcgNTQ4IDQ0OCA1NDhIMTAwQzQ0Ljc3MTUgNTQ4IDAgNTAzLjIyOCAwIDQ0OFYxMDBDNC4wOTE1N2UtMDYgNDUuMjAzMiA0NC4wNzQ0IDAuNzAwMDc3IDk4LjcwNyAwLjAwNzgxMjVMMTAwIDBINDQ4TDQ0OS4yOTIgMC4wMDc4MTI1Wk0xMDAgMzJDNjIuNDQ0NiAzMiAzMiA2Mi40NDQ2IDMyIDEwMFY0NDhDMzIgNDg1LjU1NSA2Mi40NDQ2IDUxNiAxMDAgNTE2SDQ0OEM0ODUuNTU1IDUxNiA1MTYgNDg1LjU1NSA1MTYgNDQ4VjEwMEM1MTYgNjIuNDQ0NiA0ODUuNTU1IDMyIDQ0OCAzMkgxMDBaTTM4My4wOTEgMjM4LjgxOFYzMjIuNDU1TDE2NS42MzcgNDI3VjM2Ni4zNjRMMzQzLjc4MiAyODAuNjM3TDE2NS42MzcgMTk0LjkwOVYxMzQuMjczTDM4My4wOTEgMjM4LjgxOFoiCiAgICAgICAgICAgIGZpbGw9InVybCgjcGFpbnQwX2xpbmVhcl8xNzJfMTIyKSIKICAgICAgICAvPgogICAgICAgIDxwYXRoCiAgICAgICAgICAgIGQ9Ik00NDkuMjkyIDAuMDA3ODEyNUM1MDMuOTI1IDAuNjk5NTY0IDU0OCA0NS4yMDI4IDU0OCAxMDBWNDQ4TDU0Ny45OTIgNDQ5LjI5MkM1NDcuMyA1MDMuOTI1IDUwMi43OTcgNTQ4IDQ0OCA1NDhIMTAwQzQ0Ljc3MTUgNTQ4IDAgNTAzLjIyOCAwIDQ0OFYxMDBDNC4wOTE1N2UtMDYgNDUuMjAzMiA0NC4wNzQ0IDAuNzAwMDc3IDk4LjcwNyAwLjAwNzgxMjVMMTAwIDBINDQ4TDQ0OS4yOTIgMC4wMDc4MTI1Wk0xMDAgMzJDNjIuNDQ0NiAzMiAzMiA2Mi40NDQ2IDMyIDEwMFY0NDhDMzIgNDg1LjU1NSA2Mi40NDQ2IDUxNiAxMDAgNTE2SDQ0OEM0ODUuNTU1IDUxNiA1MTYgNDg1LjU1NSA1MTYgNDQ4VjEwMEM1MTYgNjIuNDQ0NiA0ODUuNTU1IDMyIDQ0OCAzMkgxMDBaTTM4My4wOTEgMjM4LjgxOFYzMjIuNDU1TDE2NS42MzcgNDI3VjM2Ni4zNjRMMzQzLjc4MiAyODAuNjM3TDE2NS42MzcgMTk0LjkwOVYxMzQuMjczTDM4My4wOTEgMjM4LjgxOFoiCiAgICAgICAgICAgIGZpbGw9InVybCgjcGFpbnQxX2xpbmVhcl8xNzJfMTIyKSIKICAgICAgICAvPgogICAgPC9nPgogICAgPGRlZnM+CiAgICAgICAgPGxpbmVhckdyYWRpZW50IGlkPSJwYWludDBfbGluZWFyXzE3Ml8xMjIiIHgxPSIxMjgiIHkxPSIyNzYiIHgyPSIzMDQiIHkyPSIzMDQiIGdyYWRpZW50VW5pdHM9InVzZXJTcGFjZU9uVXNlIj4KICAgICAgICAgICAgPHN0b3Agc3RvcC1jb2xvcj0iIzYxODlGRiIgLz4KICAgICAgICAgICAgPHN0b3Agb2Zmc2V0PSIxIiBzdG9wLWNvbG9yPSIjRkZGRkZGIiAvPgogICAgICAgIDwvaW5lYXJHcmFkaWVudD4KICAgICAgICA8bGluZWFyR3JhZGllbnQgaWQ9InBhaW50MV9saW5lYXJfMTcyXzEyMiIgeDE9IjI5MSIgeTE9IjE2NiIgeDI9IjM4MiIgeTI9IjI0NyIgZ3JhZGllbnRVbml0cz0idXNlclNwYWNlT25Vc2UiPgogICAgICAgICAgICA8c3RvcCBzdG9wLWNvbG9yPSIjRkZGRkZGIiAvPgogICAgICAgICAgICA8c3RvcCBvZmZzZXQ9IjEiIHN0b3AtY29sb3I9IiNGRkZGRkYiIHN0b3Atb3BhY2l0eT0iMCIgLz4KICAgICAgICA8L2xpbmVhckdyYWRpZW50PgogICAgICAgIDxjbGlwUGF0aCBpZD0iY2xpcDBfMTcyXzEyMiI+CiAgICAgICAgICAgIDxyZWN0IHdpZHRoPSI1NDgiIGhlaWdodD0iNTQ4IiBmaWxsPSJ3aGl0ZSIgLz4KICAgICAgICA8L2NsaXBQYXRoPgogICAgPC9kZWZzPgo8L3N2Zz4K)](https://geminicli.com)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Bun](https://img.shields.io/badge/Bun-%23000000.svg?logo=bun&logoColor=white)](https://bun.sh)

<img src="https://raw.githubusercontent.com/jackwotherspoon/gemini-cli-wrapped/main/assets/images/demo-wrapped.png" width="70%" alt="Gemini Wrapped Example">

</div>

---

## Installation

### Quick Start

Run directly from this fork:

```bash
git clone https://github.com/OleksiyM/gemini-cli-wrapped.git
cd gemini-cli-wrapped
bun install
bun src/index.ts --days 50
```

## Usage Options

| Option          | Description                                    |
| --------------- | ---------------------------------------------- |
| `--year <YYYY>` | Generate wrapped for a specific year           |
| `--days <N>`    | **[New]** Generate wrapped for the last N days |
| `--help, -h`    | Show help message                              |
| `--version, -v` | Show version number                            |

### Examples

```bash
# Generate last 50 days wrapped
bun src/index.ts --days 50

# Generate 2026 wrapped
bun src/index.ts --year 2026
```

## Features

- **JSONL support** for the latest Gemini CLI sessions
- **Custom rolling periods** with `--days` flag
- Sessions, messages, tokens, projects, and streaks
- GitHub-style activity heatmap
- Top models breakdown
- Detailed token usage (Input, Output, Cached)
- Shareable PNG image
- Inline image display (Ghostty, Kitty, iTerm2, WezTerm, Konsole)
- Auto-copy to clipboard

## Data Source

Gemini Wrapped reads data from your local Gemini CLI installation (~/.gemini/tmp).
No data is sent anywhere. Everything is processed locally.

## Acknowledgements

Special thanks to the following projects which provided the inspiration and starting point for this tool:
- [opencode-wrapped](https://github.com/moddi3/opencode-wrapped)
- [cc-wrapped](https://github.com/numman-ali/cc-wrapped)

---

<div align="center">

Made with ❤️ for the [Gemini CLI](https://geminicli.com) community

</div>
