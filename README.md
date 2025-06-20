# 🌬️ bitbucket-mcp-server

Simple MCP implementation for Bitbucket pull requests.

Provide context from your PRs to your favorite LLM and let it review them for you!

Written in Bun and Civet.

## Install

First you will need `bun` installed locally:

```sh
curl -fsSL https://bun.sh/install | bash
```

Then in your MCP servers settings:

```json
{
  "mcpServers": {
    "Bitbucket": {
      "command": "bun",
      "args": [
        "run",
        "/path/to/repository/src/index.civet",
        "username:password"
      ]
    }
  }
}
```

## Development

Make sure you have `bun` installed.

Then after cloning the repository and `cd`ing into it:

```sh
bun i
```

The best way to visualize everything working is by running:

```sh
bun inspect username:password
```

This will open the MCP Inspector with a GUI to play around and explore the MCP tools.

## To do

- See if we can build the `index.civet` file into a binary with Bun so that users can download the binary directly.

---

This project was created using `bun init` in bun v1.2.17. [Bun](https://bun.sh) is a fast all-in-one JavaScript runtime.
