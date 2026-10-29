# Aura quote catalog

`quotes.json` is the quote and verse catalog used by Aura. The current app still uses its bundled copy; a future app update can fetch this catalog. `manifest.json` carries schema version, catalog version, UTC update time, counts, and the SHA-256 of the exact `quotes.json` bytes. Increment the catalog version whenever the file changes and update the manifest in the same commit.

The root object contains `version`, `quotes`, and `verses`. Quote entries use stable `id`, text `t`, author `a`, categories `c`, and optional source, tags and provenance fields. Verse entries use stable `id`, reference `r`, translations `kjv` and `web`, categories `c`, and optional tags. IDs must not change or be reused: favorites and seen history depend on them. Preserve the source and attribution metadata with each entry.

Apps should validate the schema and checksum, retain the last good cached catalog, and keep a small bundled offline fallback. Favorites and reading history stay on the device, not in this repository.
