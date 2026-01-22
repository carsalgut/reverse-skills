# Reverse Engineering Skills for Claude Code

A Claude Code plugin marketplace providing reverse engineering skills.

## Skills Included

| Skill | Description |
|-------|-------------|
| `/rev-symbol` | Analyze function symbols (mangled names, calling conventions, etc.) |
| `/rev-struct` | Reconstruct data structures from decompiled code |

## Installation

### Add the Marketplace

```bash
# From GitHub (after publishing)
/plugin marketplace add username/reverse-skills

# From local path (for development)
/plugin marketplace add /path/to/reverse-skills
```

### Install the Plugin

```bash
/plugin install reverse-engineering@reverse-engineering-skills
```

## Usage

### Analyze a Symbol

```
/rev-symbol _ZN5boost6system14error_categoryD2Ev
```

### Reconstruct a Structure

```
/rev-struct

<paste your decompiled code here>
```

## Directory Structure

```
reverse-skills/
├── .claude-plugin/
│   └── marketplace.json          # Marketplace catalog
├── plugins/
│   └── reverse-engineering/
│       ├── .claude-plugin/
│       │   └── plugin.json       # Plugin manifest
│       └── skills/
│           ├── rev-symbol/
│           │   └── SKILL.md      # Symbol analysis skill
│           └── rev-struct/
│               └── SKILL.md      # Structure reconstruction skill
└── README.md
```

## Development

### Validate the Marketplace

```bash
claude plugin validate .
```

Or within Claude Code:

```
/plugin validate .
```

### Test Locally

```bash
/plugin marketplace add ./reverse-skills
/plugin install reverse-engineering@reverse-engineering-skills
```

## Adding More Skills

1. Create a new directory under `plugins/reverse-engineering/skills/`
2. Add a `SKILL.md` file with the skill definition
3. Update version in `plugin.json` if needed

## License

MIT
