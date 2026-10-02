# ipas-fetcher

A scheduled GitHub Actions workflow that checks a set of tracked apps for updates, fetches new builds, and stages them for a private build pipeline. Runs daily; publishes nothing here — builds pass through the runner on their way to the private side, which holds the configuration and the app list.

## Setup

Repository secrets:

- `INTAKE_REPO` — target repository, `OWNER/NAME`
- `INTAKE_TOKEN` — fine-grained token for that repository with **Contents** read/write and **Actions** read/write

```sh
gh secret set INTAKE_REPO --repo RyoKamui/ipas-fetcher
gh secret set INTAKE_TOKEN --repo RyoKamui/ipas-fetcher
```

## Manual run

Actions → **IPA intake** → Run workflow.
