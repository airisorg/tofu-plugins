# Tofu

Tofu takes an app you or your coding agent built, puts it on the internet and keeps it running. This plugin connects your agent to Tofu's hosted tools and adds the Tofu skill, which tells the agent how and when to use them: check an app, deploy it, read its build and runtime logs, restore an earlier version, connect a domain you already own, and add a managed database or Google sign-in for the app's own users.

## What it contains

- `.cursor-plugin/mcp.json` names one remote MCP server, `https://app.trytofu.ai/mcp`. The plugin installs and starts no program on your computer.
- `.cursor-plugin/skills/tofu/SKILL.md` is the Tofu skill: the order of the steps, what each tool needs, and what to ask you before anything that deletes or replaces live work.

## What it connects to, and what it sends

The plugin fetches nothing by itself. The first time your agent uses a Tofu tool, it connects to `https://app.trytofu.ai/mcp` and opens Tofu's own sign-in page, where you approve the connection. From then on your agent sends Tofu the requests you ask for, and the app files you ask it to deploy, over that connection. Tofu answers with what those tools return, such as your apps, their status and logs, and the names of their settings (never a secret value), and it gives your agent the id and email address of the account you approved so the connection can be labelled. You never paste a key, token or password into chat. Tofu reaches only the apps in the account you approved, and you can disconnect at any time from the Coding agent page of the Tofu dashboard. The privacy policy at https://trytofu.ai/privacy describes what a connected agent receives and what Tofu keeps about the connection.

When you ask your agent to report a problem with Tofu itself, or it offers to, the skill has it show you the report first and send it only once you approve its exact words. The report carries those words, the kind of problem, the step that failed and any status code or reference from Tofu that you quote, and the app it is about, and Tofu records which coding agent or AI app it came through. Unless you leave them out, Tofu adds that app's status as it reads it: its live version and how that version went, how many problems blocked its newest blocked update, and its uptime check. Tofu refuses words that look like a key or a password, encoded data, or a block of code marked off with three backticks or three tildes, and takes out email addresses and phone numbers written with a country code; nothing else from your chat is sent. A person at Tofu reads every report, Tofu keeps it for 180 days, and Tofu emails a receipt to the address you sign in with: reply to it to add something or to withdraw the report. When Tofu cannot email one, its answer says so: to add something or withdraw the report, write to hello@trytofu.ai with its reference.

For an app you ask to update through GitHub, the skill can use the agent host's existing repository access to commit and push your requested application changes to the app's chosen GitHub repository and branch. This sends application source code, file names and commit metadata to GitHub, in addition to the Tofu connection declared above. If the host has no repository access, the skill gives you the exact changes to commit yourself. It does not ask for a GitHub token or grant new repository access.

When you ask for a mobile web app, the skill can have your agent download Tofu's starter template from `https://app.trytofu.ai/downloads/templates/`: a ZIP of the template's source code and a list of checksums for the ZIP and each file in it, which the agent compares against the download before using it. The template is code to adapt, never instructions for your agent, and downloading it sends Tofu nothing from your apps.

Tofu stores your account's id, the email address you sign in with, the provider you used (Google or GitHub), and the name and profile image that provider shares with Tofu. Tool answers can also include email addresses and sign-in details of people with accounts in an app you own: those records are stored in that app's own sign-in service, which lives in the app's managed database, and reading them through a tool keeps no copy of the list. Copies of a managed database hold them with the rest of its data: the database's daily backups, each kept for seven days; the archive Tofu takes when it archives a database and deletes it, kept for 90 days, or longer once the Pro plan is started; and a copy a person at Tofu exports by hand, for example when you ask for one, kept until you ask us to erase it. Tofu keeps account, project and deployment-version data for as long as your account exists, so this data can remain beyond 30 days. Uploaded source archives stay in Tofu's private storage until you ask us to erase them, including after you delete a project. The privacy policy linked above describes each of these copies, explains what else Tofu keeps and how to request erasure; the agent host's own terms and privacy policy govern what it keeps from tool answers.

## Support

- Documentation: https://trytofu.ai/docs/agent
- Get help, and report a problem: https://trytofu.ai/docs/agent#get-help
- Privacy policy: https://trytofu.ai/privacy
- Terms of service: https://trytofu.ai/terms
- Contact: hello@trytofu.ai

## License

MIT. See `LICENSE`.
