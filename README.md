# claude-config-editor

Large Claude configuration files can be awkward to inspect and clean up by hand. Use this local Claude config editor to review project history in `.claude.json`, export conversations before deletion, and manage MCP servers without editing JSON directly.

## Features

- Inspect configuration size and rank projects by size, name, or message count.
- Search project histories and select multiple projects for deletion.
- Export individual project histories as JSON before removing them.
- Add or remove MCP servers and inspect their commands, arguments, environment variables, and working directories.
- Back up the configuration automatically before each save and preview changes before writing them.
- Detect Claude Code and Claude Desktop configurations through a browser interface served locally.

## Installation

You need Python 3.7 or later and a web browser. The interface uses HTML, and the local server uses the Python standard library. No third-party packages or frontend build step are required.

Download or check out this project's source, then enter its directory:

```bash
cd claude-config-editor
python3 --version
```

On Windows, use `py -3` instead of `python3` if that is how Python is installed.

## Usage

Start the local server from the project directory:

```bash
python3 server.py
```

Open `http://localhost:8765` in your browser. No command-line arguments are required for the documented startup path.

Choose the detected configuration you want to edit. In Project History, review the largest entries, export any conversations you want to keep, and select the projects to remove. Click Save Changes to write the updated configuration.

For MCP server changes, open the MCP Servers tab. Review existing entries or add a server with its name and command, then save your changes.

**Export important history before deleting it.** The tool also creates `.claude.backup.json` before each save. Keep a separate backup if you need a copy that later saves cannot replace.

The editor runs locally and does not collect telemetry. Treat configuration exports as sensitive: MCP server environment variables may contain credentials. File-size reductions depend on your configuration; smaller files do not guarantee a particular startup improvement.

## License

MIT. This project is based on [gagarinyury/claude-config-editor](https://github.com/gagarinyury/claude-config-editor). Retain the upstream copyright notice and MIT license text when redistributing its code.

## Related projects

The following repositories were supplied as other tools from the same author. Their functionality was not described in the source material, so consult their READMEs for details:

- [mdsaif786/lan-scan](https://github.com/mdsaif786/lan-scan) — See the repository for its purpose, installation instructions, and supported usage.
- [ProjectKangcutz/modelfusion](https://github.com/ProjectKangcutz/modelfusion) — See the repository for its scope and available integrations.
- [egutierrz/magic8bot](https://github.com/egutierrz/magic8bot) — See the repository for its behavior and setup requirements.

