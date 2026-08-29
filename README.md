# cf-home-shield 🛡️

Auto-updates Cloudflare Zero Trust Gateway DNS blocklists daily using [cloudflare-gateway-pihole-scripts (CGPS)](https://github.com/mrrfv/cloudflare-gateway-pihole-scripts).

## How it works

A GitHub Action runs every day at 3:00 AM UTC, pulling the latest CGPS scripts from upstream and refreshing the domain blocklists in Cloudflare Gateway — no servers, no maintenance.

## GitHub Secrets & Variables required

### Secrets (Settings → Secrets and variables → Actions → Secrets)

| Name | Description |
|------|-------------|
| `CLOUDFLARE_API_TOKEN` | Cloudflare API token with Zero Trust Read + Edit |
| `CLOUDFLARE_ACCOUNT_ID` | Your Cloudflare account ID |

### Variables (Settings → Secrets and variables → Actions → Variables)

| Name | Default | Description |
|------|---------|-------------|
| `CLOUDFLARE_LIST_ITEM_LIMIT` | `300000` | Max domains (300k for free plan) |
| `BLOCK_PAGE_ENABLED` | `0` | Show block page instead of NXDOMAIN |
| `ALLOWLIST_URLS` | _(empty, uses CGPS defaults)_ | Custom allowlist URLs |
| `BLOCKLIST_URLS` | _(empty, uses CGPS defaults)_ | Custom blocklist URLs |

## Manual run

Trigger a run anytime from **Actions → Update Cloudflare Gateway Blocklists → Run workflow**.

## Local setup

See `/Users/.../cloudflare-gateway-pihole-scripts` for the local scripts.
