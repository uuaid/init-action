# uuaid/init-action

Give your repository's AI agent a **permanent, verifiable identity** and a live
trust badge — in one CI step.

```yaml
- uses: uuaid/init-action@v1
  id: uuaid
  with:
    api-key: ${{ secrets.UUAID_API_KEY }}   # free key: npx @uuaid/cli signup "<name>"
    agent-name: "My Repo Agent"
    description: "The agent that maintains this project"

- run: echo "Identity: ${{ steps.uuaid.outputs.uuaid }}"
- run: echo "Badge: ${{ steps.uuaid.outputs.badge-markdown }}"
```

On first run it mints a UUAID and writes it to `.uuaid` (commit that file); later
runs reuse it. Outputs the agent's `uuaid` and a ready-to-paste `badge-markdown`
snippet:

[![UUAID verified](https://api.uuaid.org/badge/agent/uuaid.svg)](https://registry.uuaid.org)

## Inputs

| Input | Required | Description |
|---|---|---|
| `api-key` | yes | UUAID partner API key (store as a repo secret) |
| `agent-name` | yes | Display name for the identity |
| `description` | no | What the agent does |

## Outputs

| Output | Description |
|---|---|
| `uuaid` | The agent's permanent UUAID |
| `badge-markdown` | Live trust-badge snippet for your README |

Get a free key: `npx @uuaid/cli signup "My Lab"`. Apache-2.0 · [uuaid.org](https://uuaid.org)
