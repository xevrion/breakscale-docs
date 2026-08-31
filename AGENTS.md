# Documentation project instructions

Docs for [Breakscale](https://github.com/xevrion/breakscale), a system design
simulator. Built on Mintlify: MDX pages with YAML frontmatter, configuration in
`docs.json`.

## Everything under examples/ is generated. Do not edit it.

The 23 example pages are written by `tools/example-pages.ts` in the simulator's
repository, from the presets themselves, and the numbers in them are measured by
running each design through the real engine at build time.

Editing a page here is worse than useless: the change is lost on the next
generate, and until then the docs disagree with the tool. Fix the preset or the
generator instead, then run:

```bash
cd ../breakscale   # wherever the simulator repo lives
bun run tools/build-docs.ts ../breakscale-docs
```

That also rewrites the Examples group in `docs.json`, so a new preset appears in
the navigation without anybody remembering to add it.

## The rule the whole project runs on

The numbers have to be true. This is a tool people learn from, so a plausible
looking number is worse than no number at all. That applies to prose here as
much as to the simulator: do not write "roughly 100 requests a second" beside a
table that measured 91.

If a claim cannot be measured or cited, either measure it or cut it.

## Style

- Second person, active voice
- One idea per sentence, and vary the length so it reads like a person wrote it
- Sentence case for headings
- No em dashes, no arrow chains
- Code formatting for file names, commands and paths
- Spell out what a number means on first mention: "91 requests a second" rather
  than "91 rps"

## What belongs here

Teaching material: what a design does, why it breaks, what to change. The
simulator's own README covers building and contributing to the codebase, and
duplicating it here only creates a second copy to drift.

## Mintlify tooling

- MCP server for editing content and settings: `https://mcp.mintlify.com`
- MCP server for Mintlify's own docs: `https://www.mintlify.com/docs/mcp`
