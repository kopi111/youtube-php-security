# YouTube PHP Security Channel

One real, already-patched PHP vulnerability every week — explained so developers
can **defend** against it. Format: *Bug → Impact → Fix → Takeaway*.

Byline / host: **Sergeant Dwayne Aitken**

## Non-negotiable guardrails (every episode)
1. **Lab-only.** Demos run against a target you own. Never a live or third-party system.
2. **Disclosed & patched only.** We explain history, we don't drop 0-days.
3. **On-screen disclaimer** during every exploit demo.

## Weekly production pipeline
| Stage | How |
|-------|-----|
| Research the CVE | confirm affected + patched versions, read the real patch |
| Build the lab | Docker (Linux bugs) or Vagrant (Windows bugs) |
| Record the demo | Playwright script — same run every take, doubles as proof |
| Write the script | `episodes/<ep>/script.md`, defender's-walkthrough structure |
| Title/desc/tags/thumb | `episodes/<ep>/seo.md` |
| Publish | upload UNLISTED → review → public |

## Episodes
- `episodes/ep01-cve-2017-9841/` — **LAUNCH.** PHPUnit eval-stdin.php RCE.
  Linux Docker lab, real exploit verified running locally. (**built & demo works**)
- `episodes/ep02-cve-2024-4577/` — PHP-CGI argument injection on Windows.
  Fully scripted; demo needs a Windows VM (Vagrant lab provided). (**built, Windows lab pending**)

## Running episode 1's demo (real exploit, ~30 seconds)
```bash
cd episodes/ep01-cve-2017-9841/lab  && docker compose up -d
cd ../demo && ./run-demo.sh         # before = RCE, after = neutralised
cd ../lab && docker compose down     # clean up
```
