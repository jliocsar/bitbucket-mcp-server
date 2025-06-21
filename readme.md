# 🌬️ bitbucket-mcp-server

Simple MCP implementation for (mostly) pull requests on Bitbucket.

Provide context from your PRs to your favorite LLM and let it review them for you!

Written in Bun and Civet using Cursor.

Read the documentation [here](docs.md).

> 🚧 This repository is a MCP learning exercise and it is still work in progress.
>
> The API here lacks many features as of now. More features might be added in the near future.
>
> Also, the documentation was written by Cursor itself. Don't expect it to be perfect. 🚧

## Install

First clone this repository somewhere you'd like.

Then there are 2 ways to run it locally:

- If you want to download and use the release version, you can run via the binary available in this repository [Releases][bitbucket-mcp-server-releases];
- Otherwise, you'll have to either build from scratch, or install Bun and run the `index.civet` file directly.

### Release

To run from the pre-built binaries, go to the [Releases][bitbucket-mcp-server-releases] page and get the latest release from there.

Extract the binary somewhere you'd like.

Then, add this to your MCP servers settings:

```jsonc
{
  "mcpServers": {
    "Bitbucket": {
      // Or just `bitbucket-mcp-server` if you made it
      // available as a system/user-wide binary
      "command": "/path/to/bitbucket-mcp-server",
      "args": ["username:password"]
    }
  }
}
```

This is enough to get the server going.

### Bun/Build

If you want to run with Bun (or build with it), you'll first need to install `bun` by running:

```sh
curl -fsSL https://bun.sh/install | bash
```

Then from the project directory install all dependencies with:

```sh
bun i
```

#### Running with Bun

To run with `bun` directly, add this entry to your MCP servers settings:

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

#### Building

Run the build command from the project root directory:

```sh
bun run build
```

This will output a binary in the `dist/` folder to whatever architecture you're using.

Then follow the same steps from the [Release](#release) option to add the MCP server to your settings.

## Development

Make sure you have both Bun's runtime and Civet's VSCode/Cursor extension installed.

Then after cloning the repository, install its dependencies:

```sh
cd /path/to/repository
bun i
```

The best way to visualize everything working is by running:

```sh
bun inspect username:password
```

This will open the MCP Inspector with a GUI to play around and explore the MCP tools.

## To do

- Decrease built binary file size
- Github action for build and tests

---

This project was created using `bun init` in bun v1.2.17. [Bun](https://bun.sh) is a fast all-in-one JavaScript runtime.

[bitbucket-mcp-server-releases]: https://github.com/jliocsar/bitbucket-mcp-server/releases
