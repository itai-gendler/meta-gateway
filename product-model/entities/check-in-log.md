---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Checkins.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/checkin.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/checkin/service.go"
    }
  ],
  "domain": "checkins"
}
---



# Check in log

An operator-visible result of a manual or scheduled native check-in.

## Information kept

- **Site** — the associated upstream site.
- **Credential** — the reference to the upstream credential that was checked in; no credential plaintext is kept in this log.
- **Trigger** — manual or scheduled initiation.
- **Time** — the recorded native check-in execution time.
- **Outcome** — the successful, failed or skipped observed result.
- **Category** — the classified recorded event or failure category.
- **Reward** — the observed upstream check-in reward.
