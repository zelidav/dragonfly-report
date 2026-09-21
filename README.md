# Dragonfly Cloud Bar — Season One

SYPP Cloud Bar field report for Dragonfly New York, covering ten measured
activations between 1 August and 17 September 2026.

The page is **AES-GCM encrypted at rest** (PBKDF2-SHA256, 250k iterations):
`payload.json` is ciphertext only, so view-source reveals nothing. Requires
HTTPS — `crypto.subtle` is unavailable on insecure origins.

The 64 photos under `photos/` are ordinary static files and are **not**
encrypted. The gate deters casual access; it does not seal the directory.

## Rebuilding

Source lives outside this repo, in `~/sypp-dragonfly-report`:

    python tools/encrypt.py '<passphrase>'    # site/ -> dist/
    # then commit dist/ here

`site/index.html` is the self-contained report (data inlined, no fetch).
`Dragonfly-CloudBar-SeasonOne.pdf` is built from `print/index.html` with
headless Chrome `--print-to-pdf`.
