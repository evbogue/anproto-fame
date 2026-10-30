# Ledger structure

The ledger is a local Markdown file connecting published work to observations.

```text
Wiredove / SSB / published Wave records
                  |
            source references
                  |
     work → interactions → outcomes
                  |
          effort and review notes
```

## Source references

Keep the original identifier, source system and an accessible URL when available. Record the author key or feed ID when known. Use a separate ledger label for convenient cross-references.

| Source | Reference to retain |
|---|---|
| Wiredove | Signed-message hash and author public key; a post URL when available. |
| SSB | Message ID and author feed ID; a viewer URL when available. |
| Published Wave collaboration | Signed record identifier and author key, or a published URL with its source identifier when available. |
| Project or other public work | Published URL and a release or commit identifier when relevant. |

ANProto signs a timestamp plus a content hash. Wiredove's message ID hashes the signature; its content hash identifies the exact content bytes. SSB uses its own signed message and feed identifiers. Store these identifiers with their source system.

Use the source client's verification result when available and record its date. Mark references whose verification is pending or whose content is unavailable. Preserve the identifiers when access changes.

## Local observations

Each interaction records a date, a stable local person label, the relevant work and the observed action. Outcomes link to supporting interactions where known. Record the evidence and whether the connection was reported by the person or inferred by the researcher.

Use participant labels consistently throughout the experiment. Link accounts only when the person confirms the connection or supporting evidence establishes it. Keep that evidence in the notes.

Relationship context and research observations stay in the creator's local ledger. Choose which entries to share when preparing a public research report.

## Export and recovery

Copy the completed ledger together with any locally retained supporting evidence into a dated directory. Keep relative links to evidence files and original source identifiers in the ledger. Open the copy independently and check that entries, references and evidence remain usable.

The starting implementation is [LEDGER.md](LEDGER.md). Its tables can be exported as CSV or represented as JSON when a later workflow needs it.
