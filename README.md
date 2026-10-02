# Tofu

Tofu takes an app you or your coding agent built, puts it on the internet and keeps it running. This plugin connects your agent to Tofu's hosted tools and adds the Tofu skill, which tells the agent how and when to use them: check an app, deploy it, read its build and runtime logs, restore an earlier version, connect a domain you already own, and add a managed database or Google sign-in for the app's own users.

## What it contains

- `.mcp.json` names one remote MCP server, `https://app.trytofu.ai/mcp`. The plugin installs and starts no program on your computer.
- `skills/tofu/SKILL.md` is the Tofu skill: the order of the steps, what each tool needs, and what to ask you before anything that deletes or replaces live work.

## What it connects to, and what it sends

The plugin fetches nothing by itself. The first time your agent uses a Tofu tool, it connects to `https://app.trytofu.ai/mcp` and opens Tofu's own sign-in page, where you approve the connection. From then on your agent sends Tofu the requests you ask for, and the app files you ask it to deploy, over that connection. Tofu answers with what those tools return, such as your apps, their status and logs, and the names of their settings (never a secret value), and it gives your agent the id and email address of the account you approved so the connection can be labelled. You never paste a key, token or password into chat. Tofu reaches only the apps in the account you approved, and you can disconnect at any time from the Coding agent page of the Tofu dashboard. The privacy policy at https://trytofu.ai/privacy describes what a connected agent receives and what Tofu keeps about the connection.

## Support

- Documentation: https://trytofu.ai/docs/agent
- Privacy policy: https://trytofu.ai/privacy
- Terms of service: https://trytofu.ai/terms
- Contact: hello@trytofu.ai

## License

MIT. See `LICENSE`.
