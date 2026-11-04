# Working on anproto-fame

Read `WORK_ORDER.md` and the current README before changing this project. Preserve original signed records and distinguish implemented behavior from planned work.

## Git synchronization — standing instruction

Ev explicitly requested on 30 October 2026 that local work and GitHub stay synchronized. Sync is part of completing authorized work; do not wait for a separate push request.

- At session start, inspect `git status`, the current branch, remotes, and upstream. Fetch `origin` and compare local and remote commits before editing. Read incoming changes and updated agent/work-order instructions.
- Preserve uncommitted work before integrating incoming commits. Fast-forward when possible; otherwise reconcile both histories and resolve conflicts deliberately. Never discard local work, overwrite another agent's commits, or force-push to make a branch appear current.
- Use this repository's established default branch and upstream. Keep related repositories coordinated, but inspect each independently; do not blindly stage unrelated changes, secrets, identity backups, generated state, or private research data.
- Run checks appropriate to the reconciled changes and update work orders/handoffs to match observed behavior. Commit completed work in focused commits and push the intended branch to GitHub before finishing a change session, unless Ev explicitly asks to keep it local.
- Fetch again before pushing. If GitHub advanced, integrate the new commits, rerun affected checks, and retry a normal push. After pushing, verify the local HEAD equals the intended GitHub branch tip and inspect the remaining worktree status. Report the commit, branch, checks, and any remaining changes or divergence automatically.
- If authentication, network access, conflicts, failing checks, or unfinished work prevent synchronization, preserve the work and report the exact blocker. Do not claim synchronization from an attempted push or a stale remote-tracking ref. Clearly label any intentionally preserved unfinished checkpoint.
- A GitHub push is source synchronization, not permission to deploy services, publish public test messages, send email, or change production data. Existing release and publication rules still apply. Do not install background auto-pull jobs; sync at session boundaries and coordinated handoffs.

## git-ssb synchronization — all projects

Ev explicitly requested on 1 November 2026 that all projects also be pushed to git-ssb. This applies to every project in this workspace, alongside the GitHub synchronization requirement above. Pushing authorized source changes to git-ssb is part of completing the work; do not wait for a separate push request.

- Inspect each project's `ssb` remote independently. If it is missing, locate the existing git-ssb repository or create one using the local sbot workflow documented in `ssbc/AGENTS.md`, then configure the remote. Do not silently skip git-ssb or create duplicate repositories when an existing one can be found.
- Use our sbot's Git-over-HTTP endpoint (`http://127.0.0.1:8989/git/%25<repo-id>.sha256`), following the current local configuration. Replace legacy `ssb://` remotes with the corresponding HTTP endpoint; do not use the legacy `git-remote-ssb` helper.
- Fetch and compare the intended branch on both `origin` and `ssb` before integrating or pushing. Preserve local work and reconcile incoming commits from either remote. Use each project's established default branch and upstream; never assume every project uses `main`, discard commits, or force-push to synchronize histories.
- Push completed source changes to both GitHub and git-ssb before finishing a change session, unless Ev explicitly asks to keep the work local. Verify the intended branch tip on each remote against local HEAD after pushing; use a fresh remote query rather than relying on stale tracking refs.
- If sbot is unavailable, follow the documented local startup workflow and retry. If repository creation, authentication, connectivity, conflicts, or checks still block synchronization, preserve the work and report the exact blocker and which remote remains unsynchronized. Do not claim completion from an attempted push.
- Report the commit, branch, checks, and synchronization status for both remotes. Keep secrets, identity backups, generated state, and private research data out of source pushes. This instruction authorizes source synchronization; existing deployment and other publication rules still apply.

### Local git-ssb workflow

- From the workspace's `ssbc` checkout, run `npm run agent:preflight` to ensure sbot is listening on port 8989. Leave sbot running.
- If the remote is missing, query sbot's `messagesByType` for `git-repo` messages and compare repository IDs, authors, names, and known remotes. Names alone are not unique. Only create a repository when no existing match is found: run `node bin.js git.create <project-name>` from `ssbc`, then configure `ssb` with the returned HTTP URL. Remove surrounding JSON quotes and preserve URL encoding.
- Fetch both remotes again before pushing. If either advanced, reconcile incoming commits and rerun affected checks before a normal push. Push the intended branch to both remotes; never use force or mirror pushes.
- Verify local HEAD against fresh `git ls-remote --heads origin` and `git ls-remote --heads ssb` results for the intended branch. Re-read HEAD and worktree status afterward to catch concurrent changes. Report any remaining changes or divergence.
