# Agent Browser Skill

An [Agent Skill](https://agentskills.io) for browser automation using [agent-browser](https://github.com/vercel-labs/agent-browser).

## What is this?

This skill teaches AI agents how to automate web browsers - navigating pages, filling forms, clicking buttons, taking screenshots, and extracting data.

## Installation

### For Claude Code

```bash
mkdir -p .claude/skills
curl -o .claude/skills/agent-browser/SKILL.md \
  https://raw.githubusercontent.com/bentossell/skill-agent-browser/main/SKILL.md
```

### For other agents

Copy the `SKILL.md` file to your agent's skills directory.

## Prerequisites

The agent needs `agent-browser` CLI installed:

```bash
npm install -g agent-browser
agent-browser install  # Download Chromium
```

## Usage

Once installed, ask your agent to:

- "Open example.com and take a screenshot"
- "Fill out the login form and submit"
- "Extract all product prices from this page"
- "Test the signup flow"

The skill teaches the agent to use `agent-browser snapshot` to discover interactive elements, then interact using refs like `@e1`, `@e2`.

## Example Session

```
User: Go to hacker news and click the "new" link

Agent: I'll navigate there and find the link.

$ agent-browser open https://news.ycombinator.com
$ agent-browser snapshot -i
# Shows: link "new" [ref=e2]

$ agent-browser click @e2
$ agent-browser snapshot -i
# Now on /newest page
```

## Learn More

- [Agent Skills Specification](https://agentskills.io/specification)
- [agent-browser CLI](https://github.com/vercel-labs/agent-browser)

## License

Apache-2.0
