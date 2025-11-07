# Known Issues

- Oracle is centralized; price manipulation risk if owner is compromised
- No `pause()` or emergency stop
- No borrow cap per user or per asset
- TWAP interval is fixed (30 minutes); not dynamically adjusted based on volatility
- Interest rate model is static; no dynamic market response