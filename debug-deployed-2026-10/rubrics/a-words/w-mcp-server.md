# Rubric: MCP server

If the learner misses a question here, set a DEFINE or INTERPRET move for MCP server live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

An MCP server is what plugs a service into your agent as tools it can call: once connected, the
agent sees the service's actions (read logs, list deploys, change a setting) as tools of its own.
The confusables are a CLI, a program the agent drives by typing commands in a terminal; and your
app's backend, the server you wrote that answers your frontend's requests. "Connector" is another
name for it and is not a confusable. Mossharbor is a made-up host.

### q1

- **goal:** `w-mcp-server`
- **move:** DISTINGUISH
- **answer:** With the CLI, the agent types commands into a terminal, as you could, and reads the
  text they print. The MCP server plugs Mossharbor into the agent itself, so its actions show up
  as tools the agent calls directly, with no commands typed.
- **credit:** full for naming how the agent reaches each: typing commands in a terminal for the
  CLI, calling tools the MCP server adds to the agent for the MCP server. Half for only one half,
  such as "the CLI is commands" with nothing on what the MCP server gives the agent. None for an
  incidental difference alone, such as which is newer, or which is easier to set up.

### q2

- **goal:** `w-mcp-server`
- **move:** DISTINGUISH
- **answer:** The backend is your app's server, code you wrote, answering your frontend's requests
  for visitors. Mossharbor's MCP server serves your agent, not your visitors: it gives the agent
  tools for acting on your Mossharbor account, such as reading your backend's logs, and you didn't
  write it.
- **credit:** full for naming whom each serves and for what: the backend answers the app's
  requests for visitors, the MCP server gives the agent tools to work with the host. Half for only
  one half, such as "the backend is my code" with nothing on what the MCP server is for. None for
  an incidental difference alone, such as where each runs, or that both are servers.

### q3

- **goal:** `w-mcp-server`
- **move:** CATCH
- **answer:** An MCP server gives the agent whatever tools the service offers, not only reading
  logs. A host's MCP server can also change settings or start a deploy, so the agent can do those
  unless it is told, or set up, to read only.
- **credit:** full for naming that the MCP server plugs in all the tools the service offers, which
  can include changing things, so reading logs is not all the agent could do. Half for "it can do
  more than read" without saying why. None for a different quibble alone, such as that they should
  use the CLI instead, or that the agent might misread the logs.
