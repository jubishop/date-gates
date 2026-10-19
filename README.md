# Date gates

Each open issue here is a date gate. An issue in another repository that can't
start before a date is marked *Blocked by* that date's gate, so GitHub shows it
as Blocked, and lists it under `is:blocked`, until the day arrives.

- A gate's title is `Not before <Weekday>, <YYYY-MM-DD>`, such as
  `Not before Monday, 2026-12-21`. Reuse the open gate for a date instead of
  adding another.
- Every morning, the [Close due gates](.github/workflows/close-due-gates.yml)
  workflow closes each gate whose date has arrived in Pacific time. Closing a
  gate unblocks every issue it blocks.
- Gates are day-level. The waiting issue's timing note gives any exact time.
- A gate whose title has no valid date fails the workflow, so GitHub reports it
  instead of leaving the gate open forever.
- The repository is public, so the workflow's minutes are free. GitHub disables
  a public repository's scheduled workflows after 60 days without a commit, so
  the workflow adds an empty commit once `main` has gone 45 days without one.
