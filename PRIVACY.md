# Privacy

FinLens Catalyst Mapper is a local plugin package. By default, it does not ship with a built-in remote telemetry service, private API key, or hard-wired personal data provider.

## What the public plugin does

- Reads the user's prompt inside the host environment.
- Uses the host model runtime and any tools the host makes available.
- Encourages verification against primary sources, public data sites, and optional user-configured providers.

## What the public plugin does not do by itself

- It does not bundle a tracking SDK.
- It does not include a built-in analytics endpoint.
- It does not include private credentials.
- It does not force a specific premium data vendor.

## Optional providers

If a user configures optional external providers, those providers may have their own privacy policies and data handling rules. Users are responsible for reviewing and accepting those terms before use.

## Contact

Replace the author and repository placeholders in `plugin.json` before public release so users know where to find the final privacy contact.
