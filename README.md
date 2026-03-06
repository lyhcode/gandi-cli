# gandi-cli

CLI tool for [Gandi.net](https://www.gandi.net/) API.

## Quick Start

Run directly without installing:

```bash
uvx --from git+https://github.com/lyhcode/gandi-cli gandi --help
```

## Install

```bash
pip install gandi-cli
```

## Authentication

Set your [Gandi Personal Access Token](https://admin.gandi.net/organizations/account/pat):

```bash
export GANDI_PAT=your-token-here
```

Or save it to config:

```bash
gandi auth login
```

## Usage

```bash
# Domains
gandi domain list
gandi domain info example.com
gandi domain check myname.com

# DNS Records
gandi dns list example.com
gandi dns create example.com www A 1.2.3.4
gandi dns update example.com www A --value 5.6.7.8
gandi dns delete example.com www A

# Email
gandi email forward list example.com
gandi email mailbox list example.com

# Certificates
gandi cert list
gandi cert info <cert-id>

# Organizations
gandi org list
gandi org whoami

# Output formats
gandi -o json domain list
gandi -o plain domain list
gandi -o table domain list   # default
```

## Sandbox

Use `--sandbox` to test against the Gandi Sandbox API:

```bash
gandi --sandbox domain list
```

## Configuration

Config file: `~/.config/gandi-cli/config.toml`

```toml
[auth]
pat = "your-token"

[defaults]
output = "table"
sharing_id = "your-org-id"
```

## License

MIT
