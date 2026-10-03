# Tofu

Tofu takes an app you or your coding agent built, puts it on the internet and keeps it running. This plugin connects your agent to Tofu's hosted tools and adds the Tofu skill, which tells the agent how and when to use them: check an app, deploy it, read its build and runtime logs, restore an earlier version, connect a domain you already own, and add a managed database or Google sign-in for the app's own users.

## What it contains

- `.mcp.json` names one remote MCP server, `https://app.trytofu.ai/mcp`. The plugin installs and starts no program on your computer.
- `skills/tofu/SKILL.md` is the Tofu skill: the order of the steps, what each tool needs, and what to ask you before anything that deletes or replaces live work.

## What it connects to, and what it sends

The plugin fetches nothing by itself. The first time your agent uses a Tofu tool, it connects to `https://app.trytofu.ai/mcp` and opens Tofu's own sign-in page, where you approve the connection. From then on your agent sends Tofu the requests you ask for, and the app files you ask it to deploy, over that connection. Tofu answers with what those tools return, such as your apps, their status and logs, and the names of their settings (never a secret value), and it gives your agent the id and email address of the account you approved so the connection can be labelled. You never paste a key, token or password into chat. Tofu reaches only the apps in the account you approved, and you can disconnect at any time from the Coding agent page of the Tofu dashboard. The privacy policy at https://trytofu.ai/privacy describes what a connected agent receives and what Tofu keeps about the connection.

For an app you ask to update through GitHub, the skill can use the agent host's existing repository access to commit and push your requested application changes to the app's chosen GitHub repository and branch. This sends application source code, file names and commit metadata to GitHub, in addition to the Tofu connection declared above. If the host has no repository access, the skill gives you the exact changes to commit yourself. It does not ask for a GitHub token or grant new repository access.

Tofu stores your account's id and email address. Tool answers can also include email addresses and sign-in details of people with accounts in an app you own: those records are stored in that app's own sign-in service, and Tofu reads them without keeping a separate copy of the list. Tofu keeps account, project and deployment-version data for as long as your account exists, so this data can remain beyond 30 days. Uploaded source archives stay in Tofu's private storage until you ask us to erase them, including after you delete a project. The privacy policy linked above explains what Tofu keeps and how to request erasure; the agent host's own terms and privacy policy govern what it keeps from tool answers.

## Support

- Documentation: https://trytofu.ai/docs/agent
- Privacy policy: https://trytofu.ai/privacy
- Terms of service: https://trytofu.ai/terms
- Contact: hello@trytofu.ai

## License

MIT. See `LICENSE`.
