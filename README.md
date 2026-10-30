# Jaksa plugin

[Jaksa](https://jaksa.run) is a voice coach for running and other workouts. In
the app it talks to you through your earphones while you train, knowing your
heart rate, pace, distance and route. This plugin brings the same account into
your assistant.

Ask about any workout (every kilometre's pace and heart rate, the map, what you
said to the coach), compare workouts, see your records, and read or change your
goals and training plan in conversation. Jaksa's coach reads that plan before
every workout, so a plan made here is the plan you run.

## What is in it

Only a connection to Jaksa's hosted MCP server. No skills, hooks, commands or
local code; nothing is installed or run on your machine.

| File | For |
|---|---|
| `.mcp.json` | Claude Code and Grok Build (`type: http`) |
| `mcp.json` | Cursor (`type: streamable-http`) |
| `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json` | Claude Code |
| `.grok-plugin/plugin.json` | Grok Build |
| `.cursor-plugin/plugin.json` | Cursor |
| `plugin.json` | other agents that read the agent-plugins.org manifest |

## Install

- **Grok Build:** `/marketplace`, find Jaksa, press `i` (once listed).
- **Claude Code:** `/plugin marketplace add generativechaos/jaksa-plugin`, then
  `/plugin install jaksa@jaksa`. Or without the plugin:
  `claude mcp add --transport http jaksa https://mcp.jaksa.run`.
- **Cursor:** from the Cursor marketplace (once listed), or add
  `https://mcp.jaksa.run` as an MCP server.
- **grok.com, claude.ai, ChatGPT:** add `https://mcp.jaksa.run` as a custom
  connector. Step-by-step pages: <https://jaksa.run/grok>,
  <https://jaksa.run/claude>, <https://jaksa.run/chatgpt>.

## Network and credentials

- **One endpoint:** `https://mcp.jaksa.run`, run by Generative Chaos LLC, the
  maker of Jaksa. Nothing else is called.
- **Sign-in:** OAuth 2.1 with dynamic client registration and PKCE (S256). Your
  assistant registers itself; the first call opens Jaksa's own page, where you
  sign in with Apple, Google or Microsoft, as in the Jaksa app. No API key,
  no secrets in this repo, nothing read from your machine.
- **What it can do:** read and change your own Jaksa account, and, when you ask,
  act beyond it the way the app does: post a workout to Strava or another place
  you set up, email a live-workout link, text a code to confirm your phone,
  control your music on Spotify, look up places, routes, races and weather,
  and comment on or cheer the workouts of runners you follow. Anything that
  cannot be undone (deleting a workout or your account) takes two steps and
  happens only after you agree.

You need a Jaksa account; signing in creates one. Jaksa is not a doctor and
gives no medical advice.

- Privacy: <https://jaksa.run/privacy>
- Terms: <https://jaksa.run/terms>
- Support: <https://jaksa.run/support> · hello@jaksa.run

## License

MIT, © 2026 Generative Chaos LLC. The Jaksa name and logo are not covered by
the license.
