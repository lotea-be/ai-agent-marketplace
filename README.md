# lotea-agents

Lotea's catalog of Claude Code agents and workflows, distributed as a [Claude Code plugin marketplace](https://docs.claude.com/en/docs/claude-code/plugins).

## Add the marketplace

In Claude Code, add this repository as a marketplace:

```
/plugin marketplace add lotea-be/ai-agent-marketplace
```

You can also point at the Git URL directly:

```
/plugin marketplace add https://github.com/lotea-be/ai-agent-marketplace.git
```

Once added, refresh it any time to pick up new or updated plugins:

```
/plugin marketplace update lotea-agents
```

## Install a plugin

Browse and install interactively:

```
/plugin
```

Or install a specific plugin directly by name:

```
/plugin install qrspi@lotea-agents
```

After installing, restart Claude Code (or reload the session) so the plugin's commands, subagents, and skills are loaded. Manage installed plugins — enable, disable, or remove — from the `/plugin` menu.

## Available plugins

| Plugin | Category | Description |
| --- | --- | --- |
| `qrspi` | workflow | Eight-stage spec-driven workflow (Questions → Research → Design → Structure → Plan → Worktree → Implement → PR) on top of OpenSpec. Includes `/qrspi-*` commands, `opsx-*` helpers, seven stage subagents, and supporting skills. |

## Contributing a plugin

Add an entry to the `plugins` array in [.claude-plugin/marketplace.json](.claude-plugin/marketplace.json):

```json
{
  "name": "my-plugin",
  "source": { "source": "github", "repo": "lotea-be/my-plugin" },
  "description": "What the plugin does.",
  "category": "workflow",
  "tags": ["tag-a", "tag-b"]
}
```

Each plugin lives in its own repository under [lotea-be](https://github.com/lotea-be) and is referenced here by `source`. After updating the manifest, bump `metadata.version` and run `/plugin marketplace update lotea-agents` to test.

## License

[MIT](LICENSE) © Lotea
