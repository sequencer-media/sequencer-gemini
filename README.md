# Sequencer for Google agents

Generate AI media, quote costs before creating, and edit Sequencer projects using the hosted MCP connection and Sequencer skill.

## Antigravity CLI

Clone this repository, then install the local package:

```sh
git clone https://github.com/sequencer-media/sequencer-gemini.git
agy plugin install ./sequencer-gemini
```

Open `/mcp` in Antigravity, connect Sequencer, and approve access to your Sequencer account. Ask the agent to load a Sequencer skill or create a project.

This package includes the native `plugin.json`, `mcp_config.json`, and `skills/` format supported by Antigravity. It also retains the Gemini CLI extension format for eligible Gemini CLI accounts.

## Gemini CLI

```sh
gemini extensions install https://github.com/sequencer-media/sequencer-gemini
```

Open `/mcp`, authenticate Sequencer, and use the tools in a conversation.

## Usage

Before paid generation, ask for a quote and approve your budget. Importing an existing image and making a standard MP4 export can test the connection without AI generation.

[Connect and view pricing](https://sequencer.media/plugin?source=gemini-cli).

Support: support@sequencer.media. [Privacy](https://sequencer.media/privacy-policy). [Terms](https://sequencer.media/terms-of-service). Package license: [MIT](LICENSE).
