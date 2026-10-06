# Sequencer for Gemini CLI

Create product ads, animate images, generate images, video and voiceovers, and edit Sequencer projects from your assistant.

Connect your Sequencer account through OAuth. Generation uses your existing account allowance or balance, with a USD quote before spending.

Setup and starter prompts: https://sequencer.media/plugin?source=gemini-cli

## Install

Install the extension:

```sh
gemini extensions install https://github.com/sequencer-media/sequencer-gemini
```

Run `/mcp` in Gemini CLI, authenticate Sequencer, and confirm tools are connected. For a local checkout, use `gemini extensions install /absolute/path/to/this/folder`.

## Try it

- “Animate my image into a 5-second video. Show the model, settings, and USD quote first.”
- “Create a three-shot product ad from this brief. Quote the complete plan before generating.”
- “Open my Sequencer project and help me improve its shots and voiceover.”

Approve the quoted plan and budget. Your assistant tracks the media job and returns a playable result. Open the project in Sequencer to continue editing.

Configuration: `gemini-extension.json`. Support: support@sequencer.media. [Privacy](https://sequencer.media/privacy-policy). [Terms](https://sequencer.media/terms-of-service).

## Connection and license

This package connects to `https://mcp.sequencer.media/` using Sequencer OAuth. Your assistant works with the account and projects you authorize. It asks for approval of the quoted generation plan and budget before spending.

The connector package is distributed under the [MIT license](LICENSE). The Sequencer service follows its linked terms above.
