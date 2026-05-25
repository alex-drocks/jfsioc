# Just Fucking Set Identity Onchain

A vulgar public service announcement for Bittensor subnet operators who still ship empty onchain identity metadata.

**Live site:** <https://justfuckingsetidentityonchain.com/>

## What is this?

Bittensor subnets can publish identity metadata that helps validators, miners, stakers, and explorers understand who is operating a subnet and what it does. This parody page exists to shame subnet owners into filling that metadata out instead of hiding behind a coldkey and vibes.

The tone follows the "Just Fucking Use X" meme genre. The command is real.

## Current command

```bash
btcli subnets set-identity \
  --netuid 1 \
  --wallet.name your-coldkey \
  --subnet-name "Your Subnet Name" \
  --github-repo "https://github.com/yourorg/subnet" \
  --subnet-contact "ops@yoursubnet.com" \
  --subnet-url "https://yoursubnet.com" \
  --discord-handle "https://discord.gg/invitecode" \
  --description "What your subnet actually does" \
  --additional-info "Docs, dashboard, model card, or other useful proof" \
  --subtensor.network finney
```

Audit first:

```bash
btcli subnets get-identity \
  --netuid 1 \
  --subtensor.network finney \
  --json-output
```

## Identity fields

`SubnetIdentityV3` includes:

| Field | Purpose |
| --- | --- |
| `subnet_name` | Human-readable subnet name |
| `github_repo` | Source repository or public code location |
| `subnet_contact` | Operational contact |
| `subnet_url` | Website or docs home |
| `discord` | Community or support link |
| `description` | Short explanation of what the subnet does |
| `logo_url` | Logo image URL, when supported by the installed tooling |
| `additional` | Extra proof such as docs, dashboards, audits, or model cards |

Keep field values short and durable. Long-form claims belong on your website or docs, not inside metadata.

## References

- Bittensor BTCLI reference: <https://docs.learnbittensor.org/btcli>
- Subtensor source: <https://github.com/opentensor/subtensor>
- Just Fucking Use archive: <https://justfuckinguse.com/>

## Tech stack

- Static HTML
- Static CSS
- No build step

## License

MIT.
